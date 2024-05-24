<script>
  import { Select, Label } from "flowbite-svelte";
  let countries = [
    { value: "usa", name: "USA" },
    { value: "canada", name: "Canada" },
    { value: "uk", name: "UK" },
    { value: "nolisted", name: "No Listed" },
  ];
</script>

<div class="sm:col-span-12">
  <div class="flex">
    <label for="email" class="block text-sm font-medium leading-6 text-gray-900"
      >You Email address</label
    ><span class="ml-2 text-red-600">*</span>
  </div>
  <div class="">
    <input
      id="email"
      name="email"
      type="email"
      autocomplete="email"
      class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
    />
  </div>
</div>

<div class="sm:col-span-12">
  <div class="flex">
    <label
      for="first-name"
      class="block text-sm font-medium leading-6 text-gray-900"
      >First name and last name</label
    >
    <span class="ml-2 text-red-600">*</span>
  </div>
  <div class="">
    <input
      type="text"
      name="first-name"
      id="first-name"
      class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
    />
  </div>
</div>
<div class="sm:col-span-12">
  <Label>
    Country
    <span class="ml-2 text-red-600">*</span>
    <Select class="mt-2" items={countries} />
  </Label>
</div>

<div class="sm:col-span-12">
  <div class="flex">
    <label
      for="first-name"
      class="block text-sm font-medium leading-6 text-gray-900">Subject</label
    >
    <span class="ml-2 text-red-600">*</span>
  </div>

  <div class="">
    <input
      type="text"
      name="first-name"
      id="first-name"
      class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
    />
  </div>
</div>

<div class="sm:col-span-12">
  <div class="flex">
    <label for="about" class="block text-sm font-medium leading-6 text-gray-900"
      >Description</label
    >
    <span class="ml-2 text-red-600">*</span>
  </div>

  <div class="">
    <textarea
      id="about"
      name="about"
      rows="3"
      class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
    ></textarea>
  </div>
  <p class="mt-3 text-sm leading-6 text-gray-600">
    Please enter the details of your request. A member of our support staff will
    respond as soon as possible.
  </p>
</div>


<div class="sm:col-span-12">
  <label
    for="cover-photo"
    class="block text-sm font-medium leading-6 text-gray-900">Attachments</label
  >
  <div
    class=" flex justify-center rounded-lg border border-dashed border-gray-900/25 px-6 py-10"
  >
    <div class="text-center">
      <svg
        class="mx-auto h-12 w-12 text-gray-300"
        viewBox="0 0 24 24"
        fill="currentColor"
        aria-hidden="true"
      >
        <path
          fill-rule="evenodd"
          d="M1.5 6a2.25 2.25 0 012.25-2.25h16.5A2.25 2.25 0 0122.5 6v12a2.25 2.25 0 01-2.25 2.25H3.75A2.25 2.25 0 011.5 18V6zM3 16.06V18c0 .414.336.75.75.75h16.5A.75.75 0 0021 18v-1.94l-2.69-2.689a1.5 1.5 0 00-2.12 0l-.88.879.97.97a.75.75 0 11-1.06 1.06l-5.16-5.159a1.5 1.5 0 00-2.12 0L3 16.061zm10.125-7.81a1.125 1.125 0 112.25 0 1.125 1.125 0 01-2.25 0z"
          clip-rule="evenodd"
        />
      </svg>
      <div class="mt-4 flex text-sm leading-6 text-gray-600">
        <label
          for="file-upload"
          class="relative cursor-pointer rounded-md bg-white font-semibold text-indigo-600 focus-within:outline-none focus-within:ring-2 focus-within:ring-indigo-600 focus-within:ring-offset-2 hover:text-indigo-500"
        >
          <span>Upload a file</span>
          <input
            id="file-upload"
            name="file-upload"
            type="file"
            class="sr-only"
          />
        </label>
        <p class="pl-1">or drag and drop</p>
      </div>
      <p class="text-xs leading-5 text-gray-600">PNG, JPG, GIF up to 10MB</p>
    </div>
  </div>
</div>
