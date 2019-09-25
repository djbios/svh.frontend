<template>
    <nav class="navbar navbar-expand-sm bg-dark navbar-dark">
        <a class="navbar-brand" href="#">Top categories:</a>
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#collapsibleNavbar">
            <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="collapsibleNavbar">
            <ul class="navbar-nav">
                <li :key="tag.name" v-for="tag in tags">
                    <a class="nav-link" href="{% url 'by_type' t %}">{{ tag.name }}</a>
                </li>
            </ul>
        </div>
        <p>{{js}}</p>
    </nav>
</template>

<script>
    import axios from 'axios';

    export default {
        name: "NavBar",
        vars: {},
        data () {
            return {
                tags:[
                    {name: 'sdfdsf'},
                    {name: 'sdg'}
                ],
                js:""
            }
        },
        mounted() {
            axios
                .get('https://api.coindesk.com/v1/bpi/currentprice.json')
                .then(response => (this.js = response.data.bpi.USD));
        }
    }

</script>

<style scoped>

</style>