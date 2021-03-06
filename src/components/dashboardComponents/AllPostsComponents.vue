<template>
  <div class="q-ma-md">
    <q-card
      @click="openPost"
      class="my-card card-wrapper flex justify-between cursor-pointer"
    >
      <q-card-section>
          <div class="title text-capitalize q-mb-sm overflow-hidden">
            {{title}}
          </div>
          <div class="description overflow-hidden">
            {{description}}
          </div>
        </q-card-section>
      <q-card-actions align="left" class="counter flex items-center">
          <q-btn flat outline color="grey-5" icon="fas fa-comment" size="xs"></q-btn>
          <span>{{counterComment}}</span>
        </q-card-actions>
    </q-card>
  </div>
</template>

<script>
export default {
  name: "AllPostsComponents",
  data () {
    return {
      idPost: this.id
    }
  },
  props: {
    id: {
      type: Number
    },
    title: {
      type: String,
      default: 'Title'
    },
    description: {
      type: String,
      default: 'Description'
    },
    counterComment: {
      type: Number,
      default: 0
    }
  },
  methods:{
    openPost () {
      this.$emit('open-post', this.idPost)
    }
  }
}
</script>

<style scoped>

</style>
