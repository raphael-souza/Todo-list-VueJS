<template>
<div class="row">
    <div class="columns">
      <div class="column">
        <div class="field is-grouped" v-for="(task, index) in tasks">
          <p class="control">
            <a class="button is-rounded is-small check-button" @click="check(index)">
              <span class="icon is-small">
              </span>
            </a>
          </p>
          <p class="control is-expanded" :class="{'checked': task.checked}"> 
            {{task.description}} 
          </p>
          <p class="control">
            <a class="button is-danger is-small" @click="deleteTask(index)">
              <span class="icon is-small">
                <i class="fa fa-trash"></i>
              </span>
            </a>
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'todo-list',
  props: ['tasks'],
  data () {
    return {
    }
  },
  methods: {
    check(indexTas) {
      this.$emit('check', indexTas)
    },
    deleteTask(indexTask) {
      this.$emit('delete', indexTask)
    }
  }
}
</script>

<style scoped>
.button {
  border-radius: 50%;
}
.checked {
  text-decoration: line-through;
}
</style>