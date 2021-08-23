<template>
    <header class="header">
        <h2 class="title">Добавление товара</h2>
        <select name="" id="" class="filter-product">
            <option value="hide">По умолчанию</option>
        </select>
    </header>
</template>

<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Source+Sans+Pro&display=swap');
    *{
        font-family: 'Source Sans Pro', sans-serif;
    }
    header{
        display: flex;
        justify-content: space-between;
        padding: 20px;
        font-weight: 600;
        align-items: center;
        font-size: 28px;
    }
    select{
        border: none;
        border-radius: 5px;
        box-shadow: 2px 2px 10px rgba(0,0,0, .5);
        height: 50px;
        padding: 5px 10px;
        outline: none;
        size: 12px;
        color: grey;      
    }
</style>