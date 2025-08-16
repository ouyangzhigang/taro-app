<template>
  <view class="demo">
    <view>
      欢迎使用 NutUI 开发 Taro 多端项目 <Dongdong />
    </view>
    <view>{{ count }}</view>
    <view>
      <nut-button type="primary" @click="handleClick">
        Count++
      </nut-button>
    </view>
    <Popup title="hello, my component"></Popup>
  </view>
</template>

<script setup>
import { ref } from 'vue';
import { Dongdong } from '@nutui/icons-vue-taro';
import Popup from "../../components/popup/index.vue";

const count = ref(0);

const handleClick = () => {
  count.value++;
};
</script>

<style>
.demo {
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
</style>