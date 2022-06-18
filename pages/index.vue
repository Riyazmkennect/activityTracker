<template>
  <main>
    <h1>Track your Activities</h1>
    <p>Hey user Hope you use this app in best way!</p>

    <div class="create-new">
      <input
        type="text"
        v-model="newTask"
        placeholder="hey user add your activity"
        @keypress.enter="addTask"
        
      />
      <button @click="addTask">Add</button>
    </div>

    <div class="tasks">
     <!-- {{$store.state.tasks}} -->
     <Task v-for="(task,i) in $store.state.tasks " :key="i" :task="task"/>
    </div>
    
  </main>

</template>

<script>
export default {
  // name: "IndexPage",
  data(){
    return {
      newTask:""
    }
   
  },
  methods:{
    addTask(){
      if(this.newTask){
        this.$store.commit('ADD_TASK',this.newTask)
        this.newTask=""
      }
    }
  }
};
</script>
