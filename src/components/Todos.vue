<template>
<div>
    <h3 class="text-primary text-center">All todos</h3>
    <div class="container">
        <div class="row">
            <AddTodos></AddTodos>
        </div>
        <div class="row">
            <div class="col-md-4 my-4" v-for="todo in myTodos" :key="todo.id">
                <b-card bg-variant="primary" text-variant="white" class="text-center">
                    <b-card-text class="d-flex justify-content-between"><span>{{todo.title}}</span>
                    <span @click="deleteTodo(todo.id)"><b-icon icon="trash-fill" variant="danger"></b-icon></span></b-card-text>
                  </b-card>
            </div>
        </div>
    </div>
    </div>    
</template>

<script>
import AddTodos from './AddTodos'
import {mapActions, mapGetters} from 'vuex';
export default {
  components: { AddTodos },
    computed:mapGetters(["myTodos"]),
    methods:mapActions(['getTodos',"deleteTodo"]),
    mounted(){
        this.getTodos();
    }
}
</script>

<style>

</style>