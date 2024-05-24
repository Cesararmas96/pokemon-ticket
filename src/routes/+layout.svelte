<script lang="ts">
    import Footer from '$lib/components/Footer.svelte'
    import Header from '$lib/components/Header.svelte'
    import "../app.css";
    import "../main.css";

    let isPageLoaded = false;
    const pageLoaded = () => {
      isPageLoaded = true
    }
  </script>

{#if !isPageLoaded}
<div    use:pageLoaded class="z-10 flex h-screen w-screen items-center justify-center overflow-hidden">
  <div class="sm:col-span-12 flex justify-center">
    <img
      class="animate-spin w-[100px]"
      src="poke-boll.png"
      alt="Loading"
    />
  </div>
</div>
  
{:else}
<Header/>
<section class="section m-5 p-8  bg-white rounded-xl">

  <slot />


  
  
</section>
<Footer/>
{/if} 