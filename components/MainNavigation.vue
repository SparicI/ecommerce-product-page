
<template>
    <nav
        class="nav"
        id="main-nav"
        aria-label="Main navigation"
    >
        <button
            @click="$emit('closeMenu')"
            class="nav__close-btn"
        >
            <img
                src="/images/icon-close.svg"
                alt="Close menu"
            >
        </button>
        <ul class="nav__list margin-inline-start-600">
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
</template>

<script setup>

</script>

<style scoped>
.nav__close-btn {
    display: none;
}

@media screen and (max-width: 768px) {

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

@media screen and (min-width: 769px) {

    .nav__list {
        display: flex;
        gap: var(--spacing-600)
    }

    .nav__link {
        color: var(--dark-grayish-blue);
        padding-block: var(--spacing-800);
        display: inline-block;
    }

    .nav__link:hover {
        color: var(--very-dark-blue);
        padding-block-end: 29px;
        padding-block-start: var(--spacing-800);
        border-bottom: 3px solid var(--orange);
    }


}
</style>
