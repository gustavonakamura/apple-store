<template>
    <header class="header">
        <nav class="nav">
            <router-link to="/" class="logo">
                Loja Apple
            </router-link>
            <div class="nav-links">
                <router-link to="/add-item" class="nav-link">
                    Cadastrar Produtos
                </router-link>
                <router-link to="/items" class="nav-link">
                    Listar Produtos
                </router-link>
            </div>
        </nav>
    </header>
</template>

<script>
export default {
    name: "AppHeader",
};
</script>

<style scoped>
.header {
    padding: 16px 0;
}
.nav {
    display: flex;
    align-items: center;
    justify-content: space-between;
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 24px;
    width: 100vw;
}
.logo {
    font-size: 1.5rem;
    font-weight: bold;
    text-transform: uppercase;
    letter-spacing: 1px;
    transition: color 0.3s ease;
    text-decoration: none;
}
.nav-links {
    display: flex;
    gap: 24px;
}
.nav-link {
    font-size: 1.125rem;
    text-decoration: none;
    transition: color 0.3s ease;
    padding: 8px 12px;
}
.nav-link:hover {
    color: #9ca3af;
}
</style>