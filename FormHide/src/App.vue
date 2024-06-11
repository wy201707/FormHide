<template>
  <form-hide   v-slot="slotProps" :formDataConfig="formDataConfig" :conditionInitShowLength="conditionInitShowLength" >
      <a-row :gutter="[0,20]">
        <a-col
          :span="8"
          v-for="itemID in formDataConfig.slice( 0,slotProps.conditionFold ? conditionInitShowLength : formDataConfig.length)"
          :key="itemID"
        >
          <a-button style="background-color: aqua;width: 300px">{{itemID}}</a-button>
        </a-col>
        <!-- 法二：
        <a-col
          :span="8"
          v-for="(itemID,index) in formDataConfig"
          :key="itemID"
        >
           <a-button v-if="index < (slotProps.conditionFold ? conditionInitShowLength : formDataConfig.length)"  style="background-color: aqua;width: 300px">{{itemID}}</a-button>
        </a-col> -->
      </a-row>
  </form-hide>
</template>

<script setup>
import {FormHide} from "./components/index.js";
import { ref } from 'vue'; 
const formDataConfig = ref(new Array(10).fill(null).map((_, idx) => idx + 1));
let conditionInitShowLength=3
</script>
