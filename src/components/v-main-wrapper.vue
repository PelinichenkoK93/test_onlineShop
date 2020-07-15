<template>
    <div class="v-main-wrapper">
        <keep-alive>
            <router-view></router-view>
        </keep-alive>
    </div>
</template>



<script>

export default {
    name: 'v-main-wrapper',
    props: {}, //данные которые приходят от родителя
    data() { //персональные данные компонента
        return{
            title: "Main wrapper"
        }
    },
    computed: {}, //вычислительные свойства компонента
    methods: {}, //отлавливаемые действия пользователя
    watch: {}, //следит за состоянием компонента
    mounted() {}, //отработка когда компонент полностью загрузится
}
</script>

<style>
    .v-main-wrapper {
        margin: 0 auto;
    }
</style>