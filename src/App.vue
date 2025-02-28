<script setup>
import { ref, onMounted } from "vue";

const isPulsing = ref(false);

const isToggled = ref(true);

onMounted(() => {
  setTimeout(() => {
    isPulsing.value = true;
  }, 4000);
});
</script>

<template>
  <div
    id="app"
    class="relative flex items-center justify-center overflow-hidden h-screen bg-cover bg-center]"
    :class="{
      'bg-[url(/images/mountains.jpg)]': isToggled,
      'bg-none': !isToggled,
    }"
  >
    <div class="absolute top-4 left-4 text-white rounded-lg">
      <label class="inline-flex items-center cursor-pointer">
        <input
          type="checkbox"
          value=""
          class="sr-only peer"
          @click="isToggled = !isToggled"
          checked
        />
        <div
          class="relative w-12 h-6 bg-gray-200 rounded-full peer peer-checked:after:translate-x-full after:absolute after:top-[2px] after:start-[2px] after:bg-white after:border-gray-300 after:border after:rounded-full after:h-5 after:w-5 after:transition-all peer-checked:bg-blue-600"
        ></div>
      </label>
    </div>

    <img
      src="/images/water.png"
      alt="water-bottle"
      class="mt-8 ml-0 md:mr-8 hidden md:block md:max-h-[75vh] w-auto object-contain"
      :class="{
        'animate-slideUp': !isPulsing,
        'animate-pulseBottle': isPulsing,
      }"
    />

    <div class="flex flex-col">
      <div class="mt-0 md:-mt-8 flex flex-col md:justify-center md:flex-row">
        <div class="animate-slideDown mb-2 mt-8 lg:mb-8 flex flex-col gap-4">
          <h1 class="text-center text-5xl md:text-6xl lg:text-7xl font-amulya">
            VOLSTROM
          </h1>
          <p class="text-center text-2xl lg:text-4xl font-synonym">
            Designer Water
          </p>
        </div>
      </div>
      <div
        class="animate-slideUp max-w-[90vw] md:max-w-[60vw] lg:max-w-[50vw] xl:max-w-[40vw] bg-white/75 p-12 rounded-lg shadow-lg flex flex-col justify-center items-center"
      >
        <h2 class="text-xl md:text-xl lg:text-3xl font-amulya text-center mb-4">
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
          class="rounded-md text-lg z-10 cursor-pointer bg-black text-white py-2 px-6 transition-colors hover:scale-110 transition-transform duration-200 ease-in"
        >
          GET YOURS NOW
        </button>
      </div>
    </div>
    <div class="pointer-events-none absolute -bottom-2 w-full overflow-hidden">
      <div class="flex">
        <img
          src="/images/fog1.png"
          alt="Description"
          class="opacity-0 w-auto max-h-[30vh] object-cover"
          :class="{
            hidden: !isPulsing,
            'animate-fogMove': isPulsing,
          }"
          style="animation-delay: 0s"
        />
        <img
          src="/images/fog4.png"
          alt="Description"
          class="opacity-0 w-auto max-h-[30vh] object-cover"
          :class="{
            hidden: !isPulsing,
            'animate-fogMove': isPulsing,
          }"
          style="animation-delay: 1s"
        />
        <img
          src="/images/fog1.png"
          alt="Description"
          class="opacity-0 w-auto max-h-[30vh] object-cover"
          style="animation-delay: 2s"
          :class="{
            hidden: !isPulsing,
            'animate-fogMove': isPulsing,
          }"
        />
        <img
          src="/images/fog5.png"
          alt="Description"
          class="opacity-0 w-auto max-h-[30vh] object-cover"
          style="animation-delay: 3s"
          :class="{
            hidden: !isPulsing,
            'animate-fogMove': isPulsing,
          }"
        />
        <img
          src="/images/fog4.png"
          alt="Description"
          class="opacity-0 w-auto max-h-[30vh] object-cover"
          style="animation-delay: 4s"
          :class="{
            hidden: !isPulsing,
            'animate-fogMove': isPulsing,
          }"
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
  40%,
  60% {
    opacity: 1;
  }
  100% {
    transform: scale(1.6);
    opacity: 0;
  }
}

.animate-fogMove {
  animation: fogMove 6s linear infinite;
}
</style>
