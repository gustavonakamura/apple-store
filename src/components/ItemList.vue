<template>
    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4 p-4">
        <ItemCard v-for="(item, index) in items" :key="index" :item="item" :index="index" @delete-item="deleteItem" />
    </div>
</template>

<script>
import ItemCard from './ItemCard.vue';

export default {
    name: "ItemList",
    components: { ItemCard },
    props: ["items"],
    methods: {
        deleteItem(index) {
            this.$emit("delete-item", index);
        },
    },
};
</script>

<style scoped>
/* Estilos para a lista */
</style>