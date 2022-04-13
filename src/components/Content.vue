<template>

    <div class="container mt-5">

     <h1>Enter tasks to be done</h1>

    <form>

        <div class="form-group">
            <label for="action">Action</label>
            <input type="text" id="action" class="form-control mt-2">
        </div>

        <button class="btn btn-primary mt-3">Create a task</button>

    </form>

    <ul>
        <li v-bind:key="index" v-for="(task, index) in taskArray">
            <task :task="task"/>
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
