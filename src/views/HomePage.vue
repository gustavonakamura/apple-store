<template>
    <div>
        <Header />
        <h1>Bem-vindo à Loja Apple</h1>
        <Footer />
    </div>
</template>

<script>
import Header from "../components/AppHeader.vue";
import Footer from "../components/AppFooter.vue";

export default {
    components: { Header, Footer },
};
</script>