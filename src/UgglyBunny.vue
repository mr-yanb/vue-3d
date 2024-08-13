<script setup>
import { ref } from 'vue'
import { useLoader } from '@tresjs/core'
import { GLTFLoader } from 'three/addons/loaders/GLTFLoader'
import { useAnimations, useGLTF, useFBX } from '@tresjs/cientos'

// const { scene: model, animations } = await useGLTF('https://raw.githubusercontent.com/Tresjs/assets/main/models/gltf/ugly-naked-bunny/ugly-naked-bunny-animated.gltf')
const model = await useFBX('./models/test3.fbx')

// const { actions } = useAnimations(animations, model)

// const currentAction = ref(actions.Greeting)

// currentAction.value.play()
console.log(model)

</script>

<template>
  <!-- <primitive :object="model" /> -->
  <primitive :object="model" />
</template>