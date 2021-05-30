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
      <p>*при печати все окна ввода на странице не отображаются</p>
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
  p {
    font-size: 10px;
    font-style: italic;
    margin: 10px 0 0 0;
  }
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