<script>
export default {
  // Properties returned from data() become reactive state
  // and will be exposed on `this`.
  data() {
    return {
      count: 0,
      text:"This is home page",
      numbers:34,
      cars:[2,4,5,7],
      object:{ 
        name:"BMW",
        model:"3064"
      }
    }
  },

  // Methods are functions that mutate state and trigger updates.
  // They can be bound as event handlers in templates.
  methods: {
       increment(){
            this.count++;
        },
        decrement(){
            this.count--;
        },
      
        handleKeyup(e) {
            this.name = e.target.value;
        },
        fromsubmitted (e) { 
            console.log("from submitted");
            e.preventDefault();
        }
  },

   computed: {
        gettitle(){ 
            return this.title;
          }
    },

    watch: { 
       mobile(newvalue, oldvalue){ 
        console.log(newvalue);
        if (isNaN(newvalue)) { 
            alert("Please enter number");
            this.mobile = oldvalue;
        }
         if (newvalue.length == 11) { 
            alert("Please enter 11 number");
         }

        },
  mounted() {
    console.log(`The initial count`)
  },
}
}
</script>

<template>
    <div>
           <p>{{title}}</p>
        <p>{{gettitle}}</p>

        <button @click="count++">{{ count }}</button>

        <button v-on:click="increment">increment</button>
        <button v-on:click="decrement">Decrement</button>



        <form @submit.prevent="fromsubmitted">
            <h3>Enter your name</h3>
            <input type="text" v-model="name" />
            <p> welcome {{name}} !</p>
            <h3>Enter your Mobile Number</h3>
            <input type="text" v-model="mobile" />
             <p> welcome {{mobile}} !</p>    
            <button type="submit">OK</button>
        </form>
        <hr>
    </div>
</template>