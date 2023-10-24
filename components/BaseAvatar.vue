<template>
    <!-- Profile avatar -->
    <button class="avatar">
        <img
            src="/images/image-avatar.png"
            alt="Profile avatar"
            class="avatar__image"
        >
    </button>
</template>

<script setup>

</script>

<style socped>
.avatar:hover,
.avatar:focus {
    outline: 1px solid var(--orange);
    border-radius: 50%;

}

@media screen and (max-width: 768px) {
    .avatar {
        width: 35px;
    }
}

@media screen and (min-width: 769px) {
    .avatar__image {
        width: 55px;
    }


}
</style>