
<template>



  <div class="container">
    <div class="row">
      <div class="col-12 text-white">
        <h1> To do List</h1>

        <br>

        <div class="row" >
          <div class="col-8" >
            <input class="form-control " type="text" v-model="task" @keyup.enter="addTask" placeholder="Enter your task...">
          </div>
          <div class="col-4">
            <p>Items listed {{tasks.length}}</p>
            <p></p>
          </div>

      </div>

      </div>

      <div class="col-12">
        <ul>
          <li class="tasks" v-for="(t, index) in tasks" :key="index" @click="removeTask(index)">{{t }}</li>

        </ul>
      </div>

    </div>
  </div>

</template>

<script>
export default {
name : 'ToDoList',
  data(){
    return{

      tasks:["go grocery shopping","work out","clean kitchen"],

      task: '',
    }
  },

  methods:{

  addTask(){
    this.tasks.push(this.task)
    this.task= ""
  },
  removeTask(index){
    this.tasks.splice(index,1)
  },
  completed(index){
    this.tasks.show(index)

  },

  }
}

</script>


<style>
.form-control{
  background: rebeccapurple !important;
  font-size: 25px !important;
  color: white !important;
  margin: 45px;
  padding: 20px !important;
}

.tasks{
list-style-type: none;
  border: 1px solid black;
  margin: 1px;
  padding: 10px;
  background: seagreen;
font-size: 25px !important;
color: white !important;


}
.tasks:hover{
  border: 1px solid black;
  font-size: 30px;
  color: rebeccapurple!important;
}
body{
  background-color: #2c3e50 !important;
  height: 100% !important;
}
h1{
  font-family: 'Amatic SC'!important;
  font-size: 50px !important;

}
.col-4{
  font-size: 25px !important;
  color: white !important;
  padding: 2px !important;
  padding-top: 50px !important;


}



</style>