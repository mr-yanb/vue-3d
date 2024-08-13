<script setup>
import { TresCanvas } from "@tresjs/core";
import { OrbitControls, GLTFModel } from "@tresjs/cientos";
import { BasicShadowMap, SRGBColorSpace, NoToneMapping } from "three";

import UgglyBunny from "./UgglyBunny.vue";

const gl = {
  clearColor: "#F78B3D",
  shadows: true,
  alpha: false,
  shadowMapType: BasicShadowMap,
  outputColorSpace: SRGBColorSpace,
  toneMapping: NoToneMapping,
  windowSize: true,
};
</script>
<template>
  <TresCanvas clear-color="#000000">
    <TresPerspectiveCamera :position="[5, 5, 5]" />
    <OrbitControls />
    <Suspense>
      <!-- <UgglyBunny /> -->
      <!-- <FBXModel
        path="https://raw.githubusercontent.com/Tresjs/assets/main/models/fbx/low-poly-truck/Jeep_done.fbx"
        :scale="0.025"
      /> -->
      <GLTFModel path="https://raw.githubusercontent.com/Tresjs/assets/main/models/gltf/venom-snake-sculpt/scene.gltf" draco />
    </Suspense>
    <TresDirectionalLight
      color="#FFFFFF"
      :position="[10, 10, 10]"
      :look-at="[0, 0, 0]"
      :intensity="5"
    />
    <TresAmbientLight :intensity="5" />
    <!-- <TresGridHelper /> -->
  </TresCanvas>
</template>

<style>
html,
body {
  margin: 0;
  padding: 0;
  height: 100%;
  width: 100%;
}
#app {
  height: 100%;
  width: 100%;
}
</style>
