<template>
  <div class="about">
    <h1>This is an about page</h1>
    <div>
      <div v-for="(v, i) in abc" :key="i">
        {{ v }}
      </div>
    </div>
  </div>
</template>
<script>
import {ref, onMounted, reactive, isReactive} from 'vue'
export default {
  setup() {
    const adv = ref('')
    const abc = reactive({})
    const fuck = async () => {
      let i = 0
      await setInterval(() => {
        abc['a' + i] = '胡也行' + i
        i++
        // console.log(abc)
        console.log(isReactive(abc))
      }, 1000)
    }
    onMounted(() => {
      fuck()
    })
    return {
      fuck,
      adv,
      abc
    }
  }
}
</script>
