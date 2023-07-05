<template>
  <div class="boxes flex flex-justify-around">
    <div class="inputBox__wrapper radius-border shadow flex flex-center flex-column">
      <el-input
          v-model="input"
          maxlength="25"
          placeholder="Please input"
          show-word-limit
          type="text"
      />
      <div class="input-button">
        <el-button @click="toTranslate">Translate</el-button>
      </div>
    </div>

    <div class="outputBox__wrapper radius-border shadow flex flex-center flex-column">
      {{ translate.result }}
    </div>
  </div>
</template>

<script lang="ts" setup>
import {ref} from 'vue'
const translate = ref('')
const input = ref('')

let toTranslate = () => {
  const options = {
    method: 'POST',
    headers: {
      accept: 'application/json',
      'content-type': 'application/json',
      Authorization: 'a_EnNlrX1W5HiAEXjGUA5KwpQGFJrBx7gy9VkWsuMPfFa0SQUAImmoOWTRuT4VJFPAmt5tiX0v1fa0TOwO'
    },
    body: JSON.stringify({platform: 'api', to: 'ru_RU', data: input.value})
  };

  fetch('https://api-b2b.backenster.com/b1/api/v3/translate', options)
      .then(response => response.json())
      .then(response => {translate.value = response
      })
      .catch(err => console.error(err));
}

</script>

<style lang="scss">
.inputBox__wrapper {
  width: 280px;
  height: 240px;
  max-height: 240px;
  padding: 15px;
  border: 1px solid black;
}

.outputBox__wrapper {
  width: 280px;
  height: 240px;
  max-height: 240px;
  padding: 15px;
  border: 1px solid black;
}

.boxes {
  margin-top: 30px;
}

.input-button {
  margin-top: 15px;
}

</style>