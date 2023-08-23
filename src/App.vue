// здесь описывать наш компонент

<template>
        <HeaderTemplate></HeaderTemplate>
        
</template>

<script>
import HeaderTemplate from "@/components/HeaderTemplate.vue";
//внутри - логика компонента
export default { //обязательная строка
    components:{
        HeaderTemplate,
    },
    data() {
        return {
            likes: 0,
            dislikes: 5,
        }
    },

    methods:{
        addLike(){
            this.likes += 1;
        },
        addDislike(){
            this.dislikes += 1;
        }
    }
}

</script>

<style></style>