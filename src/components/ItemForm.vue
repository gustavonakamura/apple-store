<script>
export default {
    name: "ItemForm",
    data() {
        return {
            item: {
                name: '',
                description: '',
                price: 0,
            },
        };
    },
    methods: {
        addItem() {
            this.$emit('add-item', { ...this.item });
            this.item = { name: '', description: '', price: 0 };
        },
    },
};
</script>
<template>
    <form @submit.prevent="addItem" class="space-y-6 p-6 bg-gray-100 rounded-lg shadow-md max-w-lg mx-auto">
        <div>
            <label class="block text-lg font-semibold text-gray-700 mb-4">Nome do Produto</label>
            <input v-model="item.name" type="text" required
                class="w-full p-3 border border-gray-300 rounded focus:outline-none focus:ring-2 focus:ring-blue-500" />
        </div>
        <div>
            <label class="block text-lg font-semibold text-gray-700 mb-4">Descrição</label>
            <input v-model="item.description" type="text" required
                class="w-full p-3 border border-gray-300 rounded focus:outline-none focus:ring-2 focus:ring-blue-500" />
        </div>
        <div>
            <label class="block text-lg font-semibold text-gray-700 mb-4">Preço</label>
            <input v-model="item.price" type="number" required
                class="w-full p-3 border border-gray-300 rounded focus:outline-none focus:ring-2 focus:ring-blue-500" />
        </div>
        <button type="submit"
            class="w-full bg-blue-600 text-white py-3 rounded hover:bg-blue-700 transition-colors mt-4">
            Adicionar novo produto da Apple
        </button>
    </form>
</template>