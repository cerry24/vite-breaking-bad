<script>
export default {
    name: 'AppHeader',

    data() {
        return {
            archetypeValue: ''
        }
    },
}
</script>

<template>
    <div class="main-title">
        <img src="http://vignette1.wikia.nocookie.net/yugiohenespanol/images/a/aa/Yugioh_anime_logo.jpg/revision/latest?cb=20130310042737&path-prefix=es"
            alt="Yu-Gi-Oh logo">
        <h1>YU-Gi-Oh Api</h1>
    </div>

    <div class="filter">
        <label for="archetype-selector">Seleziona archetype</label>
        <select name="archetype-selector" id="archetype-selector" v-model.trim="archetypeValue"
            @change="$emit('filter', archetypeValue)">
            <option value="Alien">Alien</option>
            <option value="Laval">Laval</option>
            <option value="Vylon">Vylon</option>
            <option value="Inzektor">Inzektor</option>
            <option value="Umi">Umi</option>
            <option value="Gusto">Gusto</option>
        </select>
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

.filter {
    height: 35px;
    font-size: 22px;
    font-weight: bold;
    margin: 25px 15%;

    label {
        margin-right: 15px;
    }

    #archetype-selector {
        height: 100%;
        font-size: 17px;
        text-align: center;
        padding: 5px;
    }
}
</style>