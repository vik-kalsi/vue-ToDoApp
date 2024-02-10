<script>
    export default {
        data() {
            return {
                tasks: [],
                additionalTask: null,
            }
        },

        methods: {
            addToDoList() {
                this.tasks.push(this.additionalTask);
                this.additionalTask = null;
                this.$refs.AddTaskBtn.classList.add("hidden");
            },
            showAddButton() {
                this.$refs.AddTaskBtn.classList.remove("hidden");
            }
        }
    };

</script>

<template> 
    <div class="my-6">
        <h1 class="text-5xl font-bold">To Do List</h1>

        <div>
            <input class="mt-3 text-black p-2 font-bold text-lg" type="text" placeholder="Type in the task" v-on:keydown="showAddButton" v-model="additionalTask"/>
            <button ref="AddTaskBtn" type="button" class="border-2 p-2 mx-3 font-bold text-lg hidden" v-on:click="addToDoList">Add</button>
        </div>


        <div class="border-2 mt-6 p-3">
            <ul class="space-y-3">
                <li class="text-lg" v-for="task in tasks"><input type="radio"> {{ task }}</li>
            </ul>
        </div>

        
    </div>
</template>