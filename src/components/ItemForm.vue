<template>
    <div class="container">
        <div class="form-card">
            <h1 class="form-title">Adicionar Novo Produto da Apple</h1>
            <form @submit.prevent="addItem" class="form">
                
                <div class="form-group">
                    <label class="form-label">Nome do Produto</label>
                    <input 
                        v-model="item.name" 
                        type="text" 
                        required
                        class="form-input"
                        placeholder="Ex: iPhone 16 Pro"
                    />
                </div>
                
                <div class="form-group">
                    <label class="form-label">Descrição</label>
                    <textarea 
                        v-model="item.description" 
                        required 
                        class="form-input"
                        placeholder="Descrição do produto"
                        rows="3"
                    ></textarea>
                </div>
                
                <div class="form-group">
                    <label class="form-label">Preço</label>
                    <input 
                        v-model="item.price" 
                        type="number" 
                        required
                        min="0"
                        class="form-input"
                        placeholder="R$ 0,00"
                    />
                </div>
                
                <button type="submit" class="form-button">
                    Adicionar Produto
                </button>
            </form>
        </div>
    </div>
</template>

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

<style scoped>
.container {
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: #f3f4f6;
    padding: 20px;
}
.form-card {
    width: 100%;
    max-width: 500px;
    background-color: #ffffff;
    padding: 30px;
    border-radius: 8px;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
}
.form-title {
    font-size: 24px;
    font-weight: 700;
    text-align: center;
    color: #333333;
    margin-bottom: 20px;
}
.form-group {
    margin-bottom: 16px;
}
.form-label {
    display: block;
    font-size: 16px;
    font-weight: 500;
    color: #555555;
    margin-bottom: 8px;
}
.form-input {
    width: 100%;
    padding: 10px;
    border: 1px solid #cccccc;
    border-radius: 5px;
    font-size: 16px;
    color: #333333;
    box-sizing: border-box;
    transition: border-color 0.3s ease;
}
.form-input:focus {
    border-color: #3b82f6;
    outline: none;
}
.form-button {
    width: 100%;
    padding: 12px;
    font-size: 18px;
    font-weight: 600;
    color: #ffffff;
    background-color: #3b82f6;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s ease, transform 0.3s ease;
}
.form-button:hover {
    background-color: #2563eb;
}

.form-button:active {
    transform: scale(0.98);
}
</style>