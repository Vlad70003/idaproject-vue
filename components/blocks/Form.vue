<template>
    <form action="" class="form">
        <label for="prod-name" >Наименование товара<span class="red">*</span></label>
        <input type="text" name="prod-name" id="prod-name" placeholder="Введите наименование товара" v-model="name" :class="error && name.length == 0 && 'error'" maxlength="15">
        <label for="prod-desc">Введите описание товара</label>
        <textarea name="prod-desc" id="prod-desc" cols="30" rows="10" maxlength="50" placeholder="Введите описание товара" v-model="desc"></textarea>
        <label for="prod-link">Ссылка на изображение товара<span class="red">*</span></label>
        <input type="text" name="prod-link" id="prod-link" placeholder="Введите ссылку" v-model="link" :class="error && link.length == 0 && 'error'">
        <label for="prod-price">Цена товара<span class="red">*</span></label>
        <input type="text" name="prod-price" id="prod-price" placeholder="Введите цену" v-model="price" :class="error && price.length == 0 && 'error'" maxlength="10">
        <input type="submit" value="Добавить товар" :class="{'button': true, 'button-available': name.length !== 0 && link.length !== 0 && price.length !== 0}"  @click.prevent="addItems(name, desc, link, price), remove()">
    </form>
</template>

<script>
export default {
    props: ['numbers', 'addItems'],
    data(){
        return{
            name: '',
            desc: '',
            link: '',
            price: '',
            error: false,
        }
    },
    methods: {
        remove: function(){
            if(this.name.length !== 0 && this.link.length !== 0 && this.price.length !== 0){
                this.name = '';
                this.desc = '';
                this.link = '';
                this.price = '';
                this.error = false;
            } else{
                this.error = true;
            }
        }
    }

}

</script>

<style scoped>
    form{
        min-width: 22%;
        display: flex;
        flex-direction: column;
        padding: 20px;
        box-shadow: -5px 5px 20px rgba(0,0,0, .5);
        background: white;
        border-radius: 10px;
        max-height: 20%;
        align-self: flex-start;
    }
    textarea{
        resize: none;
    }
    label{
        font-size: 10px;
        color: #49485E;
        padding: 15px 5px 5px 5px;
    }
    input, textarea{
        padding: 10px 15px;
        border: none;
        outline: none;
        box-shadow: 2px 2px 5px rgba(0,0,0, .3);
        border-radius: 5px;
        refont-size: none;
        font-size: 12px;
        word-wrap: break-word;
    }
    .button{
        margin: 20px 0;
        background: #EEEEEE;
        color: #B4B4B4;
        font-weight: 600;
        cursor: pointer;
    }
    .button-available{
        color: white;
        background: #7BAE73;
    }
    .red{
        color: #FF8484;
        font-weight: 600;
    }
    .error{
        box-shadow: 2px 2px 5px rgba(255, 2, 2, 0.5);
    }
    @media screen and (max-width: 1600px){
        form{
        min-width: 33%;
    }
    }
    @media screen and (max-width: 1000px){
        form{
            min-width: 25%;
        }
        label{
            font-size: 10px;
        }
    }
    @media screen and (max-width: 900px){
        form{
            margin: 0 auto;
            margin-bottom: 50px;  
        }

    }
        
</style>