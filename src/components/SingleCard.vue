<template >
    <div class="card">
        <img :src="backUrl + '/storage/' + element.cover_img" class="card-img-top">
        <div class="card-body">
            <h5 class="card-title">{{element.name}}</h5>
            <p class="card-text">{{element.description}}</p>
            <router-link :to="'/'" class="btn btn-primary">Dettagli</router-link>
        </div>
    </div>
</template>

<script>

export default {
    props: {
        backUrl: String,
        element: Object
    },

}
</script>

<style lang="scss"></style>