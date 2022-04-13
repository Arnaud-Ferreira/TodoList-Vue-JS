<template>

    <div class="container mt-5">

     <h1>Enter tasks to be done</h1>

    <form>

        <div class="form-group">
            <label for="action">Action</label>
            <input v-model="formData.task" type="text" id="action" class="form-control mt-2">
        </div>

        <button v-on:click.prevent="createTask" class="btn btn-primary mt-3">Create a task</button>

    </form>

    <ul>
        <li v-bind:key="index" v-for="(task, index) in taskArray">
            <task :id="index" :task="task" :remove="remove"/>
        </li>
    </ul>

    </div>
</template>



<script>

    import Task from './Task.vue';

    export default {
        name: 'ContenuComp',
        data(){
            return {
                formData: {
                    task: ''
                },
                taskArray: ['JavaScript', 'Learn Vue', 'Learn Python', 'Master React']
            }
        },
        methods: {
            createTask: function() {
                this.taskArray.push(this.formData.task)
                this.formData.task = ''
            },
            remove: function(event) {
                // deletes the id of the parent of the targeted element
                this.taskArray.splice(event.target.parentNode.id, 1)
            }
        },
        components: {
            'task': Task
        }
        
    }

</script>

<style scoped>

    h1 {
        margin-top: 100px !important;
    }
    ul {
        margin-top: 1rem;
        list-style-type: none;
        padding: 0;
    }

</style>
