<template>

    <HelloWorld ></HelloWorld>

</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import Flexable from '../assets/flexable.min.js'
export default {
  name: 'home',
  components: {
    HelloWorld
  }
}
</script>
