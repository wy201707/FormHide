<template>
  <form-hide>
    <a-form
      ref="formRef"
      :model="formDataConfig"
    >
      <a-row :gutter="[0,20]">
        <a-col
          :span="8"
          v-for="itemID in formDataConfig.slice( 0,conditionFold ? conditionInitShowLength : formDataConfig.length)"
          :key="itemID"
        >
          <a-button style="background-color: aqua;width: 300px">{{itemID}}</a-button>
        </a-col>
      </a-row>
      <!-- <a-row  :offset="8" :gutter="{ xs: 8, sm: 16, md: 24, lg: 32 }"> -->
      <a-row>
      
        <a-col :offset="18" :span="8" >
          {{ xs,sm,md,lg }}
          <a style="font-size: 16px" @click="conditionFold=!conditionFold">
            <template v-if="conditionFold">
              <DownOutlined />
            </template>
            <template v-else>
              <UpOutlined />
            </template>
            {{conditionFold? '展开':'折叠'}}
          </a>
        </a-col>
        
      </a-row>
    </a-form>

  </form-hide>
</template>

<script setup>
import { DownOutlined, UpOutlined } from '@ant-design/icons-vue';
import {FormHide} from "./components/index.js";
import { ref } from 'vue'; 

const formRef = ref()
  // formDataConfig=ref(new Array(10).fill((idx)=>idx+1))
  const formDataConfig = ref(new Array(10).fill(null).map((_, idx) => idx + 1));
  let conditionFold=ref(false);
  let conditionInitShowLength=3


</script>
