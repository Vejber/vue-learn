// здесь описывать наш компонент

<template>
    <div>
        <!-- homework 1 -->
        <!-- task1
        Создать кнопку "Перевернуть". При клике на кнопку текст кнопки, должен перевернуться и отобразиться в обратном порядке.-->
        <button @click="turnAround">{{ message }}</button>

        <!-- task 2
        Есть список элементов. Пользователь может добавлять новые элементы списка с текстом “Новый элемент списка” нажав на кнопку "Добавить". 
            task 3
            * При клике на элемент списка он должен быть удален. (по желанию)
        -->

        <ul>
            <li v-for="(text, index) in liArray"  @click="deleteLi(index)" :key="text.id"> {{ text.text }} </li>
        </ul>
        <button @click="addLi">Добавить</button>
    </div>
</template>

<script defer>
//внутри - логика компонента
import { onMounted, onUnmounted } from "vue";
export default { //обязательная строка
    data() {
        return {
            message: 'Перевернуть',
            liArray:[
                {text: 'Element'},
                {text: 'Element'},
                {text: 'Element'},
            ],
            standartText: 'New element', 
        }
    },

    methods:{
        turnAround(){
            this.message = this.message
            .split('')
            .reverse()
            .join('')
        },

        addLi(){
            this.liArray.push({text:this.standartText});
            
            //also works
            // this.ul = document.querySelector('ul');
            // console.log(this.ul);
            // this.ul.insertAdjacentHTML("beforeend",'<li @click="deleteLi">Новый элемент списка, можно удалить по клику</li>');  
            // console.log(this.liArray);
        },

        deleteLi(index){
            this.liArray.splice(index, 1);

            //doesnt work
            // this.li = EventTarget;
            // console.log(this.li);
        }

    }
}
</script>

<style></style>