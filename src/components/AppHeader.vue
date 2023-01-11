<script>
export default {
    name: 'AppHeader'
}
</script>

<template>
    <div class="main-title">
        <img src="http://vignette1.wikia.nocookie.net/yugiohenespanol/images/a/aa/Yugioh_anime_logo.jpg/revision/latest?cb=20130310042737&path-prefix=es"
            alt="Yu-Gi-Oh logo">
        <h1>YU-Gi-Oh Api</h1>
    </div>
</template>

<style lang="scss" scoped>
@use '../styles/partials/variables' as *;

.main-title {
    display: flex;
    background-color: $secondary-color;
    padding: .5rem;

    img {
        width: 150px;
        padding-right: 20px;
    }
}
</style>