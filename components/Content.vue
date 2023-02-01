<script setup>

const state = reactive({
  tabs: [
    {name: 'Рассылки', tab: 'newsletters'},
    {name: 'Соцсети', tab: 'socialNetwork'},
    {name: 'Мессенджеры', tab: 'messengers'},
  ],
  currentVersion: 'newsletters'
})

// const currentVersion = ref('v1')
  const setVersion = (v) => {
    state.currentVersion = v
  }
</script>

<template>
  <div class="flex flex-col mt-[24px] w-full items-center">
    <div class="flex flex-row gap-[24px] justify-center">
      <span
        v-for="tab in state.tabs"
        @click="setVersion(tab.tab)"
        class="cursor-pointer"
        :class="[ state.currentVersion === tab.tab ? 'tab-active' : 'tab' ]"
      >
        {{ tab.name }}
      </span>
    </div>
    <div class="flex flex-col bg-[#F5F5F8] w-full max-w-[1024px] py-[32px] px-[16px] items-center lg:rounded-[16px] lg:py-[48px] lg:px-[24px]">
      <Newsletters v-if="state.currentVersion === 'newsletters'"/>
    </div>
    <img src="/images/smile.png" class="mt-[48px]" alt="">
  </div>
</template>

<style scoped>
.tab {
  color: #666666;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
}

.tab-active {
  color: #5A8CF1;
  font-weight: 500;
  font-size: 16px;
  line-height: 24px;
  border-bottom: 2px solid #5A8CF1;
  padding-bottom: 16px;
}
</style>
