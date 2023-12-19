<template>
  <main>
     <div class="container"> 
      <div class="card" style="width: 95%; padding:5%">
        <div class="card-header"> 
         <h4> Employee
          <router-link to="/about" class="btn btn-primary float-end">
            Add Employee
          </router-link>
         </h4>
        </div> 
        <div class="card-body"> 
          <table class="table table-success table-striped"> 
            <thead> 
              <tr> 
                <th scope="col">ID</th>
                <th scope="col">Employee Name</th>
                <th scope="col">Address</th>
                <th scope="col">Mobile</th>
                <th scope="col">Option</th>
              </tr>
            </thead>
            <tbody> 

              <tr v-for="employee in result" v-bind:key="employee.id">
          
                <td>{{ employee.id }}</td>
                <td>{{ employee.name }}</td>
                <td>{{ employee.address }}</td>
                <td>{{ employee.mobile }}</td>
                <td>
                  <button type="button" class="btn btn-warning" @click="edit(employee)">Edit</button>
                  <button type="button" class="btn btn-danger"  @click="remove(employee)">Delete</button>
                </td>
              </tr>
              <!-- <tr v-for="(student,index) in this.students" :key="index"> 
                <td>{{ student.id }}</td>
               <td> 
                <router-link to="/" class="btn btn-sucess">
                  edit
                </router-link>
                <button type="button" class="btn btn-danger">Delete</button>
               </td>
                
              </tr> -->
            </tbody>
          </table>
        </div>

      </div>
     </div>
  </main>
</template>
<script> 
import axios from 'axios'
 export default { 
  name: 'home',
  data() {
    return {
      result: []
    }
  },
  // created() { 
  //       this.getEmployees();
  //   },
  mounted(){ 
    this.getEmployees();
    console.log("mounted() called.......");
  },

  methods: {
    // getEmployees(){ 
    //   axios.get('http://127.0.0.1:8000/api/employees').then(res => { 
    //     this.employee = res.data.employees
    //     // console.log(res)
    //   });
    // }

    getEmployees()
           {
                 var page = "http://127.0.0.1:8000/api/employees";
                 axios.get(page)
                  .then(
                      ({data})=>{
                        console.log(data);
                        this.result = data;
                      }
                  );
           }
  },
 }
</script>