<template>
    <div>
        <Header />
        <b-container>
            <b-row class="product-cards-container">
                <product-card
                v-for="product in products"
                :product="product"
                :key="product.id" />
            </b-row>
        </b-container>
    </div>
</template>

<script>
import ProductCard from './ProductCard.vue'
import Header from './Header.vue'
export default {
    name: 'App',
    components: {
        ProductCard,
        Header
    },
    data() {
        return {
            products: [
                {
                    id: 1,
                    name: "NIKE EPIC REACT FLYKNIT v1".toUpperCase(),
                    category: "WOMEN'S RUNNING SHOE".toUpperCase(),
                    detail: "The Nike Epic React Flyknit 2 takes a step up from its predecessor with smooth, lightweight performance and a bold look.",
                    price: 150,
                    rating: 4,
                    colorCode: "#D3ADAC",
                    image: "nike-epic-react-pink.jpg"
                },
                {
                    id: 2,
                    name: "NIKE EPIC REACT FLYKNIT v1".toUpperCase(),
                    category: "WOMEN'S RUNNING SHOE".toUpperCase(),
                    detail: "The Nike Epic React Flyknit 2 takes a step up from its predecessor with smooth, lightweight performance and a bold look.",
                    price: 150,
                    rating: 4,
                    colorCode: "#3476A6",
                    image: "nike-epic-react-blue.jpg"
                },
                {
                    id: 3,
                    name: "NIKE EPIC REACT FLYKNIT v2".toUpperCase(),
                    category: "WOMEN'S RUNNING SHOE".toUpperCase(),
                    detail: "The Nike Epic React Flyknit 2 takes a step up from its predecessor with smooth, lightweight performance and a bold look.",
                    price: 150,
                    rating: 4,
                    colorCode: "#D3ADAC",
                    image: "nike-epic-react-pink.jpg"
                },
                {
                    id: 4,
                    name: "NIKE EPIC REACT FLYKNIT v2".toUpperCase(),
                    category: "WOMEN'S RUNNING SHOE".toUpperCase(),
                    detail: "The Nike Epic React Flyknit 2 takes a step up from its predecessor with smooth, lightweight performance and a bold look.",
                    price: 150,
                    rating: 4,
                    colorCode: "#3476A6",
                    image: "nike-epic-react-blue.jpg"
                },
            ],
        }
    },
}
</script>

<style scoped>
    .product-cards-container {
        display: flex;
        gap: 30px;
        justify-content: center;
        align-items: center;
    }
</style>
