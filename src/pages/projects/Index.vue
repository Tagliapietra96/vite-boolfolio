<template>
    <AppHeader/>
    <section>
        <div class="container">
            <div class="row">

                <div v-for="element in projects" class="col-3">
                    <h1>ciao</h1>
                </div>

            </div>
        </div>
    </section>    
    
</template>

<script>
import AppHeader from '../../components/AppHeader.vue';
import axios from "axios";
export default {
    components: { AppHeader },
    name: "ProjectsIndex",
    data(){
        return{
            backUrl: "http://127.0.0.1:8000",
            projects: []
        }
    },
    methods: {
        fetchProjects(){
            axios.get(this.backUrl + "/api/projects").then((resp) => {
                this.projects = resp.data.data;
                console.log(resp.data.data);
            })
        }
    },
    mounted() {
        this.fetchProjects();
    },
}
</script>

<style lang="scss">
    
</style>