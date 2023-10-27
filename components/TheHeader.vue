
<template>
    <header class="header flex justify-content-space-between">
        <!-- Header - LEFT -->
        <div class="flex">

            <!-- Hamburger -->
            <button
                type="button"
                aria-haspopup="true"
                aria-controls="main-nav"
                aria-expanded="false"
                class="hamburger-bar"
                @click="openMenu"
            >

                <img
                    src="/images/icon-menu.svg"
                    alt="Open menu button"
                >
            </button>

            <!-- Logo -->
            <img
                src="/images/logo.svg"
                alt="Open menu button"
            >

            <!-- Navigation -->
            <div
                class="nav-container"
                :class="{ 'open': isMenuOpen }"
            >
                <MainNavigation @close-menu="closeMenu" />
            </div>


        </div>

        <!-- Header - RIGHT -->
        <div class="flex position-relative align-self-center">
            <!-- Add to Cart button -->
            <button
                class="add-to-cart-btn"
                @mouseover="isCartOpen = true"
                @mouseleave="isCartOpen = false"
            >
                <img
                    src="/images/icon-cart.svg"
                    alt="Add to cart"
                >
            </button>
            <BaseCart :is-cart-open="isCartOpen" />

            <BaseAvatar />

        </div>

    </header>
</template>

<script setup>

// -------------- Menu ------------------
let isMenuOpen = ref(false)

const openMenu = () => isMenuOpen.value = true
const closeMenu = () => isMenuOpen.value = false

// ------------- Cart modal -------------------
let isCartOpen = ref(false)


</script>

<style scoped>
.header {
    position: fixed;
    z-index: 100;
    width: 100%;
    max-width: 1024px;
    background-color: var(--white);
}

.hamburger-bar {
    display: none;
}

@media screen and (max-width: 768px) {

    .nav-container {
        display: none;
        position: fixed;
        inset: 0;
    }

    .nav-container.open {
        display: block;
        background-color: var(--background);
    }

    .hamburger-bar {
        display: block;
        padding: var(--spacing-400);
    }

    .add-to-cart-btn {
        margin-inline-end: var(--spacing-400);
    }

}

@media screen and (min-width: 769px) {
    .header {
        border-bottom: 1px solid #ebedf2;
    }

    .add-to-cart-btn {
        padding: var(--spacing-800) var(--spacing-400);
        margin-inline-end: var(--spacing-800);
    }

}
</style>
