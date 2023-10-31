<template>
  <div>
    <TheHeader />

    <main class="main-container">

      <ProductGallery @show-gallery="showGallery" />
      <ProductDetails />

      <div
        class="lightbox-gallery-container"
        v-if="lightboxGalleryIsOpen"
      >
        <button
          type="button"
          class="close-gallery-btn"
          @click="closeGallery"
        >
          <svg
            width="14"
            height="15"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="m11.596.782 2.122 2.122L9.12 7.499l4.597 4.597-2.122 2.122L7 9.62l-4.595 4.597-2.122-2.122L4.878 7.5.282 2.904 2.404.782l4.595 4.596L11.596.782Z"
              fill="#fff"
              fill-rule="evenodd"
            />
          </svg>
        </button>
        <ProductGallery class="lightbox-gallery" />
      </div>


    </main>

  </div>
</template>

<script setup>

const lightboxGalleryIsOpen = ref(false)
const showGallery = () => lightboxGalleryIsOpen.value = true
const closeGallery = () => lightboxGalleryIsOpen.value = false


</script>

<style>
@media screen and (min-width: 769px) {
  .main-container {
    display: flex;
    gap: 5rem;
    padding: 3rem;
    padding-block-start: 12rem;
  }

  .lightbox-gallery-container {
    position: fixed;
    inset: 0;
    z-index: 10000;
    display: grid;
    grid-template-columns: 1fr 500px 1fr;
    grid-template-rows: 1fr 580px 1fr;
    background-color: var(--background);

  }

  .lightbox-gallery {
    grid-template-columns: 450px !important;
    grid-template-rows: 1fr 90px !important;
    grid-column: 2 / 3;
    grid-row: 2 / 3;
  }

  .close-gallery-btn {
    grid-column: 3 / 4;
    margin-inline-start: 10px;
    margin-block-start: 45px;
  }

  .close-gallery-btn:hover svg path {
    fill: var(--orange);
  }

}

@media screen and (min-width: 768px) and (max-width: 1025px) {
  .main-container {
    gap: var(--spacing-400);
  }

}
</style>
