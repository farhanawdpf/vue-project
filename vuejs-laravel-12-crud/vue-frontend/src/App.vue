<script>
import axios from "axios";
export default {
    data() {
        return {
            tasks: [],
            newCategory: {
                title: "",
                description: ""
            },
        };
    },

    mounted() {
        this.getCategory();
    },
    methods: {
        getCategory() {
            axios.get('http://127.0.0.1:8000/api/category')
                .then((res) => {
                    this.tasks = res.data.data
                    console.log(res.data.data)
                })

        },
        // create category
        async createCategory() {
            const res = await axios.post("http://127.0.0.1:8000/api/category", this.newCategory);
            this.tasks.unshift(res.data.data);
            this.newCategory = {
                title: "",
                description: ""
            };
        },

        // createCategory() {
        //     axios.post("http://127.0.0.1:8000/api/category", this.newCategory)
        //         .then((response) => {
        //             this.newCategory = {
        //                 title: "",
        //                 description: ""
        //             }
        //             this.getCategory()
        //             this.newCategory = {
        //                 title: "",
        //                 description: ""
        //             }
        //             console.log(response)

        //         });
        // },

        async deleteTask(id) {
            await axios.delete(`http://127.0.0.1:8000/api/category/${id}`);
            this.tasks = this.tasks.filter((t) => t.id !== id);
        },

    },
};
</script>

<template>
<div>
    <h1>Vue + Laravel API CRUD</h1>
    <!-- Add category -->
    <form @submit.prevent="createCategory">
        <input v-model="newCategory.title" placeholder="Title" /><br />
        <input v-model="newCategory.description" placeholder="Description" /><br />
        <button>Add</button>
    </form>

    <table class="table table-hover">
        <thead>
            <tr>
                <th scope="col">SL</th>
                <th scope="col">Category Name</th>
                <th scope="col">Description</th>
                <th scope="col">Action</th>
            </tr>
        </thead>
        <tbody v-for="(d, i) in tasks" :key="i">
            <tr>
                <td scope="row">{{ i + 1 }}</td>
                <td>{{ d.title }}</td>
                <td>{{ d.description }}</td>
                <td width="150px">
                    <button class="btn btn-primary">Edit</button>
                    <button class="btn btn-danger" @click="deleteTask(d.id)">Delete</button>
                </td>
            </tr>

        </tbody>
    </table>
</div>
</template>

<style>
  
</style>
