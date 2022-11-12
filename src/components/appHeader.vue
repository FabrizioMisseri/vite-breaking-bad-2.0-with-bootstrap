<script>
import { store } from '../../store.js';

export default {
    name: "app header",

    data() {
        return {
            store,
            categories: ["Breaking Bad", "Better call Saul"],
        }
    }
}
</script>

<template>

    <div class="container py-5">
        <div class="row py-3">
            <div class="col-12 text-center fs-1">Breaking Bad</div>
        </div>

        <div class="row py-3">
            <div class="offset-4 col-4 text-center">
                <select @change="$emit('event')" v-model="store.category" class="form-select" name="" id="">
                    <option value="">empty</option>
                    <option v-for="(category, index) in categories" :key="index" :value="category"> {{ category }}
                    </option>
                </select>
            </div>
        </div>

        <div class="row py-3">
            <div class="offset-4 col-4 text-center">
                FOUND {{ store.personaggi.length }} CHARACTERS
            </div>
        </div>
    </div>

</template>

<style lang="scss" scoped>

</style>
