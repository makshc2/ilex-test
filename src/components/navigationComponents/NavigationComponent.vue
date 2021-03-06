<template>
  <q-tabs
      v-model="tab"
      vertical
      switch-indicator
      indicator-color="green-5"
      class="navigation-wrapper text-white shadow-2"
  >
    <div class="logo flex justify-center items-start q-mt-xl">
      <img src="../../assets/img/logo.png" alt="logo">
    </div>
    <div>
      <q-tab v-for="(item, index) in names"
             :key="index"
             :name="item.name"
             class="text-capitalize"
             @click="filterPosts(item.id)"
      >
        <q-avatar size="37px">
          <img src="https://cdn.quasar.dev/img/avatar.png">
        </q-avatar>
        <span>{{item.name}}</span>
      </q-tab>
    </div>
  </q-tabs>
</template>

<script>

export default {
  name: "NavigationComponent",
  props:{
    id: {
      type: Number,
      default: 0
    }
  },
  data(){
    return{
      idUser: Number,
      tab: 'All subscription',
      names: [
        {
          id: 1,
          name: 'Ronald Sherman'
        },
        {
          id: 2,
          name: 'Donna Harvey'
        },
        {
          id: 3,
          name: 'Angela Johnson'
        },
        {
          id: 0,
          name: 'All subscription'
        },
      ]
    }
  },
  methods:{
    filterPosts (id) {
      this.$emit('filter-post', id)
    }
  }
}
</script>

<style scoped>

</style>
