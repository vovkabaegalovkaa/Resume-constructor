<template>
  <div class="container">
    <div class="formContainer">
      <div class="formControllerDiv">
        <form class="formController">
          <label for="type">Выберите тип:</label>
          <select name="type" id="type" v-model="type">
            <option value="app-header" selected="selected">Загловок</option>
            <option value="app-sup-header">Подзагловок</option>
            <option value="app-avatar">Аватар</option>
            <option value="app-text">Текст</option>
          </select>
          <label for="content">Введите содержимое блока</label>
          <textarea name="content" id="content" v-model.trim="content" wrap="soft" cols="20" rows="5"></textarea>
        </form>
      </div>
      <div class="btnContainer">
        <button class="btn" :disabled="content.length < 4" @click="sendData">Отправить</button>
      </div>
    </div>
    <div class="resume">
      <h1>Резюме</h1>
      <div class="component" v-for="(item, index) in components" :key="index">
        <component :is="item.name" :content="item.content"></component>
        <hr/>
      </div>
    </div>
  </div>
</template>

<script>
import AppAvatar from './AppAvatar.vue';
import AppHeader from './AppHeader.vue';
import AppSupHeader from './AppSupHeader.vue';
import AppText from './AppText.vue'; 

export default {
  data(){
    return {
      type: 'app-header',
      content: "",
      components: [],
    }
  },
  methods: {
    sendData(){
      let compObj = {
        name: this.type,
        content: this.content,
      }
      this.components.push(compObj);
      this.content = '';
    }
  }, 
  components: {
    'app-avatar': AppAvatar,
    'app-header': AppHeader,
    'app-sup-header': AppSupHeader,
    'app-text': AppText,
  }
}
</script>

