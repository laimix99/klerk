<script setup>
const props = defineProps({
  card: {
    type: Object,
    default: () => {}
  }
})
</script>

<template>
  <div 
    class="bg-white flex flex-row rounded-[16px] w-full max-w-[476px] p-[24px] relative justify-between items-start card" 
    lg=""
  >
    <div class="flex flex-col w-full items-start lg:max-w-[310px]">
      <h1 class="font-[400] text-[13px] text-[#999999]">{{ card.title }}</h1>
      <span class="font-[500] text-black text-[20px]">{{ card.subTitle }}</span>
      <p class="font-[400] mt-[8px] text-[14px] text-[#666666]">{{ card.description }}</p>
      <div 
        class="flex flex-col mt-[16px] items-start"
      >
        <div 
          v-for="advantage in card.advantages"
          class="flex flex-row gap-[8px] items-center"
        >
          <BaseSvg/>
          <span 
            class="font-[400] text-black text-[14px]"
          >
            {{ advantage }}
          </span>
        </div>
      </div>
      <div class="flex flex-row mt-[16px] gap-[8px] items-center">
        <Toggle/>
        <p class="font-[400] text-black text-[14px]">{{ card.people }}</p>
      </div>
    </div>
    <img class="w-full max-w-[40px] top-[24px] right-[16px] absolute lg:max-w-[80px] lg:relative" :src="card.img" alt="">
  </div>
</template>

<style scoped>
.card {
  box-shadow: 0px 8px 16px rgba(0, 0, 0, 0.08);
}
</style>
