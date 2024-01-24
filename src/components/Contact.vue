<script setup>

import { reactive } from 'vue';


var formInput={
    name:"",
    email:"",
    message:""
}

var confirmSendMessage= reactive({val: ""});

const handleSubmit=async ()=>{

  if(formInput.message!=="" && formInput.email!=="" ){
    fetch("https://formsubmit.co/ajax/gradiayoub3@gmail.com", {
    method: "POST",
    headers: { 
        'Content-Type': 'application/json',
        'Accept': 'application/json'
    },
    body: JSON.stringify({...formInput})
    }).then(response => response.json()).then((data) => {
        if(data.success==="true"){
          confirmSendMessage.val="true"
        }else{
          confirmSendMessage.val="false"
        }
    })
  }else{
    confirmSendMessage.val="false"
  }
}

</script>



<template>

     <!-- contact -->
   <section id="contact" x-data="{contact:contact }" class="container mb-5">
    <h1 class="text-center sectionTitle" data-aos="fade-up">CONTACT </h1>

    <form @submit.prevent="handleSubmit" class="container col-10 col-lg-8 mx-auto">
    
      <div v-show="confirmSendMessage.val==='true'"  class="alert alertSuccess" role="alert">
        <h3>Thank you!</h3> 
        Your message has been successfully sent. We will contact you very soon!
      </div>
      <div v-show="confirmSendMessage.val==='false'" class="alert alert-danger" role="alert">
        oops! something happened wrong, please try again
      </div>
    
        <input type="text" v-model="formInput.name" id="name" class="form-control mb-3" placeholder="full name" data-aos="fade-up">
        <input type="email" v-model="formInput.email" id="email" class="form-control mb-3" placeholder="email" data-aos="fade-up">
        <textarea class="form-control" v-model="formInput.message" id="message" placeholder="message" rows="3" data-aos="fade-up"></textarea>
        <button class="btn btn-light mt-3" type="submit" data-aos="fade-up"> Send</button>

    </form>

  </section>
</template>