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
  <button @click.prevent="openBanner()">Open Banner</button>
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
    },
    openBanner () {
      NamiQChatWidget.openBanner(`<style>
  @media screen and (min-width: 525px) {
    .ad {
      height: 90px;
    }
  
    .ad .container {
      padding: 0 25px;
    }
  
    .ad .logo {
      float: left;
    }
  
    .ad h2 {
      float: right;
      background-color: rgba(255, 255, 255, .25);
    }
  }
  </style>
  
  <section class="ad" style="max-width: 768px; background-image: url('https://validatedlearning.co/wp-content/uploads/2017/08/green-geo-background-banner-300x89.jpeg'); background-size: cover; background-position: left center; border: 1px solid #333;">
    <div class="container" style="clear: both; padding: 1px 0 0 0;">
      <a href="http://www.timberland.com/" style="display: block; color: #fff; text-decoration: none;">
        <div class="logo" alt="Timberland" style="width: 283px; margin: 20px auto; height: 50px; background-image: url('https://upload.wikimedia.org/wikipedia/commons/thumb/e/e8/Timberland-logo.png/799px-Timberland-logo.png'); background-size: cover; background-position: center center;">
        </div>
      </a>
      
    </div>
  </section>`)
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
