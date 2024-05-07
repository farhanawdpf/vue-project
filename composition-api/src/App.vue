<script setup>
import { ref,onMounted, computed } from 'vue';
 
    const firstName = ref('x');
    const secondName = ref('y');

    const changeValue =()=>{ 
       firstName.value ="p";
       secondName.value="q"
    }
    // onMounted(() => {
    //   changeValue();
    // })
    
    // const fullName = computed({
    //   get() {
    //     return firstName.value + ' ' + secondName.value
    //   }
    // })
// export default { 
//   data(){
//     return{ 
//       firstName: "x",
//       secondName: "y"
//     }
//   },
//   methods:{ 
//     changeValue(){ 
//       this.firstName="p",
//       this.secondName="q"
//     },
//     // mounted() {
//     //   return this.changeValue();
//     // }

//     computed:{ 
//       fullName(){ 
//         return this.firstName + ' ' + this.secondName;
//       }
//     }
//   }
// }

</script>

<template>
  <div>
    <h1>Method,computed,mounted</h1> 
    </div><br>
  <div> 
    <h2>First Name:{{ firstName }}</h2>
    <h2>Second Name:{{ secondName }}</h2>
    <h2>Full Name:{{ fullName }}</h2>
    <button @click="changeValue">Add</button>
  </div>
</template>

<style>

</style>
