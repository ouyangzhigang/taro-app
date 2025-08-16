<template>
  <View class="popup-component" :style="{height}">
    <Text>{{ title }}</Text>
    <View>
      <Image src="https://ke.successkaoyan.com/static/img/wxgzh.7160412d.png"></Image>
    </View>
    <View>
      <Input type="text" placeholder="将会获取焦点" :focus="true" :value="message" @input="inputMsg" />
    </View>
  </View>
</template>

<script setup lang="ts">
import {ref, computed} from 'vue'
import {View, Text, Image, Input} from '@tarojs/components'

const props = defineProps<{
  title: string;
  height?: number;
}>()

const message = ref('')

const title = computed(() => props.title)
const height = computed(() => props.height)

const inputMsg = (e) => {
  console.log(e.target)
  message.value = e.target.value
}
</script>


<style lang="scss" scoped>
.popup-component {
  position: fixed;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 75%;
  border-radius: 15rpx 15px 0 0;
  background-color: blue;
  display: flex;
  justify-content: flex-start;
  align-items: center;
  flex-direction: column;
  z-index: 9;
}
</style>