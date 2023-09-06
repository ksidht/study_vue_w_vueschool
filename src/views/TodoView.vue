<template>
  <div class="w-1/4 mx-auto">
    <h1>Todoist</h1>
    <Form :validation-schema="simpleValidation" @submit="handleSubmit">
    <Field 
      type="text" 
      name="email" 
      class="block w-full rounded-md border-0 py-1.5 pl-7 pr-20 text-gray-900 ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
      />
      <ErrorMessage name="email" />
      
      <Field 
      type="text" 
      name="password" 
      class="block w-full rounded-md border-0 mt-5 py-1.5 pl-7 pr-20 text-gray-900 ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
      />
      <ErrorMessage name="password" />      

      <br/>
      <button 
        type="submit"
        class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 mr-2 mb-2 mt-5 dark:bg-blue-600 dark:hover:bg-blue-700 focus:outline-none dark:focus:ring-blue-800"
      >Submit</button>
    </Form>
  </div>
</template>

<script setup>

import { Form, Field, ErrorMessage } from "vee-validate";


function validateSidname(value) {
  console.log(value)
  console.log(!value)

  if (!value) {
    return 'This field is required';
  }

  // return true;
}

function handleSubmit() {
  console.log('handle submit')
}

const simpleValidation = {
  email(value) {
    if(!value) {
      return 'This email is required'
    }
  },
  password(value) {
    if(!value) {
      return 'This password is required'
    }
  }
} 

</script>