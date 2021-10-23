<template>
    <b-row class="basket-item-container" :style="cssBasketVar">
        <b-col cols="4">
            <b-img class="product-card-image" :src="require('../assets/' + item.productImage)" fluid
                alt="Responsive image">
            </b-img>
        </b-col>
        <b-col>
            <p class="basket-product-name">{{ item.productName }}</p>
            <p>Size: {{ item.productSize }}</p>
            <div>
                <i @click="decreaseProductNumber" class="fas fa-minus"></i>
                <span class="basket-product-number">{{ item.productNumber }}</span>
                <i @click="increaseProductNumber" class="fas fa-plus"></i>
            </div>
        </b-col>
    </b-row>
</template>

<script>
export default {
    props: ["item", "basket"],
    methods: {
        decreaseProductNumber() {
            if(this.item.productNumber > 1) {
                this.item.productNumber -= 1;
            } else {
                this.basket.splice(this.basket.indexOf(this.item), 1);
                // console.log(this.basket.indexOf(this.item));
            }
        },
        increaseProductNumber() {
            this.item.productNumber += 1;
        },
    },
    computed: {
        cssBasketVar() {
            return {
                '--basket-item-color': this.item.productColor
            }
        }
    },
}
</script>

<style scoped>
    .basket-item-container {
        display: flex;
        align-items: center;
        overflow: hidden;
    }

    .basket-item-container img {
        transition: transform .8s;
    }

    .basket-item-container:hover img {
        transform: scale(1.1);
    }

    .basket-item-container:nth-child(odd) {
        background-color: #F3F3F3;
    }

    .basket-product-name {
        color: var(--basket-item-color);
    }

    .basket-product-number {
        margin: 0 7px;
    }

    i.fas {
        color: #333;
        transition: transform .3s;
        cursor: pointer;
    }

    i.fas:hover {
        transform: scale(1.1);
    }

    p {
        margin: 0;
    }

</style>