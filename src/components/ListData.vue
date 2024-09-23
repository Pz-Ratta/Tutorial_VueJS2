<template>
    <ul>
        <MyPerson v-for="(item, index) in employees" 
            :key="index"
            :name="item.name"
            :salary="item.salary"
            :department="item.department"
            :isVisible="item.isVisible"
            :gender="item.gender"
            :skill="item.skill"
        />
    </ul>
</template>
<script>


import MyPerson from './MyPerson.vue';

export default {
    name: 'ListData',
    components: {
        MyPerson,
    },
    props:["employees"]
}
</script>
<style scoped>
ul{
    list-style: none;
    margin: 1rem 0;
    padding: 0;
}
</style>
