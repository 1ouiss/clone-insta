<template>
    <div class="card">
        <div class="card-img">
            <img :src="post.imgUrl" alt="">
        </div>
        <h1>{{ post.title }}</h1>
        <p>{{ post.content }}</p>
        <div>
            <button v-on:click="() => this.$emit('like', post)">
                <span>{{ post.like }} {{ post.like > 1 ? 'Likes' : 'Like' }}</span>
            </button>
        </div>
    </div>
</template>

<script>
export default{
    name: 'CardComponent',
    props:['post']
}
</script>

<style scoped>
.card {
    display: flex;
    flex-direction: column;
    width: 400px;
    height: auto;
    align-items: center;
    border-radius: 6px;
    box-shadow: 0px 0px 4px 0px #000000;
    margin: 20px;
    padding: 10px;
}

.card-img{
    width: 200px;
    height: 200px;
}

.card-img img{
    width: 100%;
    height: 100%;
}

button{
    background-color: #00bcd4;
    border: none;
    border-radius: 6px;
    color: white;
    padding: 10px;
    margin: 10px;
    cursor: pointer;
}

</style>