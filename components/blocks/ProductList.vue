<template>
    <div class="product-list" >
        <ul class="list" >
                <li class="item" :key="item" v-for="(item, idx) in items" :v-if="show">
                    <div class="item__img"></div>
                    <div class="item__wrapper">
                    <div class="item__name">{{item.nameProj}}</div>
                    <div class="item__desc">{{item.descProj}}</div>
                    <div class="item__price">{{item.proceProj}}</div>
                    <div class="delete" @click='deleteItem(idx)'></div>
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
import logo from '@/static/svg/delete.svg';
export default {
    props: ['items', 'deleteItem']
}
</script>

<style scoped>
    li, ul{
        list-style: none;
        margin: 0;
    }
    ul {
        display: flex;
        flex-wrap: wrap;
    }
    li{
        display: flex;
        flex-direction: column;
        background: white;
        border-radius: 5px;
        min-width: 230px;
        max-width: 230px;
        margin: 0 15px 10px 15px;
        box-sizing: content-box;
        position: relative;
        box-shadow: 5px 5px 10px rgba(0, 0, 0, .1);
        cursor: pointer;
    }
    .delete{
        display: none;
    }
    li:hover .delete{
        content: '';
        display: block;
        width: 32px;
        height: 32px;
        background: url('@/static/svg/delete.svg ') center no-repeat;
        position: absolute;
        border-radius: 10px;
        right: -10px;
        top: -10px;
        cursor: pointer;
    }
    div{
        color: #3F3F3F;
        border-radius: 5px 5px 0px 0px;
        
    }
    .item__wrapper{
        display: flex;
        flex-direction: column;
        justify-content: space-around;
        min-height: 150px;
    }
    .item__img, .item__name, .item__desc, .item__price{
        width: 100%;
    }
    .product-list{
        justify-self: start;
        min-width: 75%;
    }
    .item__img{
        height: 200px;
        background: grey;
    }
    .item__name{
        font-size: 20px;
        font-weight: 600;
        padding-left: 16px;
        width: 80%;
    }
    .item__desc{
        font-size: 16px;
        padding-left: 16px;
        word-wrap: break-word;
        width: 80%;
    }
    .item__price{
        font-size: 24px;
        padding-left: 16px;
        width: 80%;
    }
    @media screen and (max-width: 1000px){
        .item__name{
            font-size: 16px;
        }
        .item__desc{
            font-size: 12px;
        }
        .item__price{
            font-size: 20px;
        }
    }
</style>