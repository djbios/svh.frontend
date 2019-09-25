<template>
    <nav class="navbar navbar-expand-sm bg-dark navbar-dark">
        <a class="navbar-brand" href="#">Top categories:</a>
        <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#collapsibleNavbar">
            <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="collapsibleNavbar">
<!--            <ul class="navbar-nav">-->
<!--                {% for t in types %}-->
<!--                <li class="nav-item">-->
<!--                    <a class="nav-link" href="{% url 'by_type' t %}">{{ t }}</a>-->
<!--                </li>-->
<!--                {% endfor %}-->
<!--            </ul>-->

            <ul class="navbar-nav">
                <li :key="tag.name" v-for="tag in tags">

                    <a class="nav-link" href="{% url 'by_type' t %}">{{ tag.name }}</a>-->
                </li>
            </ul>
        </div>
    </nav>
</template>

<script>
    export default {
        name: "NavBar",
        data () {
            return {
                tags:[
                    {name: 'sdfdsf'},
                    {name: 'sdg'}
                ]
            }
        }
    }

</script>

<style scoped>

</style>