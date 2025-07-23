<template>
    <form action="" id="contactForm" class="contact-form">
        <div class="names">
          <div class="input-wrapper">
            <label for="first-name" class="required">Prénom</label>
            <input type="text" id="first-name" name="first-name">
          </div>

          <div class="input-wrapper">
            <label for="last-name" class="required">Nom</label>
            <input type="text" id="last-name" name="last-name">
          </div>
        </div>

        <div class="input-wrapper">
            <label for="planet" class="required">Planète d'origine</label>
            <input type="text" id="planet" name="planet">
        </div>

        <div class="input-wrapper">
            <label for="specialite" class="required">Spécialité</label>
            <select name="specialite" id="specialite">
                <option value="hacking">Hacking</option>
                <option value="espionage">Espionnage</option>
                <option value="lightsaber">Sabre laser</option>
                <option value="telekinesis">Télékinésie</option>
            </select>
        </div>

        <div class="input-wrapper">
            <label for="message" class="required">Message de motivation</label>
            <textarea id="message" name="message" rows="5" cols="30"></textarea>
        </div>

        <button type="submit" class="submit-button">Soumettre mon allégeance</button>
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
select option{
    appearance: none;
    color: var(--color-text);
    background-color: rgb(var(--color-background-rgb), 1);
}
label.required::after{
    content: " *";
    color: #FF0000;
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
@media (min-width: 768px) {
    .names{
        flex-direction: row;
    }
}
</style>

<script setup>
import { onMounted } from 'vue'
import gsap from 'gsap'

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