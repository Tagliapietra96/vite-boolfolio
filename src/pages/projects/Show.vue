<template>
    <AppHeader/>
    <section class="mt-5">

        <div class="container">
            <SingleCard :backUrl="backUrl" :element="project"/>
        </div>

    </section>
</template>

<script>
import AppHeader from '../../components/AppHeader.vue';
import axios from "axios";
import SingleCard from '../../components/SingleCard.vue';


export default {
    components: { AppHeader, SingleCard },
    data(){
        return{
            backUrl: "http://127.0.0.1:8000",
            project: {}
        }
    },
    methods: {
        fetchProject(){
            axios.get(this.backUrl + "/api/projects/" + this.$route.params.id).then((resp) => {
                this.project = resp.data;
            })
        }
    },
    mounted() {
        this.fetchProject();
    },
}
</script>

<style lang="scss">
    
</style>