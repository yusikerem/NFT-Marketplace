<template>
  <div>
    <div class="my-container">
      <custom-header-and-text-lg class="mb-8">
        <template #header> Browse Marketplace </template>
        <template #text>
          Browse through more than 50k NFTs on the NFT Marketplace.
        </template>
      </custom-header-and-text-lg>
      <div
        class="w-full bg-primary flex justify-between border-secondary rounded-base py-[18px] px-5 border-[1px]"
      >
        <input
          placeholder="Search your favorite NFTs"
          class="bg-primary placeholder:text-primary text-primary"
          type="text"
        />
        <img
          width="20"
          height="20"
          src="../assets/mini-icons/MagnifyingGlass.svg"
          alt=""
        />
      </div>
    </div>
    <hr class="text-[#3B3B3B] h-[1px]" />
    <div class="my-container py-0 pt-6">
      <div>
        <div class="flex w-full justify-evenly mb-1">
          <div class="lg:text-lg font-semibold w-1/2 flex justify-center">
            <div class="flex items-center gap-x-4 mb-4">
              NFTs
              <div
                class="hidden md:flex px-2.5 py-1 rounded-base bg-[#858584] font-mono items-center text-base"
              >
                302
              </div>
            </div>
          </div>

          <div
            class="lg:text-lg text-primary font-semibold items-center gap-x-4 w-1/2 flex justify-center mb-4"
          >
            Collections
            <div
              class="hidden md:flex p-2 rounded-base bg-secondary text-white font-mono items-center text-base"
            >
              302
            </div>
          </div>
        </div>
        <hr class="w-1/2 text-primary h-0.5" />
      </div>
    </div>
    <div class="bg-secondary">
      <div class="my-container py-[60px]">
        <div
          class="grid lg:grid-cols-3 md:grid-cols-2 grid-cols-1 gap-y-[30px]"
        >
          <DiscoverCard
            v-for="(card, i) in discoverCards"
            :index="i"
            :class="
              handleResponsivity(
                {
                  sm: 4,
                  md: 8,
                  lg: -1,
                },
                'block',
                discoverCards.length,
                i
              )
            "
            :card="card"
          >
            <!-- :class="[
              discoverCards.length - 1 - i < 4
                ? 'lg:block hidden'
                : i > 3 && i < 7
                ? 'hidden md:block'
                : '',
            ]" -->
          </DiscoverCard>
        </div>
      </div>
      <hr class="text-secondary border-[1px]" />
    </div>
  </div>
</template>
<script setup>
import img1 from "../assets/discover-images/Image Placeholder.svg";
import img2 from "../assets/discover-images/Image Placeholder-1.svg";
import img3 from "../assets/discover-images/Image Placeholder-2.svg";
import avatar1 from "../assets/avatar-icons/avatar1.svg";
import avatar2 from "../assets/avatar-icons/avatar2.svg";
import avatar3 from "../assets/avatar-icons/avatar3.svg";
import handleResponsivity from "../utils/responsive";
const discoverCards = [
  {
    img: img1,
    header: "Distant Galaxy",
    userAvatar: avatar1,
    userName: "MoonDancer",
    price1: 1.63,
    price2: 0.33,
    class: "bg-primary",
  },
  {
    img: img2,
    header: "Distant Galaxy",
    userAvatar: avatar2,
    userName: "MoonDancer",
    price1: 1.63,
    price2: 0.33,
    class: "bg-primary",
  },
  {
    img: img3,
    header: "Distant Galaxy",
    userAvatar: avatar3,
    userName: "MoonDancer",
    price1: 1.63,
    price2: 0.33,
    class: "bg-primary",
  },
  {
    img: img1,
    header: "Distant Galaxy",
    userAvatar: avatar1,
    userName: "MoonDancer",
    price1: 1.63,
    price2: 0.33,
    class: "bg-primary",
  },
  {
    img: img2,
    header: "Distant Galaxy",
    userAvatar: avatar2,
    userName: "MoonDancer",
    price1: 1.63,
    price2: 0.33,
    class: "bg-primary",
  },
  {
    img: img3,
    header: "Distant Galaxy",
    userAvatar: avatar3,
    userName: "MoonDancer",
    price1: 1.63,
    price2: 0.33,
    class: "bg-primary",
  },
  {
    img: img1,
    header: "Distant Galaxy",
    userAvatar: avatar1,
    userName: "MoonDancer",
    price1: 1.63,
    price2: 0.33,
    class: "bg-primary",
  },
  {
    img: img2,
    header: "Distant Galaxy",
    userAvatar: avatar2,
    userName: "MoonDancer",
    price1: 1.63,
    price2: 0.33,
    class: "bg-primary",
  },
  {
    img: img3,
    header: "Distant Galaxy",
    userAvatar: avatar3,
    userName: "MoonDancer",
    price1: 1.63,
    price2: 0.33,
    class: "bg-primary",
  },
  {
    img: img1,
    header: "Distant Galaxy",
    userAvatar: avatar1,
    userName: "MoonDancer",
    price1: 1.63,
    price2: 0.33,
    class: "bg-primary",
  },
  {
    img: img2,
    header: "Distant Galaxy",
    userAvatar: avatar2,
    userName: "MoonDancer",
    price1: 1.63,
    price2: 0.33,
    class: "bg-primary",
  },
  {
    img: img3,
    header: "Distant Galaxy",
    userAvatar: avatar3,
    userName: "MoonDancer",
    price1: 1.63,
    price2: 0.33,
    class: "bg-primary",
  },
];

// function handleResponsivityTest(sizes, displayClass, length, index) {
//   return index > sizes.md - 1
//     ? `lg:${displayClass} hidden`
//     : index <= length - sizes.sm - 1 && index > length - sizes.md - 1
//     ? `md:${displayClass} hidden`
//     : "";
// }

// let width;
// onMounted(() => {
//   window.addEventListener("resize", () => {
//     width.value = document.documentElement.clientWidth;
//   });
// });

// onBeforeUnmount(() => {
//   window.removeEventListener("resize", () => {
//     width.value = document.documentElement.clientWidth;
//   });
// });
// const handleResponsivity = computed(() => {
//   // Computed logic here
//   if (process.client) {
//     width = ref(document.documentElement.clientWidth);

//     if (width.value > 1280) {
//       return discoverCards;
//     } else if (830 < width.value && width.value < 1280) {
//       return discoverCards.slice(0, 8);
//     } else if (830 > width.value) {
//       return discoverCards.slice(0, 5);
//     }
//   } else {
//     return 0;
//   }
// });
</script>
