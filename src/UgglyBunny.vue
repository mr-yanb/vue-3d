<script setup>
import { ref } from 'vue'
import { useLoader } from '@tresjs/core'
import { GLTFLoader } from 'three/addons/loaders/GLTFLoader'
import { useAnimations, useGLTF, useFBX } from '@tresjs/cientos'

// const { scene: model, animations } = await useGLTF('https://raw.githubusercontent.com/Tresjs/assets/main/models/gltf/ugly-naked-bunny/ugly-naked-bunny-animated.gltf')
// const model = await useFBX('./models/test3.fbx')
const { scene } = await useGLTF('https://raw.githubusercontent.com/mr-yanb/vue-3d/main/src/models/test2.glb', { draco: true })
// const { actions } = useAnimations(animations, model)

// const currentAction = ref(actions.Greeting)

// currentAction.value.play()
console.log(scene)

</script>

<template>
  <!-- <primitive :object="model" /> -->
  <primitive :object="scene" />
</template>