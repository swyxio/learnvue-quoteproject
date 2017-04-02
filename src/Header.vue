<template>
    <div class="app-header">
        <h1>Quotes Added</h1>
        <div class="progress">
            <div class="progress-bar" role="progressbar" 
                :aria-valuenow="quotes.length * 10"
                :style="'width: ' + quotes.length * 10 + '%'"
                aria-valuemin="0" aria-valuemax="100">{{ quotes.length }}/10</div>
        </div>
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style>
</style>

</template>

<script>
    export default {
        props: ['quotes']
    }
</script>

<style>
.app-header {
    margin: 30px auto
}
</style>
