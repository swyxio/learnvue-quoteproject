<template>
    <div class="container">
        <app-header :quotes="quotes"></app-header>
        <add-quote-component> </add-quote-component>
        <div class="row">
            <app-card v-for="(q,i) in quotes" :index="i">
                <p> {{ q }} </p>
            </app-card>
        </div>
        <app-footer />
    </div>
</template>

<script>
    import appHeader from './Header.vue'
    import appFooter from './AppFooter.vue'
    import appCard from './AppCard.vue'
    import addQuoteComponent from './AddQuote.vue'
    import {eventBus} from './main.js'
    export default {
        data() {
            return {
                quotes: ['a','b']
            }
        },
        components: {
            appHeader,
            appFooter,
            appCard,
            addQuoteComponent
        },
        created() {
            eventBus.$on('addquote',x => {
                if (this.quotes.length > 9) {
                    alert(' too many quotes! dlete first')
                } else {
                    this.quotes.push(x)
                }
            })
            eventBus.$on('deletecard',x => {
                this.quotes.splice(x,1)
            })
        }
    }
</script>

<style>
</style>
