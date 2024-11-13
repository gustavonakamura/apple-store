<template>
    <div class="card">
        <h3 class="card-title">{{ item.name || 'Produto Sem Nome' }}</h3>
        <p class="card-description">{{ item.description || 'Nenhuma descrição disponível' }}</p>
        <p class="card-price">R$ {{ item.price != null ? item.price.toFixed(2) : '0.00' }}</p>
        <button @click="$emit('delete-item', index)" class="card-button">Excluir</button>
    </div>
</template>

<script>
export default {
    name: "ItemCard",
    props: {
        item: {
            type: Object,
            default: () => ({ name: '', description: '', price: 0 })
        },
        index: {
            type: Number,
            required: true
        }
    }
};
</script>

<style scoped>
/* Card styling */
.card {
    background-color: #ffffff;
    border-radius: 8px;
    padding: 20px;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    min-height: 50px;
}



/* Card title styling */
.card-title {
    font-size: 1.5rem;
    font-weight: bold;
    color: #333333;
    margin-bottom: 8px;
    text-align: center;
}

/* Card description styling */
.card-description {
    font-size: 1rem;
    color: #666666;
    margin-bottom: 12px;
    text-align: center;
}

/* Card price styling */
.card-price {
    font-size: 1.25rem;
    font-weight: bold;
    color: #3b82f6;
    margin: 16px 0;
    text-align: center;
}

/* Button styling */
.card-button {
    background-color: #e53e3e;
    color: #ffffff;
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
    font-weight: 600;
    cursor: pointer;
    transition: background-color 0.3s ease, transform 0.3s ease;
    align-self: center;
}

/* Hover and active effect for button */
.card-button:hover {
    background-color: #c53030;
}

.card-button:active {
    transform: scale(0.98);
}
</style>
