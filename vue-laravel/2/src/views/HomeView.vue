<template>
  <main>
     <div> 
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
                <th>SL</th>
                <th>Name</th>
                <th>Contact</th>
                <th>Email</th>
                <th>Action</th>
              </tr>
            </thead>
            <tbody> 
              <tr> 
                <td>01</td>
                <td>Mila</td>
                <td>1231231</td>
                <td>er@gmail.com</td>
                <td>
                  <button>Edit</button>
                  <button>Delete</button>
                  <button>view</button>
                </td>
              </tr>
              <tr> 
                <td>01</td>
                <td>Mila</td>
                <td>1231231</td>
                <td>er@gmail.com</td>
                <td>
                  <button>Edit</button>
                  <button>Delete</button>
                  <button>view</button>
                </td>
              </tr>
              <tr> 
                <td>02</td>
                <td>Mila</td>
                <td>1223431231</td>
                <td>pr@gmail.com</td>
                <td>
                  <button>Edit</button>
                  <button>Delete</button>
                  <button>view</button>
                </td>
              </tr>
              <tr> 
                <td>03</td>
                <td>Shila</td>
                <td>1231231</td>
                <td>er@gmail.com</td>
                <td>
                  <button>Edit</button>
                  <button>Delete</button>
                  <button>view</button>
                </td>
              </tr>
            </tbody>
          </table>
        </div>

      </div>
     </div>
  </main>
</template>
<script> 
 export default { 
  name: 'home',
  data() {
    return {
      home: '',
    };
  },
 }
</script>