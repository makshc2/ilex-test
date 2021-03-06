<template>
  <div class="search-wrapper flex row justify-between items-center q-my-lg">
    <q-input v-model="search"
             filled
             type="search"
             class="search-input"
    >
      <template v-slot:prepend>
        <q-icon name="search" color="grey-8"/>
      </template>
    </q-input>
    <div>
      <q-avatar size="37px">
        <img src="https://cdn.quasar.dev/img/avatar.png">
      </q-avatar>
      <q-btn-dropdown outline flat dense color="grey"/>
    </div>
  </div>
</template>

<script>
export default {
  name: "SearchComponent",
  data(){
    return{
      search:''
    }
  }
}
</script>

<style scoped>

</style>
