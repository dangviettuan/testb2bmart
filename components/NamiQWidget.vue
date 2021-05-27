<template>
  <div></div>
</template>

<script lang="ts">
import Vue from 'vue';
import NamiQChatWidget from '@namiq/chat-widget';

var myMixin = {
  mounted: function () {
    const checkChanged = (eventName: string, payload: any) => {
      console.log(eventName, payload)

    }
    NamiQChatWidget.init({
      selector: '#chat-widget',
      socketUrl: 'https://dev-api.namiq.io/1.0.0/namiQ/chat',
      language: 'vi',
      showCloseButton: true,
      showFullScreenButton: true,
      mainColor: '#3596f0',
      userTextColor: '#fff',
      userBackgroundColor: '#3596f0',
      assistTextColor: '#0065c3',
      assistBackgroundColor: '#c6e3ff',
      defaultProductID: 249,
      logoUrl: 'https://b2bmart.vn/_nuxt/img/logo.3c0376c.png',
      conversationBackgroundColor: '#000',
      apiKey: 'TL7u0Qgp2GLA1aW4vQe1Q2XXlxVnYSKY',
      onWidgetEvent: checkChanged
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

