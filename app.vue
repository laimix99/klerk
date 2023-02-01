<script setup>
  const state = reactive({
    links: [
      'Главная', 
      'Рассылки', 
      'Хлебные крошки',
    ]
  })
</script>

<template>
  <div class="flex flex-col w-full py-[24px] items-center lg:py-[48px]">
    <img src="/images/logo.png" alt="">
    <div class="flex flex-row mt-[28px] gap-[8px] lg:mt-[24px]">
      <div 
        v-for="(link, index) in state.links" 
        :key="link.id"
        class="flex flex-row gap-[8px] items-center"
      >
      <span class="text-[13px] text-[#999999] link">
          {{ link }}
      </span>
      <svg v-if="index < state.links.length - 1" width="9" height="4" viewBox="0 0 9 4" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M6.827 3.575C6.957 3.29767 7.08267 3.055 7.204 2.847C7.334 2.639 7.45967 2.46567 7.581 2.327H0.00200018V1.781H7.581C7.45967 1.63367 7.334 1.456 7.204 1.248C7.08267 1.04 6.957 0.801666 6.827 0.533H7.282C7.828 1.16567 8.4 1.63367 8.998 1.937V2.171C8.4 2.46567 7.828 2.93367 7.282 3.575H6.827Z" fill="#999999"/>
      </svg>
      </div>
    </div>
    <h1 class="font-[500] text-[32px] leading-[72px] color-black lg:text-[56px]">Подписки «Клерка»</h1>
    <Content/>
  </div>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;700&display=swap');
span{
  font-family: 'Roboto', sans-serif;
}

p {
  font-family: 'Roboto', sans-serif;
}

h1 {
  font-family: 'Roboto', sans-serif;
}

:root {
  --color-blue:#316FEE;
}
  .br {
    outline: 1px solid red;
  }
  .bg {
    outline: 1px solid green;
    text-decoration: underline;
  }

  .link {
    border-bottom: 1px solid #E6EDFF;
    /* background-color: ; */
  }

/* .link::after {
  content: '';
  display: block;
  width: 13px;
  height: 5px;
  background: url('/images/next.png') transparent no-repeat;
}

.link:last-child::after {
  display: none;
} */
</style>
