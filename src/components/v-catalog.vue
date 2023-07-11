<template>
    <div class="v-catalog">
        <h1>Catalog</h1>
        <div class="v-catalog-body">
            <v-catalog-item
                v-for="product in PRODUCTS"
                :key="product.id"
                :product_data="product"
                @addToCart="addToCart"
            /> 
        </div>
    </div>
</template>

<script>
    
    import vCatalogItem from '@/components/v-catalog-item.vue';
    import { mapActions, mapGetters } from 'vuex';

    export default {
        components: {
            vCatalogItem,
        },
        data() {
            return {
                products: [],
            }
        },
        methods: {
            ...mapActions([
                'GET_PRODUCT_FROM_API',
                'ADD_TO_CART',
            ]), 
            addToCart(data) {
                this.ADD_TO_CART(data)
                // this.SET_CART(data);
                console.log(data)
            }
        },
        computed: {
            ...mapGetters([
                'PRODUCTS',
                'CART'
            ])
        }, 
        mounted() {
            this.GET_PRODUCT_FROM_API();
        },
    }
</script>

<style>
    .v-catalog-body {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        gap: 20px;
    }
    @media (max-width: 1000px) {
        .v-catalog-body {
            grid-template-columns: repeat(3, 1fr);
        }
    }
    @media (max-width: 770px) {
        .v-catalog-body {
            grid-template-columns: repeat(2, 1fr);
        }
    }
    @media (max-width: 380px) {
        .v-catalog-body {
            grid-template-columns: repeat(1, 1fr);
        }
    }
</style>