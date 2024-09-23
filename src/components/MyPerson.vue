<template>
    <StyleCard>
        <template v-slot:card-header>
            <h1> {{ name }} </h1>
        </template>
        <template v-slot:card-content>
            <Transition-group name="fade">
                <p>เงินเดือน: {{ salary }} บาท, เพศ: {{ gender }}</p>
                <p> ตำแหน่งงาน: {{ department }} </p>
                <p> ภาษา: {{ skill }} </p>

            </Transition-group>
        </template>
    </StyleCard>
</template>
<script>
import StyleCard from './StyleCard.vue';


export default {
    name: 'MyPerson',
    components: {
        StyleCard
    },
    props: {
        name: {
            type: String,
            required: true
        },
        salary: {
            type: Number,
            default: 15000
        },
        department: {
            type: String,
            required: true
        },
        gender:{
            type: String,
            required: true
        },
        skill:{
            type: Array
        }
    }
}
</script>

<style scoped>
h1 {
    color: white;
}


</style>
