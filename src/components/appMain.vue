<script>
import { store } from '../../store';
import appCard from './appCard.vue';

export default {
    name: "app main",

    components: {
        appCard,
    },

    data() {
        return {
            store,
        }
    },

} 
</script>

<template>

    <section class="container">

        <div class="row g-5">

            <!-- (* 6)
            <div class="col-2 p-2">
                <div class="my_card">
                    ciao
                </div>
            </div> 
            -->

            <appCard v-for="(character, index) in store.personaggi" :key="index" :person="character" />

        </div>

    </section>

</template>

<style lang="scss" scoped>
.container {
    color: black;

}
</style>