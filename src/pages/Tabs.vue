<template>
  <ion-page>
    <ion-content>
      <ion-tabs>
        <ion-router-outlet></ion-router-outlet>
        <ion-tab-bar slot="bottom">
          <ion-tab-button tab="tab1" href="/tabs/tab1" @click="$router.replace('/tabs/tab1')">
            <ion-icon :icon="triangle" />
            <ion-label>Tab 1</ion-label>
          </ion-tab-button>

          <ion-tab-button tab="tab2" href="/tabs/tab2" @click="$router.replace('/tabs/tab2')">
            <ion-icon :icon="albums" />
            <ion-label>Tab 2</ion-label>
          </ion-tab-button>

          <ion-tab-button tab="tab3" href="/tabs/tab3" @click="$router.replace('/tabs/tab3')">
            <ion-icon :icon="square" />
            <ion-label>Tab 3</ion-label>
          </ion-tab-button>
        </ion-tab-bar>
      </ion-tabs>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import {
  IonRouterOutlet,
  IonTabBar,
  IonTabButton,
  IonTabs,
  IonContent,
  IonLabel,
  IonIcon,
  IonPage,
} from '@ionic/vue'
import { albums, square, triangle } from 'ionicons/icons'

export default defineComponent({
  name: 'Tabs',
  components: {
    IonRouterOutlet,
    IonContent,
    IonLabel,
    IonTabs,
    IonTabBar,
    IonTabButton,
    IonIcon,
    IonPage,
  },
  setup() {
    return {
      albums,
      square,
      triangle,
    }
  },
})
</script>
