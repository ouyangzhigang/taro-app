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

<style>
.popup-component{background-color:blue;border-radius:15rpx 15px 0 0;bottom:0;display:-webkit-box;display:-webkit-flex;display:-ms-flexbox;display:flex;height:75%;left:0;position:fixed;width:100%;-webkit-box-pack:start;-webkit-justify-content:flex-start;-ms-flex-pack:start;justify-content:flex-start;-webkit-box-align:center;-webkit-align-items:center;-ms-flex-align:center;align-items:center;-webkit-box-orient:vertical;-webkit-box-direction:normal;-webkit-flex-direction:column;-ms-flex-direction:column;flex-direction:column;z-index:9}
</style>
