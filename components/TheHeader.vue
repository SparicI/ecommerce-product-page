
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
            <nav
                class="nav"
                id="main-nav"
                aria-label="Main navigation"
            >
                <ul>
                    <li><a href="#">Collections</a></li>
                    <li><a href="#">Men</a></li>
                    <li><a href="#">Women</a></li>
                    <li><a href="#">About</a></li>
                    <li><a href="#">Contact</a></li>
                </ul>
            </nav>

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

<script>
</script>

<style scoped>
.nav {
    display: none;
}

.header__avatar {
    width: 55px;
    padding: 1rem;
}

.hamburger-bar {
    padding: 1rem
}
</style>
