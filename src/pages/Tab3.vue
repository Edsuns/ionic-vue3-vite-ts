<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Tab 3</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Tab 3</ion-title>
        </ion-toolbar>
      </ion-header>

      <ion-list>
        <ion-item>
          <ion-label>Dark Mode</ion-label>
          <ion-toggle @ionChange="toggleDarkMode" value="Dark Mode" :checked="darkMode">
          </ion-toggle>
        </ion-item>
      </ion-list>
    </ion-content>
  </ion-page>
</template>

<script lang="ts" setup>
import { ref } from 'vue'
import {
  IonPage,
  IonHeader,
  IonToolbar,
  IonTitle,
  IonContent,
  IonList,
  IonItem,
  IonLabel,
  IonToggle,
  ToggleCustomEvent,
} from '@ionic/vue'

const darkMode = ref(document.body.classList.contains('dark'))

const toggleDarkMode = (ev: ToggleCustomEvent) => {
  document.body.classList.toggle('dark', ev.detail.checked)
  const colorScheme = document.head.querySelector('meta[name="color-scheme"]')
  colorScheme?.setAttribute('content', ev.detail.checked ? 'dark' : 'light')
}
</script>
