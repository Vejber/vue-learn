// здесь описывать наш компонент

<template>
    <div>
        It freaking works

        <button @click="addLike">
            Like
        </button>
        <button @click="addDislike">
            Dislike
        </button>
        <div> likes count: <strong>{{ likes }}</strong> </div>
        <div> dislikes count: <strong>{{ dislikes }}</strong> </div>
    </div>
</template>

<script>
//внутри - логика компонента
export default { //обязательная строка
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