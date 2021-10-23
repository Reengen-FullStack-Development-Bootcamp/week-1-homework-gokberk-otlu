<template>
    <div>
        <b-button @click="openModel">
            <i class="fas fa-shopping-basket fa-lg me-2"></i>
            <span>{{ basket.length }}</span>
        </b-button>
        <b-modal ref="basketModel" title="Basket">
            <b-row v-if="basket.length === 0">
                <p>Basket is empty</p>
            </b-row>
            <basket-item v-else v-for="(item, index) in basket" :item="item" :key="index" />
        </b-modal>
    </div>
</template>

<script>
import BasketItem from './BasketItem.vue'
    export default {
        props: ["basket"],
        components: {
            BasketItem
        },
        methods: {
            openModel() {
                this.$refs["basketModel"].show();
            }
        }
    }
</script>

<style scoped>
</style>