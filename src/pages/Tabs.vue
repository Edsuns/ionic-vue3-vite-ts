<template>
  <ion-page>
    <ion-tabs>
      <ion-router-outlet></ion-router-outlet>
      <ion-tab-bar :translucent="true" slot="bottom">
        <ion-tab-button
          tab="tab1"
          href="/tabs/tab1"
          @click="router.replace('/tabs/tab1', animateTab)"
        >
          <ion-icon :icon="triangle" />
          <ion-label>Tab 1</ion-label>
        </ion-tab-button>

        <ion-tab-button
          tab="tab2"
          href="/tabs/tab2"
          @click="router.replace('/tabs/tab2', animateTab)"
        >
          <ion-icon :icon="albums" />
          <ion-label>Tab 2</ion-label>
        </ion-tab-button>

        <ion-tab-button
          tab="tab3"
          href="/tabs/tab3"
          @click="router.replace('/tabs/tab3', animateTab)"
        >
          <ion-icon :icon="square" />
          <ion-label>Tab 3</ion-label>
        </ion-tab-button>
      </ion-tab-bar>
    </ion-tabs>
  </ion-page>
</template>

<script lang="ts" setup>
import {
  IonRouterOutlet,
  IonTabBar,
  IonTabButton,
  IonTabs,
  IonLabel,
  IonIcon,
  IonPage,
  useIonRouter,
  createAnimation,
} from '@ionic/vue'
import { albums, square, triangle } from 'ionicons/icons'

const router = useIonRouter()
const emptyAnimation = createAnimation()
const animateTab = () => emptyAnimation
</script>
