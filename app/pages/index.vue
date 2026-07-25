<script setup lang="ts">
import { usePageSeo } from '~/data/site'

usePageSeo(
  { zh: 'PCBA 制造与成品组装企业', en: 'PCBA Manufacturing & Finished Product Assembly Provider' },
  { zh: '壹原理科技围绕键鼠控制板、相机遥控器、充电宝模块与定制 PCBA，提供 PCBA 加工、成品组装、测试验证与量产交付支持。', en: 'YiYuanLi supports keyboard/mouse control boards, camera remotes, power bank modules and custom PCBA with manufacturing, testing and batch delivery.' }
)
</script>

<template>
  <HomeHero />
  <HomeCapabilityStats />
  <HomeAbout />
  <HomeProductTiles />
  <HomeFootprint />
  <HomeSupport />
</template>
