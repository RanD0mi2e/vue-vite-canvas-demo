<template>
  <div></div>
</template>

<script setup lang="ts">
import { ref, reactive, onMounted } from "vue";

const logos = reactive([
  { label: "kazimierz", url: "/src/assets/logo_kazimierz.png" },
  { label: "rhine", url: "/src/assets/logo_rhine.png" },
  { label: "rhodes", url: "/src/assets/logo_rhodes.png" },
  { label: "victoria", url: "/src/assets/logo_victoria.png" },
  { label: "yan", url: "/src/assets/logo_yan.png" },
]);

interface CanvasConfig {
  canvasWidth: number
  canvasHeight: number
}

class Partical {
  x: number // 粒子x轴初始位置
  y: number // 粒子y轴初始位置
  totalX: number // 粒子x轴目标位置
  totalY: number // 粒子y轴目标位置
  mx?: number // 粒子x轴需要移动距离
  my?: number // 粒子y轴需要移动距离
  vx?: number // 粒子x轴移动速度
  vy?: number // 粒子y轴移动速度
  time: number // 粒子移动耗时
  r: number // 粒子半径
  color: number[] // 粒子颜色
  opacity: number // 粒子透明度

  constructor(totalX: number, totalY: number, time: number, color: number[], canvasConfig: CanvasConfig) {
    // 设置粒子初始位置、目标位置和耗时
    this.x = (Math.random() * canvasConfig.canvasWidth) >> 0
    this.y = (Math.random() * canvasConfig.canvasHeight) >> 0
    this.totalX = totalX
    this.totalY = totalY
    this.time = time
  }
}
</script>

<style scoped></style>
