<template>
    <b-col md="7" lg="5" class="product-card-col" :style="cssColorVar">
        <b-row class="product-card">
            <b-col cols="6" class="product-image-size-container p-0 me-4">
                <b-row>
                    <b-img class="product-card-image" :src="require('../assets/' + this.product.image)" fluid
                    alt="Responsive image">
                    </b-img>
                </b-row>
                <b-row>
                    <h5 class="choose-size">CHOOSE SIZE</h5>
                    <b-row class="size-container m-0">
                        <div>5</div>
                        <div>6</div>
                        <div>7</div>
                        <div>8</div>
                        <div>9</div>
                        <div>10</div>
                        <div>11</div>
                        <div>12</div>
                    </b-row>
                </b-row>
            </b-col>
            <b-col class="p-0">
                <h3 class="product-category">{{ product.category }}</h3>
                <h2 class="product-header">{{ product.name }}</h2>
                <span class="product-price">$ {{ product.price }}</span>
                <div>
                    <b-form-rating id="rating-inline" :color="product.colorCode" readonly no-border
                    style="background-color: transparent; padding: 0; box-shadow: none;"
                    inline v-model="product.rating">
                    </b-form-rating>
                </div>
                <p class="product-explanation">
                    {{product.detail}}
                </p>
                <b-row class="btn-add-to-card">
                    <b-col>
                        <select name="product-select-numbers" id="product-select-numbers">
                            <option value="product-num-1">1</option>
                            <option value="product-num-1">2</option>
                            <option value="product-num-1">3</option>
                            <option value="product-num-1">4</option>
                            <option value="product-num-1">5</option>
                            <option value="product-num-1">6</option>
                            <option value="product-num-1">7</option>
                            <option value="product-num-1">8</option>
                            <option value="product-num-1">9</option>
                            <option value="product-num-1">10</option>
                        </select>
                    </b-col>
                    <b-col>
                        <span>ADD TO CARD</span>
                    </b-col>
                </b-row>
            </b-col>
        </b-row>
    </b-col>
</template>

<script>
    export default {
        created() {
            console.log(this.product);
        },
        data() {
            return {}
        },
        props: ['product'],
        computed: {
            cssColorVar() {
                return {
                    '--color': this.product.colorCode
                }
            }
        }
    }
</script>

<style scoped>

    .product-card-col {
        min-width: 524px;
    }

    .product-card {
        text-align: start;
        border-radius: 10px;
        overflow: hidden;
        padding: 23px 20px;
        background-color: #F4F5F5;
        box-shadow: 5px 4px 6px -1px rgba(145, 145, 145, 0.95);
    }

    .product-image-size-container {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
    }

    .product-card-image {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }

    .choose-size {
        font-size: 1rem;
        color: var(--color);
    }

    .size-container {
        display: flex;
        justify-content: space-between;
    }

    .size-container * {
        width: 25px;
        height: 25px;
        font-size: .9rem;
        display: flex;
        justify-content: center;
        align-items: center;
        border: .3px solid var(--color);
        color: var(--color);
    }

    .product-category {
        font-size: 1rem;
        color: var(--color);
    }

    .product-header {
        font-size: 1.2rem;
    }

    .product-price {
        font-size: 1.3rem;
        color: var(--color);
        font-weight: bold;
    }

    .product-explanation {
        font-size: .8rem;
    }

    .btn-add-to-card span {
        color: #fff;
        background-color: var(--color);
        width: 140px;
        height: 50px;
        display: flex;
        justify-content: center;
        align-items: center;
        border-radius: 4px;
        cursor: pointer;
    }

    #product-select-numbers {
        height: 100%;
        width: 100%;
        color: var(--color);
        border: 1px solid var(--color);
        text-align: center;
        border-radius: 4px;
    }
</style>