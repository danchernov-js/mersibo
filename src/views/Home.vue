<template>
  <div class="home">
    <div class="chair">
      <label for="name" class="chair__text">Введите Ф.И.О. Председателя УС:</label>
      <input 
        id="name" 
        class="chair__input" 
        type="text" 
        v-model="chairman"
        placeholder="Фамилия И.О."
      >
    </div>
    
    <MyDocument 
      :chairman="chairman"
      msg='hello'/>

  </div>
</template>

<script>
// @ is an alias to /src
import MyDocument from '@/components/MyDocument.vue'

export default {
  name: 'Home',
  components: {
    MyDocument
  },
  data() {
    return {
      chairman: ''
    }
  }
}
</script>

<style lang="scss" scoped>
  .chair {
    background-color: coral;
    margin-bottom: 50px;
    padding: 10px;

    &__input {
      margin-left: 5px;
      border: none;
      font-size: 12px;
    }
  }

  @media print {
    .chair {
      display: none;
    }
  }
</style>