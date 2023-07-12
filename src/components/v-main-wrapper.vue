<template>
    <div class="v-main-wrapper">
        <div class="container">
            <h1>{{ title }}</h1>
        </div>
    </div>
    <v-catalog/>
    <v-cart
        
        :cart_data="CART"
    />
</template>

<script>
import vCatalog from '@/components/v-catalog.vue'
import vCart from '@/components/v-cart.vue'
import { mapGetters } from 'vuex'

    export default {
        name: 'v-main-wrapper',
        components: {
            vCatalog, vCart,
        },
        data() {
            return {
                title: 'Main wrapper',
            }
        },
        computed: {
            ...mapGetters([
                "CART"
            ])
        }
    }
</script>

<style>
    
</style>