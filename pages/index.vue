<template>
  <div class="container">
    <div>
      <Logo />
      <h1 class="title">testb2bmart</h1>
      <div class="links">
        <a
          href="https://nuxtjs.org/"
          target="_blank"
          rel="noopener noreferrer"
          class="button--green"
        >
          Documentation
        </a>
        <a
          href="https://github.com/nuxt/nuxt.js"
          target="_blank"
          rel="noopener noreferrer"
          class="button--grey"
        >
          GitHub
        </a>
      </div>
      <form>
    <input type="text" ref="my_input">
    <button @click.prevent="getFormValues()">Change ProductId</button>
  </form>
    </div>
    <div id="chat-widget"></div>
    <client-only placeholder="loading...">
          <NamiQWidget/>

    </client-only>
    
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import NamiQChatWidget from '@namiq/chat-widget';


export default Vue.extend({

  methods: {
    getFormValues () {
      // console.log(this.$refs['my_input'].value);
      NamiQChatWidget.setProductId((this.$refs['my_input'] as any).value)
    }
  }
})
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
