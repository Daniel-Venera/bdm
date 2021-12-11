<template>
  <div>
    {{page.content}}
    <button 
      v-for="button in page.buttons" 
      :key="button.redirect"
      @click="turnPage(button.redirect)"
    >
      {{button.content}}
    </button>
  </div>
</template>
<script lang="ts">
import Vue from 'vue'
import { PAGES } from '@/constants/pages.js'
export default Vue.extend({
  data(){
    return {
      page: PAGES[0]
    }
  },
  methods: {
    turnPage(id){
      this.page = PAGES[id]
    }
  }
})
</script>