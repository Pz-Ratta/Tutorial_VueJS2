<template>
    <li>
        <img src="https://cdn3.iconfinder.com/data/icons/business-avatar-1/512/11_avatar-512.png"/>
        <hr>
        <slot name="card-header"></slot>
        <slot name="card-button"></slot>
        <slot name="card-content"></slot>

    </li>
</template>
<script>
export default {
}
</script>

<style scoped>

img{
    width: 100px;
    height: 100px;
}

li {
    margin: 1rem 0;
    font-size: 1.25rem;
    font-weight: bold;
    background-color: purple;
    padding: 0.5rem;
    color: white;
    border-radius: 25px;
}

</style>
