
<template>
    <header class="flex justify-content-space-between">
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
                <nav
                    class="nav"
                    id="main-nav"
                    aria-label="Main navigation"
                >
                    <button @click="closeMenu">
                        <img
                            src="/images/icon-close.svg"
                            alt="Close menu"
                            class="nav__close-btn"
                        >
                    </button>
                    <ul class="nav__list">
                        <li><a
                                href="#"
                                class="nav__link"
                            >Collections</a></li>
                        <li><a
                                href="#"
                                class="nav__link"
                            >Men</a></li>
                        <li><a
                                href="#"
                                class="nav__link"
                            >Women</a></li>
                        <li><a
                                href="#"
                                class="nav__link"
                            >About</a></li>
                        <li><a
                                href="#"
                                class="nav__link"
                            >Contact</a></li>
                    </ul>
                </nav>

            </div>


        </div>

        <!-- Header - RIGHT -->
        <div class="flex">
            <!-- Add to Cart button -->
            <button>
                <img
                    src="/images/icon-cart.svg"
                    alt="Add to cart"
                >
            </button>

            <!-- Profile avatar -->
            <img
                src="/images/image-avatar.png"
                alt="Profile avatar"
                class="header__avatar"
            >
        </div>

    </header>
</template>

<script setup>

let isMenuOpen = ref(false)

// open and close menu for small resolutions
const openMenu = () => {
    console.log("clicked")
    isMenuOpen.value = true
}
const closeMenu = () => isMenuOpen.value = false
</script>

<style scoped>
.header__avatar {
    width: 55px;
    padding: var(--spacing-400);
}

.hamburger-bar {
    display: none;
}

.nav__close-btn {
    display: none;
}



@media screen and (max-width: 768px) {

    .hamburger-bar {
        display: block;
        padding: var(--spacing-400);
    }

    .nav-container {
        display: none;
        position: fixed;
        inset: 0;
    }

    .nav-container.open {
        display: block;
        background-color: var(--background);
    }

    .nav {
        position: fixed;
        top: 0;
        left: 0;
        height: 100%;
        width: 70vw;

        background-color: var(--white);
    }

    .nav__close-btn {
        display: block;
        padding: var(--spacing-600);
    }

    .nav__link {
        display: inline-block;
        padding-inline: var(--spacing-600);
        padding-block: var(--spacing-200);
        color: var(--very-dark-blue);
        font-weight: var(--font-weight-bold);
    }

}
</style>
