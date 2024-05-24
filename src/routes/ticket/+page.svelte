<script lang="ts">
  import { onMount } from "svelte";
  import Orders from "$lib/components/form/Orders.svelte";
  let requestType = "Other";
  let showAdditionalFields = false;
  import { Select, Label } from "flowbite-svelte";
  import Returns from "$lib/components/form/Returns.svelte";
  import Billing from "$lib/components/form/Billing.svelte";
  import Preorders from "$lib/components/form/Preorders.svelte";
  import Merchandise from "$lib/components/form/Merchandise.svelte";
  import Technical from "$lib/components/form/Technical.svelte";
  import Other from "$lib/components/form/Other.svelte";
  let selectedType;
  let loading = false;

  let request = [
    { value: "-", name: "Choose a request" },
    { value: "orders", name: "Orders" },
    { value: "returns", name: "Returns" },
    { value: "billing", name: "Billing" },
    { value: "preorders", name: "Preorders (Pokemon Center)" },
    { value: "merchandise", name: "Merchandise or Promotions" },
    { value: "technical", name: "Technical Issue" },
    { value: "other", name: "Other" },
  ];

  let selected = "-";
  function handleRequestTypeChange(event) {
    loading = true;
    requestType = event.target.value;
    // Mostrar campos adicionales solo si requestType no es 'Other'
    showAdditionalFields = requestType !== "other";

    setTimeout(() => {
      loading = false;
    }, 400); // Adjust the delay as needed
  }

  // Inicializar el estado del formulario
  onMount(() => {
    showAdditionalFields = requestType !== "other";
  });
</script>

<form>
  <div class="space-y-12">
    <div class=" border-gray-900/10 pb-12">
      <h2 class="text-xl font-semibold leading-7 text-gray-900">
        Submit a Request
      </h2>

      <div class="mt-10 grid grid-cols-1 gap-x-6 gap-y-8 sm:grid-cols-6">
        <div class="sm:col-span-12">
          <Label>
            Please choose a request type below
            <Select
              class="mt-2"
              items={request}
              bind:value={selected}
              on:change={handleRequestTypeChange}
            />
          </Label>
        </div>

        {#if loading}
          <div class="sm:col-span-12 flex justify-center">
            <img
              class="animate-spin w-[100px]"
              src="poke-boll.png"
              alt="Loading"
            />
          </div>
        {:else}
          {#if requestType == "orders"}
            <Orders />
          {/if}

          {#if requestType == "returns"}
            <Returns />
          {/if}

          {#if requestType == "billing"}
            <Billing />
          {/if}

          {#if requestType == "preorders"}
            <Preorders />
          {/if}

          {#if requestType == "merchandise"}
            <Merchandise />
          {/if}

          {#if requestType == "technical"}
            <Technical />
          {/if}

          {#if requestType == "other"}
            <Other />
          {/if}
        {/if}
      </div>
    </div>
  </div>

  <div class="mt-2 flex items-center justify-start gap-x-6">
    <button
      type="submit"
      class="rounded-md bg-gray-700 px-10 py-2 text-sm font-semibold text-white shadow-sm hover:bg-gray-900 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-gray-600"
      >Submit</button
    >
  </div>
</form>
