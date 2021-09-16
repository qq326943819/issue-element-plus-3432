<script setup lang="ts">
import { ref } from "vue-demi";

const formData = ref({
  name: '',
  age: ''
})


const form = ref(null)

function resetHandler() {
  (form.value as any).resetFields();
}

</script>

<template>
  <el-form ref="form" :model="formData">
    <el-form-item label="name" prop="name">
      <el-input v-model="formData.name"></el-input>
    </el-form-item>
    <el-form-item label="age" prop="age">
      <el-input v-model="formData.age"></el-input>
    </el-form-item>
    <el-form-item>
      <el-button native-type="reset">reset</el-button>
      <el-button>submit</el-button>
      <el-button @click="resetHandler">form-method-reset</el-button>
    </el-form-item>
  </el-form>
</template>