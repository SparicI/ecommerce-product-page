<template>
    <!-- Product Gallery -->
    <div class="gallery">
        <div class="gallery__container">
            <!-- Large image gallery -->
            <div class="gallery__large">
                <button
                    class="gallery__large-image-button"
                    @click="$emit('showGallery')"
                    aria-label="Open lightbox gallery"
                >
                    <img
                        v-if="isImageDisplayed === 'one'"
                        class="gallery__large-image"
                        src="/images/image-product-1.jpg"
                        alt="Two beige sneakers"
                    >
                </button>
                <button
                    class="gallery__large-image-button"
                    @click="$emit('showGallery')"
                    aria-label="Open lightbox gallery"
                >
                    <img
                        v-if="isImageDisplayed === 'two'"
                        class="gallery__large-image"
                        src="/images/image-product-2.jpg"
                        alt="Two beige sneakers, one sneaker on a rock"
                    >
                </button>
                <button
                    class="gallery__large-image-button"
                    @click="$emit('showGallery')"
                    aria-label="Open lightbox gallery"
                >
                    <img
                        v-if="isImageDisplayed === 'three'"
                        class="gallery__large-image"
                        src="/images/image-product-3.jpg"
                        alt="One beige sneaker on a two rocks"
                    >
                </button>
                <button
                    class="gallery__large-image-button"
                    @click="$emit('showGallery')"
                    aria-label="Open lightbox gallery"
                >
                    <img
                        v-if="isImageDisplayed === 'four'"
                        class="gallery__large-image"
                        src="/images/image-product-4.jpg"
                        alt="One beige sneaker on a two rocks"
                    >
                </button>

            </div>
            <div class="gallery__btns">
                <button
                    type="button"
                    class="button-gallery button-gallery--previous"
                >
                    <img
                        src="/images/icon-previous.svg"
                        alt="Button for previous images"
                    >
                </button>
                <button
                    type="button"
                    class="button-gallery button-gallery--next"
                >
                    <img
                        src="/images/icon-next.svg"
                        alt="Button for next images"
                    >
                </button>
            </div>

        </div>

        <!-- Thumbnails  -->
        <div class="gallery__small">
            <button
                class="gallery__thumbnail-button"
                @click="showImage('one')"
                aria-label="Show larger version of thumbnail"
            >
                <img
                    src="/images/image-product-1-thumbnail.jpg"
                    alt="Two beige sneakers"
                >
            </button>
            <button
                class="gallery__thumbnail-button"
                @click="showImage('two')"
                aria-label="Show larger version of thumbnail"
            >
                <img
                    src="/images/image-product-2-thumbnail.jpg"
                    alt="Two beige sneakers, one sneaker on a rock"
                >
            </button>
            <button
                class="gallery__thumbnail-button"
                @click="showImage('three')"
                aria-label="Show larger version of thumbnail"
            >
                <img
                    src="/images/image-product-3-thumbnail.jpg"
                    alt="One beige sneaker on a two rocks"
                >
            </button>
            <button
                class="gallery__thumbnail-button"
                @click="showImage('four')"
                aria-label="Show larger version of thumbnail"
            >
                <img
                    src="/images/image-product-4-thumbnail.jpg"
                    alt="One beige sneaker on a two rocks"
                >
            </button>

        </div>
    </div>
</template>

<script setup>
const isImageDisplayed = ref('one')
const showImage = (arg) => isImageDisplayed.value = arg

</script>

<style scoped>
.button-gallery {
    display: grid;
    place-items: center;
    height: 50px;
    aspect-ratio: 1;
    border-radius: 50%;
    background: var(--white);
    border: none;

}

@media screen and (max-width: 768px) {

    .gallery__container {
        position: relative;
    }

    .gallery__large {
        display: flex;
        overflow: hidden;
    }

    .gallery__large-image {
        max-height: 400px;
        width: 100vw;
        object-fit: cover;
    }

    .gallery__small {
        display: none;
    }

    .gallery__btns {
        position: absolute;
        top: 50%;
        width: 100vw;
        display: flex;
        justify-content: space-between;
        padding: 1rem;
    }

}

@media screen and (min-width: 769px) {
    img {
        border-radius: var(--border-radius-soft-10);
    }

    .gallery {
        display: grid;
        grid-template-rows: min(420px, 100%) 82px;
        grid-template-columns: repeat(4, 82px);
        gap: 1.5rem;
    }

    .gallery__container {
        grid-column: 1 / 5;
        grid-row: 1 / 2;
    }

    .gallery__btns {
        display: none;
    }

    .gallery__small {
        display: grid;
        grid-auto-flow: column;
        gap: var(--spacing-600);

        grid-column: 1 / 5;
        grid-row: 2 / 3;

    }

    .gallery__thumbnail-button {
        border-radius: var(--border-radius-soft-10);
    }

    .gallery__thumbnail-button:hover img {
        filter: opacity(0.5);
    }

    .gallery__thumbnail-button:active,
    .gallery__thumbnail-button:focus {
        outline: 2px solid var(--orange);

    }

    .lightbox-gallery .gallery__container {
        justify-self: center;
        position: relative;
    }

    .lightbox-gallery .gallery__small {
        gap: var(--spacing-400);
        justify-content: center;
    }

    .lightbox-gallery .gallery__small img {
        max-width: 90px;
    }

    .lightbox-gallery .gallery__btns {
        display: block;
        position: absolute;
        top: 43%;
        left: -25px;
        width: 575px;
        display: flex;
        justify-content: space-between;

    }

}
</style>