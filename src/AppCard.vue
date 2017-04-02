<template>
  <div class="col-sm-4 app-card">
    <div class="card" @click="deleteMe">
      <div class="card-block">
          <p><slot></slot></p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.app-card {
    padding: 10px;
    cursor: pointer;
    font-family: 'Arizonia', cursive;
    font-size: 24px;
    color: #6e6e6e

}
</style>
<script>
import {eventBus} from './main'
export default {
    props: ['index'],
    methods: {
        deleteMe() {
            eventBus.$emit('deletecard', this.index)
        }
    }
}
</script>