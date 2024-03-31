<template>
    <div class="game-box">
        <ul>
            <li v-for="item,index in gameMap" :key="index" :class="{snakehead:item.isHead,snakebody:item.isBody}"></li>
        </ul>
    </div>
</template>
<script>
export default{
    data(){
        return{
            gameMap:[],
            snakeArry:[200,201,202,203]
        }
    },
    created(){
        for(let i=0; i<600; i++)
        this.gameMap.push({})

        this.createSnake()

        setInterval(()=>{

        },1000)
    },
    methods:{
        createSnake(){
            this.gameMap[this.snakeArry[this.snakeArry.length-1]].isHead = true
            for(let i=0;i<this.snakeArry.length-1;i++)
            this.gameMap[this.snakeArry[i]].isBody = true
        }
    }
    
}
</script>
<style>
.game-box{
    height: 600px;
    width: 400px;
    margin: 0 auto;
    border: 1px solid rgba(255, 255, 255, 0.2);
    background-color: rgb(28, 27, 27);
}
ul{
    padding: 0;
    margin: 0;
    display: grid;
    grid-template-columns: repeat(20,20px);
    grid-template-rows: repeat(30,20px);
}
li{
    list-style-type: none;
    height: 20px;
    width: 20px;
    
}
.snakehead::before{
content: "";
display: block;
width: 20px;
height: 20px;
background-color: rgb(226, 59, 59);
border:  solid 1.5px white;
}
.snakebody::before{
content: "";
display: block;
width: 20px;
height: 20px;
background-color: rgb(133, 202, 29);
border: solid 1.5px white;
}
</style>