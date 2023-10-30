<template>
    <dialog
        :open="isCartOpen"
        @mouseover="isCartOpen = true"
        @mouseleave="isCartOpen = false"
        ref="cartModal"
        class="cart"
    >
        <h2 class="cart__header">
            Cart
        </h2>
        <div
            class="cart__empty"
            v-if="!cartHasItems"
        >
            <p>Your cart is empty.</p>
        </div>
        <div
            v-else
            class="cart__items-added"
        >
            <ul>
                <li class="cart__list">
                    <img
                        class="cart__img"
                        src="/images/image-product-1-thumbnail.jpg"
                        alt="Two beige sneakers"
                    >
                    <div class="cart__product font-size-300">
                        <p>Fall Limited Edition Sneakers</p>
                        <p>
                            <span>$125.00</span>
                            x
                            <span>{{ quantity }}</span>
                            <span class="font-weight-bold color-dark-blue margin-inline-start-200">${{ totalPrice.toFixed(2)
                            }}</span>
                        </p>
                    </div>
                    <button
                        aria-label="Delete item in cart"
                        @click="deleteCartItems"
                    >
                        <img
                            src="/images/icon-delete.svg"
                            alt="Delete item in cart"
                        >
                    </button>

                </li>
            </ul>
            <div class="cart__footer">
                <button
                    type="button"
                    class="button-primary"
                >Checkout</button>
            </div>

        </div>


    </dialog>
</template>

<script setup>
const props = defineProps({
    isCartOpen: {
        type: Boolean,
        default: false
    }
})

const quantity = useState('quantityState', () => 0)
const cartHasItems = useState('cartFull', () => false)
const totalPrice = computed(() => {
    return quantity.value * 125
})

const deleteCartItems = () => {
    quantity.value = 0
    cartHasItems.value = false
}
</script>

<style socped>
.cart {
    position: absolute;
    z-index: 1000;
    right: 0;
    left: -220px;
    top: 85px;
    width: 360px;
    height: 260px;
    border: none;
    box-shadow: var(--box-shadow-base);
    border-radius: var(--border-radius-soft-10);
}

.cart__header {
    padding: var(--spacing-600);
    font-size: var(--font-size-400);
    border-bottom: 2px solid var(--light-grayish-blue);
}

.cart__empty {
    display: grid;
    height: calc(100% - 80px);
    place-items: center;
    color: var(--dark-grayish-blue);
    font-weight: var(--font-weight-bold);
}

.cart__items-added {
    padding: var(--spacing-600);
    color: var(--dark-grayish-blue);
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    height: 70%;
}

.cart__list {
    display: flex;
    justify-content: space-between;

}

.cart__img {
    width: 50px;
    border-radius: var(--border-radius-soft-5);
}
</style>