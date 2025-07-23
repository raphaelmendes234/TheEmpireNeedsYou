<template>
  <form @submit="handleSubmit" id="contactForm" class="contact-form">
    <p v-if="errorMessage" class="form-message">{{ errorMessage  }}</p>
    <div class="names">
      <div class="input-wrapper">
        <label for="first-name" class="required">Prénom</label>
        <input type="text" id="first-name" name="first-name" v-model="firstName">
      </div>

      <div class="input-wrapper">
        <label for="last-name" class="required">Nom</label>
        <input type="text" id="last-name" name="last-name" v-model="lastName">
      </div>
    </div>

    <div class="input-wrapper">
      <label for="planet" class="required">Planète d'origine</label>
      <input type="text" id="planet" name="planet" v-model="planet">
    </div>

    <div class="input-wrapper">
      <label for="specialite" class="required">Spécialité</label>
      <select name="specialite" id="specialite" v-model="specialite">
        <option value="hacking">Hacking</option>
        <option value="espionage">Espionnage</option>
        <option value="lightsaber">Sabre laser</option>
        <option value="telekinesis">Télékinésie</option>
      </select>
    </div>

    <div class="input-wrapper">
      <label for="message" class="required">Message de motivation</label>
      <textarea id="message" name="message" rows="5" cols="30" v-model="message"></textarea>
    </div>

    <button type="submit" class="submit-button">Soumettre mon allégeance</button>

    <p v-if="confirmationMessage" class="form-message">{{ confirmationMessage }}</p>
  </form>


</template>

<style scoped>
.contact-form{
    display: flex;
    flex-direction: column;
    gap: 1rem;
}
.names{
    display: flex;
    flex-direction: column;
    gap: 1rem;
}
.input-wrapper{
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
}
input[type="text"], select, textarea{
    padding: 1rem;
    font-family: 'Orbitron';
    font-size: 1rem;
    color: var(--color-text);
    border: 1px solid var(--color-text);
    background: linear-gradient(200deg,rgba(var(--color-background-rgb), 0) 50%, rgba(110, 110, 110, 0.5) 100%);
    transition: all 0.4s ease-in-out;
}
input[type="text"]:hover, select:hover, textarea:hover{
    -webkit-box-shadow: 0px 0px 10px 0px var(--color-text); 
    box-shadow: 0px 0px 10px 0px var(--color-text);
}
input[type="text"]:focus, select:focus, textarea:focus{
    outline: none;
    border-color: var(--color-primary);
    background: linear-gradient(200deg,rgba(var(--color-background-rgb), 0) 50%, rgba(255, 0, 0, 0.5) 100%);
    -webkit-box-shadow: 0px 0px 10px 0px var(--color-primary); 
    box-shadow: 0px 0px 10px 0px var(--color-primary);
}
input:-webkit-autofill,
textarea:-webkit-autofill,
select:-webkit-autofill {
  box-shadow: 0 0 0px 1000px rgba(0,0,0,0) inset !important;
  -webkit-text-fill-color: var(--color-text) !important;
  transition: background-color 9999s ease-out 0s !important;
  background-color: transparent !important;
}
select option{
    appearance: none;
    color: var(--color-text);
    background-color: rgb(var(--color-background-rgb), 1);
}
label.required::after{
    content: " *";
    color: #FF0000;
}
input.invalid, select.invalid, textarea.invalid {
  border-color: #FF0000;
}
.submit-button{
    width: fit-content;
    margin-top: 1rem;
    padding: 1rem;
    font-family: 'Stereo Gothic 800';
    font-size: 1rem;
    border: none;
    border-radius: 4px;
    color: var(--color-text);
    background: linear-gradient(180deg,var(--color-primary) 0%, rgba(107, 0, 0, 1) 100%);
    transition: all 0.4s ease-in-out;
}
.submit-button:focus, .submit-button:hover{
    outline: none;
    cursor: pointer;
    -webkit-box-shadow: 0px 0px 10px 0px var(--color-primary); 
    box-shadow: 0px 0px 10px 0px var(--color-primary);
}
.form-message {
    margin-top: 1rem;
  font-family: 'Orbitron';
  color: var(--color-primary);
  font-size: 1.1rem;
  animation: fadeIn 0.5s ease-in-out;
}
@keyframes fadeIn {
  from { opacity: 0; transform: translateY(-5px); }
  to { opacity: 1; transform: translateY(0); }
}
@media (min-width: 768px) {
    .names{
        flex-direction: row;
    }
}
</style>

<script setup>
import { onMounted, ref } from 'vue'
import gsap from 'gsap'

//Form fields
const firstName = ref('')
const lastName = ref('')
const planet = ref('')
const specialite = ref('')
const message = ref('')

//Confirmation message
const errorMessage = ref('')
const confirmationMessage = ref('')

const handleSubmit = (event) => {
    event.preventDefault()

    //Reset messages
    errorMessage.value = ''
    confirmationMessage.value = ''
    
    //Reset invalid classes
    document.querySelectorAll('input, select, textarea').forEach(el => {
        el.classList.remove('invalid')
    })

    //Fields array
    //.trim allow to delete sapces in the string so if the user enter only a space it is considered as empty
    const fields = [
        { value: firstName.value.trim(), id: 'first-name' },
        { value: lastName.value.trim(), id: 'last-name' },
        { value: planet.value.trim(), id: 'planet' },
        { value: specialite.value.trim(), id: 'specialite' },
        { value: message.value.trim(), id: 'message' }
    ]

    //Find the first empty field
    const firstInvalid = fields.find(field => !field.value)

    if (firstInvalid) {
        //Error message
        errorMessage.value = "Merci de remplir tous les champs avant de soumettre le formulaire."

        //Ajoute la classe 'invalid' au champ vide
        const e = document.getElementById(firstInvalid.id)
        e.classList.add('invalid')

        //Scroll to invalid field
        e.scrollIntoView({ behavior: 'smooth', block: 'center' })

        return
    }

    //If fields not empty send form values to console
    console.log('Formulaire envoyé :'+ "\n" 
    + "Prénom : " + firstName.value + "\n"
    + "Nom : " + lastName.value + "\n"
    + "Planète : " + planet.value + "\n"
    + "Spécialité : " + specialite.value + "\n"
    + "Message : " + message.value + "\n"
    )

    confirmationMessage.value = `Merci ${firstName.value}, votre allégeance a bien été reçue !`

    // Reset
    firstName.value = ''
    lastName.value = ''
    planet.value = ''
    specialite.value = ''
    message.value = ''
}

onMounted(() => {
  const inputs = document.querySelectorAll('input[type="text"], textarea, select')

  inputs.forEach((e) => {
    e.addEventListener('focus', () => {
      gsap.to(e, {
        duration: 0.4,
        background: 'linear-gradient(200deg, rgba(0,0,0,0) 50%, rgba(255,0,0,0.5) 100%)',
        ease: 'power1.out',
      })
    })

    e.addEventListener('blur', () => {
      gsap.to(e, {
        duration: 0.4,
        background: 'linear-gradient(200deg, rgba(var(--color-background-rgb), 0) 50%, rgba(110,110,110,0.5) 100%)',
        ease: 'power1.in',
      })
    })
  })
})
</script>