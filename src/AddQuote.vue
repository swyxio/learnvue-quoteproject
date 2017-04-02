<template>
    <div>
        <h3>Quote</h3>
        <div class="form-group">
        <input class="form-control" v-model="quotetoadd" @keyup.enter="addQuote" placeholder="type somethign here">
        <button class="btn-primary" @click="addQuote">Add Quote</button>
        </div>
    </div>
</template>
<script>
import {eventBus} from './main.js'
export default {
    data() {
        return {
            quotetoadd: ""
        }
    },
    methods: {
        addQuote() {
            if (this.quotetoadd) {
                eventBus.$emit('addquote',this.quotetoadd);
                this.quotetoadd = "";
            }
        }
    }
}
</script>
<style>
input {
    width: 100%;
    margin: 30px;
}
</style>
