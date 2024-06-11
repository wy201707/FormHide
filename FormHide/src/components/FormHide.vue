<template>
  <a-form  
  :model="formDataConfig" >
  <slot :conditionFold="conditionFold"></slot>
  <a-row>
    <a-col :offset="18" :span="8" >
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
 
</template>
<script setup>
import { DownOutlined, UpOutlined } from '@ant-design/icons-vue';
import { ref } from 'vue'; 

const props = defineProps({
  formDataConfig: {
    type: Array,
    required: true
  },
  conditionInitShowLength: {
    type: Number,
    required: true
  }
});
let conditionFold=ref(false);

</script>