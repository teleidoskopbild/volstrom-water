<script setup>
import { ref, onMounted } from "vue";

const isPulsing = ref(false);

onMounted(() => {
  setTimeout(() => {
    isPulsing.value = true;
  }, 4000);
});
</script>

<template>
  <div
    id="app"
    class="relative flex items-center justify-center overflow-hidden h-screen bg-[url('images/mountains.jpg')] bg-cover bg-center"
  >
    <img
      src="/images/water.png"
      alt="water-bottle"
      class="mt-8 ml-0 md:ml-10 max-h-[75vh] w-auto object-contain"
      :class="{
        'animate-slideUp': !isPulsing,
        'animate-pulseBottle': isPulsing,
      }"
    />

    <div class="ml-6 flex flex-col">
      <div class="-mt-16 flex flex-col md:justify-center md:flex-row">
        <div class="animate-slideDown mb-8 mt-8 md:ml-6 flex flex-col gap-4">
          <h1 class="text-center text-5xl md:text-6xl lg:text-7xl font-amulya">
            VOLSTROM
          </h1>
          <p class="text-center text-4xl lg:text-5xl font-synonym">
            Designer Water
          </p>
        </div>
      </div>
      <div
        class="animate-slideUp ml-8 max-w-[50vw] lg:max-w-[40vw] bg-white/75 p-12 rounded-lg shadow-lg flex flex-col justify-center items-center"
      >
        <h2 class="text-xl md:text-3xl font-amulya text-center mb-4">
          DISCOVER THE PUREST WATER
        </h2>
        <p class="text-center mb-6 text-sm md:text-lg font-synonym">
          VOLSTROM offers the ultimate hydration experience. Refresh your body
          with the finest quality water.
        </p>

        <p class="text-center mb-6 text-sm md:text-lg font-synonym">
          Our water is not available in regular stores, ensuring exclusivity and
          offering you a luxurious experience with every sip.
        </p>

        <p class="text-center mb-6 text-sm md:text-lg font-synonym">
          With VOLSTROM, you’re not just drinking water – you’re indulging in a
          premium, high-quality product that stands out in both taste and
          design.
        </p>
        <button
          class="z-10 cursor-pointer bg-black text-white py-2 px-6 transition-colors hover:scale-110 transition-transform duration-200 ease-in"
        >
          GET YOURS NOW
        </button>
      </div>
    </div>
    <div
      class="z-0 pointer-events-none absolute -bottom-2 w-full overflow-hidden"
    >
      <div class="flex">
        <img
          src="/images/fog1.png"
          alt="Description"
          class="animate-fogMove w-auto max-h-[30vh] object-cover"
        />
        <!-- <img
          src="/images/fog2.png"
          alt="Description"
          class="w-auto max-h-[30vh] object-cover"
        /> -->
        <img
          src="/images/fog3.png"
          alt="Description"
          class="animate-fogMove w-auto max-h-[30vh] object-cover"
          style="animation-delay: 0s"
        />
        <img
          src="/images/fog4.png"
          alt="Description"
          class="animate-fogMove w-auto max-h-[30vh] object-cover"
          style="animation-delay: 1s"
        />
        <img
          src="/images/fog5.png"
          alt="Description"
          class="animate-fogMove w-auto max-h-[30vh] object-cover"
          style="animation-delay: 2s"
        />
        <img
          src="/images/fog4.png"
          alt="Description"
          class="animate-fogMove w-auto max-h-[30vh] object-cover"
          style="animation-delay: 3s"
        />
      </div>
    </div>
  </div>
</template>

<style scoped>
@keyframes pulseBottle {
  0%,
  100% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.05);
  }
}

.animate-pulseBottle {
  animation: pulseBottle 3s ease-in-out infinite;
}

@keyframes slideUp {
  0% {
    transform: translateY(200px);
    opacity: 0;
  }
  100% {
    transform: translateY(0);
    opacity: 1;
  }
}

.animate-slideUp {
  animation: slideUp 4s ease-out forwards;
}

@keyframes slideDown {
  0% {
    transform: translateY(-200px);
    opacity: 0;
  }
  100% {
    transform: translateY(0);
    opacity: 1;
  }
}

.animate-slideDown {
  animation: slideDown 4s ease-out forwards;
}

@keyframes fogMove {
  0% {
    opacity: 0;
    transform: scale(1);
  }
  20%,
  80% {
    opacity: 1;
  }
  100% {
    transform: scale(2);
    opacity: 0;
  }
}

.animate-fogMove {
  animation: fogMove 10s linear infinite;
}
</style>
