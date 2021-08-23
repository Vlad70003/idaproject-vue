<template>
    <section class="main-section">
        <div class="main-section__wrapper">
            <header class="header">
                <Header />
            </header>
            <div class="section-content" v-if='items.length !== 0'>
                <Form :addItems="addItems"/>
                <ProductList :deleteItem="deleteItem" :items="items"/>
            </div>
            <div class="section-content__null" v-if='items.length === 0'>
                <Form :addItems="addItems"/>
                <div class="message">Список товаров пуст. Заполните форму и добавьте товар!</div>
            </div>
        </div>
    </section>
</template>

<script>
import Header from '@/components/blocks/Header.vue';
import Form from '@/components/blocks/Form.vue';
import ProductList from '@/components/blocks/ProductList'
export default {
    components: {
        Header,
        Form,
        ProductList,
    },
    methods: {
        addItems: function(name, desc, link, price){
            if(name.length !== 0 && link.length !== 0 && price.length !== 0){
                this.items.push({
                nameProj: name,
                descProj: desc,
                linkProj: link,
                proceProj: price,
            });
            }
        },
        deleteItem: function(index){
            this.items.splice(index, 1);
        },
    },
    data(){
        return {
            items: [],
            show: true,
        }
}
}

</script>

<style scoped>
    .section-content{
        display: flex;
        padding: 0 20px;
        justify-content: space-between;
    }
    .main-section__wrapper{
        max-width: 1500px;
        min-width: 1500px;
    }
    .main-section{
        display: flex;
        justify-content: center;
    }
    .section-content__null{
        display: flex;
        padding: 0 20px;
    }
    .message{
        font-size: 20px;
        font-weight: 600;
        margin: 0 auto;
    }
    @media screen and (max-width: 1600px){
        .main-section__wrapper{
        max-width: 1000px;
        min-width: 1000px;
    }
    @media screen and (max-width: 1000px){
        .main-section__wrapper{
        max-width: 850px;
        min-width: 850px;
    }
    }
    }
</style>