<script setup></script>

<template>
  <div
    id="app"
    class="overflow-hidden h-screen bg-[url('images/mountains.jpg')] bg-cover bg-center"
  >
    <div class="flex flex-col md:flex-row">
      <div class="mt-6 md:ml-6 flex flex-col gap-4">
        <h1 class="text-center text-5xl md:text-6xl font-amulya">VOLSTROM</h1>
        <p class="text-center md:text-left text-4xl font-synonym">
          Designer Water
        </p>
      </div>
    </div>

    <div class="justify-center flex md:justify-start mt-8">
      <img
        src="/images/water.png"
        alt="water-bottle"
        class="ml-4 md:ml-16 max-h-[75vh] w-auto object-contain"
      />
      <div
        class="self-center ml-8 max-w-[30vw] bg-white/75 p-12 rounded-lg shadow-lg flex flex-col justify-center items-center"
      >
        <h2 class="text-xl md:text-3xl font-amulya text-center mb-4">
          DISCOVER THE PUREST WATER
        </h2>
        <p class="text-center mb-6 text-lg font-synonym">
          VOLSTROM offers the ultimate hydration experience. Refresh your body
          with the finest quality water.
        </p>

        <p class="text-center mb-6 text-lg font-synonym">
          Our water is not available in regular stores, ensuring exclusivity and
          offering you a luxurious experience with every sip.
        </p>

        <p class="text-center mb-6 text-lg font-synonym">
          With VOLSTROM, you’re not just drinking water – you’re indulging in a
          premium, high-quality product that stands out in both taste and
          design.
        </p>
        <button
          class="bg-black text-white py-2 px-6 transition-colors hover:scale-110 transition-transform duration-200 ease-in"
        >
          GET YOURS NOW
        </button>
      </div>
    </div>
  </div>
</template>

<style scoped></style>
