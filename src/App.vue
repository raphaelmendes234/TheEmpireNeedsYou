<script setup lang="ts">
import AdvantagesCard from './components/AdvantagesCard.vue';
import AdvantagesCorners from './components/AdvantagesCorners.vue';
import HeroSection from './components/HeroSection.vue';
import IconAmbition from './components/icons/IconAmbition.vue';
import IconInstagram from './components/icons/IconInstagram.vue';
import IconLoyalty from './components/icons/IconLoyalty.vue';
import IconPower from './components/icons/IconPower.vue';
import IconTiktok from './components/icons/IconTiktok.vue';
import SectionTitle from './components/SectionTitle.vue';
import StrenghtCard from './components/StrenghtCard.vue';
</script>

<template>
  <header>
    <HeroSection></HeroSection>
  </header>

  <main>
    <section>
      <SectionTitle>
        <template #title>
          Nos
          <span class="alt-font">forces</span>
        </template>
        <template #symbols>nos forces</template>
        <template #intro-text>Plonge dans l'essence du Côté Obscur : une philosophie rigoureusement sélective, impitoyablement ambitieuse… et étonnamment cohérente.</template>
      </SectionTitle>
      
      <div class="strenghts-container">
        <div></div>
        <div>
          <StrenghtCard>
            <template #icon><IconPower /></template>
            <template #title>Pouvoir</template>
            <template #symbols>pouvoir</template>
            <template #text>La Force n’est pas un outil, c’est une arme. Rejoins-nous pour en maîtriser les moindres recoins : lévitation, étranglement mental, contrôle des esprits... Tu ne suivras plus jamais les ordres : tu les donneras.</template>
          </StrenghtCard>
        </div>
        <div>
          <StrenghtCard>
            <template #icon><IconAmbition /></template>
            <template #title>Ambition</template>
            <template #symbols>ambition</template>
            <template #text>Ici, gravir les échelons n’est pas une option, c’est une vocation. L’échec ? Toléré une fois. Deux fois ? Expulsé dans une chambre sans oxygène. À chaque victoire, une promotion. À chaque défaite, une méditation... forcée.</template>
          </StrenghtCard>
        </div>
        <div>
          <StrenghtCard>
            <template #icon><IconLoyalty /></template>
            <template #title>Loyauté</template>
            <template #symbols>loyaute</template>
            <template #text>Ton libre arbitre ? On te le laisse… jusqu’à ce que l’Empereur te le reprenne. Une seule ligne de conduite : servir le plan de domination galactique. Un seul patron : Sa Majesté Palpatine. La trahison ? Très mauvaise idée.</template>
          </StrenghtCard>
        </div>
      </div>
    </section>

    <section>
      <SectionTitle>
        <template #title>
          pourquoi
          <span class="alt-font">nous rejoindre</span>
        </template>
        <template #title-symbols>nous rejoindre</template>
        <template #intro-text>Plonge dans l'essence du Côté Obscur : une philosophie rigoureusement sélective, impitoyablement ambitieuse… et étonnamment cohérente.</template>
      </SectionTitle>

      <div class="advantages-container">
        <div class="advantage-wrapper left">
          <AdvantagesCard>
            <template #number>1.</template>
            <template #title>Accès prioritaire à l'étoile de la mort</template>
            <template #symbols>acces prioritaire</template>
            <template #text>Salle de repos en orbite, cantine galactique 5 étoiles, et un laser planétaire de dissuasion. Tu auras même une place de parking pour ton TIE Fighter.
(Attention, stationnement interdit près du réacteur principal.)</template>
          </AdvantagesCard>
          <AdvantagesCorners />
        </div>
        <div class="advantage-wrapper right">
          <AdvantagesCard>
            <template #number>2.</template>
            <template #title>Télétravail par télépathie</template>
            <template #symbols>teletravail telepathie</template>
            <template #text>Plus de mails, plus de réunions : pense ton rapport, il est déjà lu. Flexibilité maximale, efficacité redoutable. Notre motto : "Slack, c’est pour les Jedi."</template>
          </AdvantagesCard>
          <AdvantagesCorners />
        </div>
        <div class="advantage-wrapper left">
          <AdvantagesCard>
            <template #number>3.</template>
            <template #title>Formation continue en étranglement à distance</template>
            <template #symbols>formation continue</template>
            <template #text>Apprends à gérer les conflits internes sans te lever de ton trône. Module de gestion de crise fourni. Efficace contre l’incompétence chronique.</template>
          </AdvantagesCard>
          <AdvantagesCorners />
        </div>
      </div>
    </section>

    <section>
      <SectionTitle>
        <template #title>
          rejoins nous
          <span class="alt-font">dès maintenant</span>
        </template>
        <template #title-symbols>rejoins nous</template>
        <template #intro-text>Dépose ton engagement. L’Empire analysera ta loyauté.</template>
      </SectionTitle>
    </section>

    <section>
      <SectionTitle>
        <template #title>
          contact
          <span class="alt-font">impérial</span>
        </template>
        <template #title-symbols>contact imperial</template>
        <template #intro-text>Tu peux fuir la République, mais tu ne peux pas ignorer l’appel du Côté Obscur. Pour toute question, candidature spontanée ou menace d’insubordination :</template>
      </SectionTitle>

      <div class="contact-container">
        <div class="contact-item">
          <div>
            <h3>Contact</h3>
            <p class="symbols">contact</p> 
          </div>
           <a class="link" href="mailto:contact.empiresith@darkmail.gal">E-mail : contact.empiresith@darkmail.gal</a>
           <a class="link" href="tel:Comlink : +113 66 6 66 66 66">Comlink : +113 66 6 66 66 66</a>
        </div>
        <div class="contact-item">
          <div>
            <h3>Réseaux</h3>
            <p class="symbols">reseaux</p>
          </div>
          <div class="social">
            <IconTiktok />
            <a class="link" href="">DarkTok</a>
          </div>
          <div class="social">
            <IconInstagram />
            <a class="link" href="">InstaSith</a>
          </div>
        </div>
      </div>

    </section>
  </main>
</template>

<style scoped>
.link{
  color: var(--color-primary);
  text-decoration: none;
}

.contact-container{
  width: 100%;
  display: flex;
  flex-direction: column;
  gap: 2rem;
}

.contact-item{
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.social{
  display: flex;
  justify-content: flex-start;
  align-items: center;
  gap: 1rem;
}

header{
  position: relative;
  width: 100%;
  height: 50vh;
  box-sizing: border-box;
  display: flex;
  justify-content: flex-start;
  align-items: flex-end;
  background-color: var(--color-background);
  background: url("/images/dark-vador.webp");
  background-repeat: no-repeat;
  background-position: center 60%;
  background-size: 100%;
}

section{
  width: 100%;
  padding: 2rem 1rem;
  box-sizing: border-box;
  display: flex;
  flex-direction: column;
  gap: 4rem;
}

.strenghts-container {
  display: grid;
  grid-template-columns: 1fr;
}

.advantages-container{
  width: 100%;
  display: flex;
  flex-direction: column;
}
.red{
  width: 100px;
  height: 100px;
  background-color: red;
}
.advantage-wrapper{
  position: relative;
  width: 100%;
  display: flex;
  align-items: center;
  border-top: 1px solid var(--color-text);
  border-bottom: 1px solid var(--color-text);
}
.left{
  justify-content: flex-start;
  background: linear-gradient(200deg,rgba(255, 0, 0, 0) 50%, rgba(109, 0, 0, 0.5) 100%);
}
.right{
  justify-content: flex-end;
  background: linear-gradient(150deg,rgba(255, 0, 0, 0) 50%, rgba(109, 0, 0, 0.5) 100%);
}

@media (min-width: 768px) {
  header{
    height: 75vh;
    background-position: center 65%;
    background-size: 75%;
  }
}

@media (min-width: 1024px) {
  header{
    height: 100vh;
    background-position: center 50%;
    background-size: 75%;
  }
  section{
    padding: 4rem;
  }
   .strenghts-container {
    grid-template-columns: repeat(2, 1fr);
  }
  .contact-container{
    flex-direction: row;
    gap: 4rem;
  }
}

</style>
