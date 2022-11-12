<script>
export default {
    name: "app card",

    props: {
        person: Object,
    },
}
</script>

<template>

    <div class="col-2 p-2">
        <div class="my_card">
            <p> {{ person.name }} </p>
            <p> <img :src="person.img" alt=""> </p>
        </div>
    </div>

</template>

<style lang="scss" scoped>
.my_card {
    background-color: white;
    text-align: center;
}
</style>