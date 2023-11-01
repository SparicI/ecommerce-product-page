
<template>
    <div class="padding-inline-400 padding-block-end-200 margin-block-start-800">
        <p class="product__subheading">Sneaker company</p>
        <h1 class="product__heading color-dark-blue">Fall Limited Edition <br>Sneakers</h1>
        <p class="font-size-300">These low-profile sneakers are your perfect casual wear companion. Featuring a
            durable rubber outer sole,
            they’ll withstand everything the weather can offer. </p>
        <!-- Price wrapper -->
        <div class="flex padding-block-400 font-weight-bold product__discont-section">
            <div class="flex gap-400 flex-1">
                <p class="product__discount-price color-dark-blue">$125.00</p>
                <p class="product__discount">50%</p>
            </div>
            <p class="product__price">$250.00</p>
        </div>
        <!-- Button wrapper -->
        <div class="product__controls">
            <div class="product__quantity-container">
                <button
                    type="button"
                    aria-label="decrease quantity of selected product by one"
                    @click="decreaseQuantity"
                >
                    <svg
                        width="12"
                        height="4"
                        xmlns="http://www.w3.org/2000/svg"
                        xmlns:xlink="http://www.w3.org/1999/xlink"
                    >
                        <defs>
                            <path
                                d="M11.357 3.332A.641.641 0 0 0 12 2.69V.643A.641.641 0 0 0 11.357 0H.643A.641.641 0 0 0 0 .643v2.046c0 .357.287.643.643.643h10.714Z"
                                id="a"
                            />
                        </defs>
                        <use
                            fill="#FF7E1B"
                            fill-rule="nonzero"
                            xlink:href="#a"
                        />
                    </svg>
                </button>

                <p class="font-weight-bold">
                    {{ quantity }}
                </p>
                <button
                    type="button"
                    aria-label="increase quantity of selected product by one"
                    @click="increaseQuantity"
                >
                    <svg
                        width="12"
                        height="12"
                        xmlns="http://www.w3.org/2000/svg"
                        xmlns:xlink="http://www.w3.org/1999/xlink"
                    >
                        <defs>
                            <path
                                d="M12 7.023V4.977a.641.641 0 0 0-.643-.643h-3.69V.643A.641.641 0 0 0 7.022 0H4.977a.641.641 0 0 0-.643.643v3.69H.643A.641.641 0 0 0 0 4.978v2.046c0 .356.287.643.643.643h3.69v3.691c0 .356.288.643.644.643h2.046a.641.641 0 0 0 .643-.643v-3.69h3.691A.641.641 0 0 0 12 7.022Z"
                                id="b"
                            />
                        </defs>
                        <use
                            fill="#FF7E1B"
                            fill-rule="nonzero"
                            xlink:href="#b"
                        />
                    </svg>
                </button>

            </div>
            <button
                class="button-primary margin-block-400"
                @click="addToCart"
            >
                <img
                    src="/images/icon-cart-white.svg"
                    alt=""
                >
                Add to cart
            </button>
        </div>
    </div>
</template>

<script setup>
let quantity = useState('quantityState', () => 0)
const decreaseQuantity = () => {
    if (quantity.value > 0) {
        quantity.value--
    }

}
const increaseQuantity = () => quantity.value++

let cartHasItems = useState('cartFull', () => false)
const addToCart = () => cartHasItems.value = true

</script>

<style scoped>
.product__subheading {
    padding-block: var(--spacing-400);
    color: hsl(26, 100%, 55%);
    text-transform: uppercase;
    font-weight: 700;
    font-size: var(--font-size-200);
    letter-spacing: 1px;
}

.product__heading {
    font-size: clamp(1.4rem, 5vw, 2.35rem);
    margin-block-end: 1rem;
}


.product__discount-price {
    font-size: var(--font-size-800);
}

.product__discount {
    font-size: var(--font-size-300);
    color: var(--orange);
    background-color: var(--pale-orange);
    padding-inline: var(--spacing-200);
    border-radius: var(--border-radius-soft-5);
}

.product__price {
    font-size: var(--font-size-300);
    color: var(--grayish-blue);
    text-decoration: line-through;

}

.product__quantity-container {
    display: flex;
    justify-content: space-between;
    width: 100%;
    padding: var(--spacing-400);
    background-color: var(--light-grayish-blue);
    border-radius: var(--border-radius-soft-10);
}

svg:hover use {
    fill: var(--orange-active) !important;
}


@media screen and (min-width: 768px) {
    .product__discont-section {
        flex-direction: column;
        align-items: flex-start;
    }

}

@media screen and (min-width: 1024px) {

    .product__controls {
        display: grid;
        grid-template-columns: 1fr 2fr;
        align-items: center;
        gap: var(--spacing-400);
    }

}
</style>
