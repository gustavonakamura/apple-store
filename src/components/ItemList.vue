<template>
    <div class="item-grid">
        <ItemCard 
            v-for="(item, index) in items" 
            :key="index" 
            :item="item || {}" 
            :index="index" 
            @delete-item="deleteItem" 
        />
    </div>
</template>

<script>
import ItemCard from './ItemCard.vue';

export default {
    name: "ItemList",
    components: { ItemCard },
    props: {
        items: {
            type: Array,
            default: () => [] // Default to an empty array if items is not provided
        }
    },
    methods: {
        deleteItem(index) {
            this.$emit("delete-item", index);
        },
    },
};
</script>
