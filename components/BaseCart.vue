<template>
    <dialog
        :open="isCartOpen"
        ref="cartModal"
        class="cart"
    >
        <h2 class="cart__header">
            Cart
        </h2>
        <div class="cart__empty">
            <p>Your cart is empty.</p>
        </div>
        <!-- <div>
            <ul class="cart__items"></ul>
            <div class="cart__footer">
                <form method="dialog">
                    <button>OK</button>
                </form>
            </div>

        </div> -->


    </dialog>
</template>

<script setup>


const props = defineProps({
    isCartOpen: {
        type: Boolean,
        default: false
    }
})
</script>

<style socped>
.cart {
    position: absolute;
    z-index: 1000;
    right: 0;
    left: -220px;
    top: 65px;
    width: 360px;
    height: 260px;
    border: none;
    box-shadow: var(--box-shadow);
    border-radius: var(--border-radius-soft);
}

.cart__header {
    padding: var(--spacing-400);
    font-size: var(--font-size-400);
    border-bottom: 2px solid var(--light-grayish-blue);
}

.cart__empty {
    display: grid;
    height: calc(100% - 50px);
    place-items: center;
    color: var(--dark-grayish-blue);
    font-weight: var(--font-weight-bold);
}
</style>