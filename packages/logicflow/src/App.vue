<template>
  <a-layout>
    <a-layout-header>Header</a-layout-header>
    <a-layout>
      <a-layout-sider theme="light"><draggable-list :list="list"/></a-layout-sider>
      <a-layout-content>Content</a-layout-content>
    </a-layout>
    <a-layout-footer>Footer</a-layout-footer>
  </a-layout>
</template>

<script>
import draggableList from './components/ItemList.vue'
let id = 1
export default {
  name: 'future-index',
  display: 'Future index',
  order: 1,
  debug: true,
  components: {
    draggableList
  },
  data() {
    return {
      enabled: true,
      list: [
        { name: 'John', id: 0 },
        { name: 'Joao', id: 1 },
        { name: 'Jean', id: 2 }
      ]
    }
  },
  methods: {
    add: function () {
      this.list.push({ name: 'Juan ' + id, id: id++ })
    },
    replace: function () {
      this.list = [{ name: 'Edgard', id: id++ }]
    }
  }
}
</script>
<style scoped>
.main-container {
  display: flex;
}
</style>
