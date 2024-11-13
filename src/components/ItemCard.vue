<template>
    <div class="border rounded-lg shadow-lg p-4 m-2 bg-white">
        <h2 class="text-2xl font-bold text-gray-800">{{ item.name }}</h2>
        <p class="text-gray-600">{{ item.description }}</p>
        <p class="text-gray-700 font-semibold mt-2">Preço: {{ formatCurrency(item.price) }}</p>
        <button @click="deleteItem"
            class="mt-4 bg-red-500 text-white rounded px-4 py-2 hover:bg-red-600 transition-colors">
            Deletar
        </button>
    </div>
</template>

<script>
export default {
    name: "ItemCard",
    props: ["item", "index"],
    methods: {
        deleteItem() {
            this.$emit("delete-item", this.index);
        },
        formatCurrency(value) {
            return new Intl.NumberFormat("pt-BR", {
                style: "currency",
                currency: "BRL",
            }).format(value);
        },
    },
};
</script>