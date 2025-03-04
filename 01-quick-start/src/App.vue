<script setup>
import { onMounted } from 'vue';
import {TOKEN} from '@/constant/data.js'
import * as Cesium from 'cesium'
onMounted(() => {
  Cesium.Ion.defaultAccessToken = TOKEN
  const viewer = new Cesium.Viewer('map', {
    geocoder:true,  // 是否显示位置查找工具
    homeButton:true, // 是否显示首页位置工具
    sceneModePicker:true, // 是否显示视角模式切换工具
    baseLayerPicker:true, // 是否显示默认图层选择工具
    navigationHelpButton:true, // 是否显示导航帮助工具
    animation:true, // 是否显示动画工具
    timeline:true, // 是否显示时间轴工具
    fullscreenButton:true, // 是否显示全屏按钮工具
    infoBox:false, // 是否显示信息框
  })
})
</script>

<template>
<div id="map"></div>
</template>

<style scoped>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#map {
  width: 100%;
  height: 100vh;
}
</style>
