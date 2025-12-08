<script>
import axios from "axios";
export default {
    data() {
        return {
            tasks: [],
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
    },
};
</script>

<template>
<div>
    <h1>Vue + Laravel API CRUD</h1>
    <br>
    <br>
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
                    <button class="btn btn-danger">Delete</button>
                </td>
            </tr>

        </tbody>
    </table>
</div>
</template>

<style>
  
</style>
