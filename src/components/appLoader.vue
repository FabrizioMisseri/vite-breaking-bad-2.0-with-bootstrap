<script>
import { store } from '../../store';

export default {
    name: "app loader",

    data() {
        return {
            store,
        }
    }
}
</script>

<template>

    <div class="container">
        <div class="row">
            <div class="col-12 text-center fs-1">
                STO CARICANDO
            </div>
        </div>
    </div>


</template>

<style lang="scss" scoped>
div {
    color: green;
}
</style>