<script setup>
  import { useWindowSize } from '@vueuse/core'
  const { width, height } = useWindowSize()

  const showButton = computed(() => {
  if (width.value < 1024) {
    return '>';
  } else {
    return 'Подписаться';
  }
})

  const cards = [
    { 
      title: 'Перед рассветом' , 
      subTitle: 'Утренний бухгалтер', 
      description: 'Самые важные новости и события за день. Кратко, по делу, структурировано.', 
      advantages: [
        'Новости для бухгалтеров, ИП и директора',
        'Подборка статей за день',
      ],
      people: 'Уже получает 59 342',
      img: '/images/card1.png'
    },
    { 
      title: 'После заката' , 
      subTitle: 'Ночной бухгалтер', 
      description: 'Самая краткая газета о налогах и бухучете в мире — современная рассылка для чтения.', 
      advantages: [
        'Анализ, оценка и только самое главное',
        'Лучшие комменты юзеров в обзоре',
      ],
      people: 'Уже получает 37 480 человек',
      img: '/images/card2.png'
    },
    { 
      title: 'Раз в две недели' , 
      subTitle: 'Ножницы скидок', 
      description: 'Подборка самых выгодных и полезных спецпредложений от надежных компаний.', 
      advantages: [
        'Акции и скидки от лидеров рынка',
        'Те, кто подписался – экономят много денег ',
      ],
      people: 'Уже получает 92 118 человек',
      img: '/images/card3.png'
    },
    { 
      title: 'По мере появления анонсов' , 
      subTitle: 'Чемодан вебинаров', 
      description: 'Подборка с анонсами бесплатных вебинаров на самые топовые темы при участии экспертов.', 
      advantages: [
        'Никогда не пришлем платные вебинары',
        'Подборка топовых тем для вебинаров',
      ],
      people: 'Уже получает 92 082 человек',
      img: '/images/card4.png'
    },
  ]
</script>

<template>
  <div class="flex flex-col w-full items-center">
    <h1 class="font-[500] text-black text-[24px] leading-[32px]">Выберите рассылки, которые подходят именно вам</h1>
    <div class="flex flex-col mt-[24px]  w-full items-start">
      <div class="flex flex-row w-full relative lg:px-[24px]">
        <input
          class="w-full py-[16px] pl-[16px] text-[16px] color-black" 
          type="emal"
          placeholder="Электронная почта"
        >
        <BaseButton class="right-0 absolute lg:right-[24px]">
          {{showButton}}
        </BaseButton>
      </div>
      <div class="flex flex-row mt-[16px] gap-[8px] items-center lg:px-[24px]">
        <Toggle/>
        <span class="font-[400] text-black text-[14px]">Подписаться на все рассылки</span>
      </div>
    </div>
    <div class="flex flex-row flex-wrap mt-[24px] w-full gap-[24px] lg:mt-[32px]">
      <Card
        v-for="card in cards"
        :card="card"
      />
    </div>
  </div>
</template>

<style scoped>
input {
  border-radius: 16px 100px 100px 16px;
}

</style>
