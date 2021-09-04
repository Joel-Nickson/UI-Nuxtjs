<template>
  <div id="app">
    <add-members />
    <list-members :members="members"/>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import AddMembers from '../components/AddMembers.vue';
import ListMembers from '../components/ListMembers.vue'

export default Vue.extend({
  async asyncData() {
    const members = await fetch('http://localhost:8000/api').then(res => res.json())
    
    return {
      members
    }
  },
  components: { ListMembers, AddMembers },
  data() {
    return {
      members: []
    }
  }
});
</script>
