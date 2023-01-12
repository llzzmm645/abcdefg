<template>
    <div id="myapp">
        <form  @submit.prevent="newpeople">
            <fieldset>
                <legend>New People</legend>
                名字:<input type="text" v-model="thename"/>
                <br>
                年龄:<input type="text" v-model="theage"/>
                <br>
                <input type="submit" value="添加"/>
            </fieldset>
        </form>
        <select>
            <option v-for="(people,index) in peoples" :key="index" :value="index">
                {{index}}:{{people.name}}-{{people.age}}
            </option>
        </select>
        <form @submit.prevent="deletepeople">
            <fieldset>
                <legend>Delete People</legend>
                序号:<input type="text" v-model="theid"/>
                <br>
                <input type="submit" value="删除"/>
            </fieldset>
        </form>
    </div>
</template>
<script>
export default {
    data(){
        return {
            peoples:[],
            thename:"",
            theage:10,
            theid:0
        }
    },
    methods:{
        newpeople(){
            this.peoples.push({
                name:this.thename,
                age:this.theage
            })
        },
        deletepeople(){
            this.peoples.splice(this.$data.theid,1)
        }
    }
}
</script>
<style>
select{
    width:5cm;
    margin-left:0.5cm;
}
form{
    width:5cm;
    margin-top:0.5cm;
    margin-bottom:0.5cm;
    margin-left:0.5cm;
}
div #myapp{
    border-style:solid;
    width:10cm;
    margin-bottom:0.5cm;
    border-width:4px;
    border-color:rgb(255,126,0);
}
</style>