<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Tab 1</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Tab 1</ion-title>
        </ion-toolbar>
      </ion-header>

      <ion-list>
        <ion-item button v-for="tech in techs" :router-link="`/explore/${tech.title}`">
          <ion-icon slot="start" :icon="tech.icon" :style="{ color: tech.color }"></ion-icon>
          <ion-label>{{ tech.title }}</ion-label>
        </ion-item>
      </ion-list>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'
import {
  IonPage,
  IonHeader,
  IonToolbar,
  IonTitle,
  IonContent,
  IonList,
  IonItem,
  IonIcon,
  IonLabel,
} from '@ionic/vue'
import {
  logoAngular,
  logoCss3,
  logoHtml5,
  logoJavascript,
  logoSass,
  logoNodejs,
  logoPython,
  logoMarkdown,
  logoTux,
} from 'ionicons/icons'
import ExploreContainer from '@/components/ExploreContainer.vue'

export default defineComponent({
  name: 'Tab1',
  components: {
    ExploreContainer,
    IonPage,
    IonHeader,
    IonToolbar,
    IonTitle,
    IonContent,
    IonList,
    IonItem,
    IonIcon,
    IonLabel,
  },
  setup() {
    const techs = ref([
      {
        title: 'Angular',
        icon: logoAngular,
        description:
          'A powerful Javascript framework for building single page apps. Angular is open source, and maintained by Google.',
        color: '#E63135',
      },
      {
        title: 'CSS3',
        icon: logoCss3,
        description:
          'The latest version of cascading stylesheets - the styling language of the web!',
        color: '#0CA9EA',
      },
      {
        title: 'HTML5',
        icon: logoHtml5,
        description: "The latest version of the web's markup language.",
        color: '#F46529',
      },
      {
        title: 'JavaScript',
        icon: logoJavascript,
        description: 'One of the most popular programming languages on the Web!',
        color: '#FFD439',
      },
      {
        title: 'Sass',
        icon: logoSass,
        description:
          'Syntactically Awesome Stylesheets - a mature, stable, and powerful professional grade CSS extension.',
        color: '#CE6296',
      },
      {
        title: 'NodeJS',
        icon: logoNodejs,
        description:
          'An open-source, cross-platform runtime environment for developing server-side Web applications.',
        color: '#78BD43',
      },
      {
        title: 'Python',
        icon: logoPython,
        description: 'A clear and powerful object-oriented programming language!',
        color: '#3575AC',
      },
      {
        title: 'Markdown',
        icon: logoMarkdown,
        description:
          'A super simple way to add formatting like headers, bold, bulleted lists, and so on to plain text.',
        color: '#412159',
      },
      {
        title: 'Tux',
        icon: logoTux,
        description: 'The official mascot of the Linux kernel!',
        color: '#000',
      },
    ])

    return {
      techs,
    }
  },
})
</script>
