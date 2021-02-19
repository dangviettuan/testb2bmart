<template>
  <div></div>
</template>

<script lang="ts">
import Vue from 'vue';
import NamiQChatWidget from '@namiq/chat-widget';

var myMixin = {
  created: function () {
    NamiQChatWidget.init({
      selector: '#chat-widget',
      socketUrl: 'https://dev-api.namiq.io/1.0.0/namiQ/chat',
      language: 'vi',
      showCloseButton: true,
      showFullScreenButton: true,
      mainColor: '#073a87',
      userTextColor: '#fff',
      userBackgroundColor: '#3596f0',
      assistTextColor: '#0065c3',
      assistBackgroundColor: '#c6e3ff',
    } as any)
  },
  methods: {
    hello: function () {
      console.log('hello from mixin!')
    }
  }
}

export default Vue.extend({
  mixins: [myMixin]
})
</script>

