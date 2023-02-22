<template>
    <main class= " min-h-screen bg-slate-600">

    <nav class=" flex justify-evenly mx-auto p-3 bg-slate-700">
        <span class=" ml-6  text-3xl font-bold text-orange-500">PhoneBook</span>   
    </nav>

<div class="  m-20 mx-auto px-10 py-8 flex justify-center items-center">
    <form @submit.prevent="handleSubmit" class=" border flex flex-col  mx-auto justify-center items-center p-1 max-w-lg 
    bg-slate-400 text-black rounded-md"  >
    
    <div class=" flex-col flex">
        <label> full name</label>
     <input v-model="fullName" type="text" class=" px-6     m-2 py-2 rounded-md mx-auto p-2" required placeholder="Enter your full name">
    </div>
     <div class="flex-col flex">
        <label> Phone number</label>
        <input v-model=" phoneNumber" type="text" class=" px-6  m-2 py-2 rounded-md mx-auto p-2 " required placeholder="Enter your phone number">
    </div>
   <div class=" m-5 flex flex-row justify-center items-center gap-x-5">
        <button class=" rounded-md py-2 px-2  text-orange-500 bg-slate-700">Add</button>
        
    </div>
</form>
    </div>
            
<div 
 class=" flex flex-col justify-center items-center mx-auto p-2 max-w-lg  bg-orange-500 text-black rounded-md  border-emerald-50 border">        
 <legend>Output</legend>
 
      
  
    <fieldset class=" flex justify-center items-center  flex-col">
        <div v-for="phone in books" :key="phone">
            {{phone.fullName}}
           {{phone.phoneNumber}}
            <button  v-on:click="remove(phone.id)" class=" rounded-md py-2 px-2 text-orange-500 bg-slate-700">delete</button>
        </div>
       
      
       
         
    </fieldset>
</div>
    </main>
</template>
<script>
export default {
    
    data(){
        return{
          data:false,
          phoneNumber:'',
          fullName:'',
         books:[
            {
                id:1,
         fullName:'francis',
          phoneNumber:'0769554443'
            },
            {
                id:2,
         fullName:'francis',
          phoneNumber:'0769554443'
            }
         ]
        }
    },
    methods:{
     handleSubmit(){
      this.books.push({fullName:this.fullName,phoneNumber:this.phoneNumber})  
    },
    remove(phone) {  
      this.books.splice(this.books.indexOf(phone));
    },
}

}
</script>