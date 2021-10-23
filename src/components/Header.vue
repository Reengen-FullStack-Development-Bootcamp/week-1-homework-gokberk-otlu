<template>
    <div class="navbar-main-container">
        <b-navbar type="dark" variant="dark">
            <b-navbar-nav class="navbar-container">
                <b-nav-item class="navbar-brand" href="#">Basket-App</b-nav-item>
                <b-nav-item-dropdown class="basket-dropdown" right>
                    <template #button-content><i class="fas fa-shopping-basket fa-lg"></i></template>
                    <b-dropdown-item href="#">
                        <dropdown-item />
                    </b-dropdown-item>
                    <b-dropdown-item href="#">
                        <dropdown-item />
                    </b-dropdown-item>
                    <b-dropdown-item href="#">RU</b-dropdown-item>
                    <b-dropdown-item href="#">FA</b-dropdown-item>
                    <b-dropdown-item href="#">FA</b-dropdown-item>
                </b-nav-item-dropdown>
            </b-navbar-nav>
        </b-navbar>
    </div>

</template>

<script>
import DropdownItem from './DropdownItem.vue'
    export default {
        components: {
            DropdownItem
        }
    }
</script>

<style scoped>
    .navbar-main-container {
        margin-bottom: 50px;
        position: sticky;
        top: 0;
    }

    .navbar-container {
        display: flex;
        align-items: center;
        padding: 0 5%;
    }

    .basket-dropdown {
        position: absolute;
        right: 220px;
    }
</style>