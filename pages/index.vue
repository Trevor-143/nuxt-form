<template>
    <div class="nuxtForm">
        <form @submit.prevent="sendForm" >
            <input type="text" placeholder="first name" v-model="formContent.firstName" id="formField" >
            <input type="text" placeholder="last name" v-model="formContent.lastName" id="formField" >
            <input type="text" placeholder="point one" v-model="formContent.point[0]" id="formField" >
            <input type="text" placeholder="point two" v-model="formContent.point[1]" id="formField" >
            <textarea cols="30" rows="5" placeholder="message" v-model="formContent.message" id="formField" ></textarea>
            <button type="button" @click="sendForm" >Submit</button>
        </form>        
    </div>
</template>

<script setup>

const formContent = ref({
    firstName: '',
    lastName: '',
    point: [
        '',''
    ],
    message: ''
})

const sendForm = () => {
    console.log(formContent.value)
    const fields = document.querySelectorAll('#formField')
    fields.forEach(function(field) {
        field.value = ''       
    })
}

</script>

<style scoped>
.nuxtForm {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100vh;
}
form {
    max-width: 500px;
    width: 100%;
    padding: 2rem;
    border-radius: 1rem;
    display: flex;
    flex-direction: column;
    background-color: #eee;
}
input, textarea {
    padding: 1rem;
    width: 100%;
    resize: none;
    border: none;
    outline: none;
    margin-bottom: 0.5rem;
    border-radius: 0.5rem;
}
button {
    background-color: rgb(19, 19, 51);
    color: #fff;
    font-weight: 700;
    padding: 0.5rem 1rem;
    border-radius: 0.5rem;
    border: none;
    cursor: pointer;
    width: fit-content;
}

</style>