
<template>
    <div class="padding-inline-400 padding-block-end-200">
        <p class="product__subheading">Sneaker company</p>
        <h1 class="product__heading">Fall Limited Edition <br>Sneakers</h1>
        <p class="product__description">These low-profile sneakers are your perfect casual wear companion. Featuring a
            durable rubber outer sole,
            they’ll withstand everything the weather can offer. </p>
        <!-- Price wrapper -->
        <div class="flex padding-block-400 font-weight-bold product__discont-section">
            <div class="flex gap-400 flex-1">
                <p class="product__discount-price">$125.00</p>
                <p class="product__discount">50%</p>
            </div>
            <p class="product__price">$250.00</p>
        </div>
        <!-- Button wrapper -->
        <div class="product__controls">
            <div class="product__quantity-container">
                <button type="button">
                    <img
                        src="/images/icon-minus.svg"
                        alt="Remove one item from cart"
                    >
                </button>

                <p class="font-weight-bold">
                    0
                </p>
                <button type="button">
                    <img
                        src="/images/icon-plus.svg"
                        alt="Add one item to cart"
                    >
                </button>

            </div>
            <button class="btn-add-to-cart">
                <img
                    src="/images/icon-cart-white.svg"
                    alt="Add to cart"
                >
                Add to cart
            </button>
        </div>
    </div>
</template>

<script setup>


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

.product__description {
    color: var(--dark-grayish-blue);
    font-size: var(--font-size-300);
}

.product__discount-price {
    font-size: var(--font-size-800);
}

.product__discount {
    font-size: var(--font-size-300);
    color: var(--orange);
    background-color: var(--pale-orange);
    padding-inline: var(--spacing-200);
    border-radius: var(--border-radius-soft);
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
    border-radius: var(--border-radius-soft);
}

.btn-add-to-cart {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: var(--spacing-400);
    width: 100%;
    padding: var(--spacing-400);
    margin-block: var(--spacing-400);
    border-radius: var(--border-radius-soft);
    background-color: var(--orange);
    color: var(--white);
    font-weight: var(--font-weight-bold);
}

@media screen and (min-width: 768px) {
    .product__discont-section {
        flex-direction: column;
        align-items: flex-start;
    }

    .product__controls {
        display: grid;
        grid-template-columns: 1fr 2fr;
        align-items: center;
        gap: var(--spacing-400);
    }

}
</style>
