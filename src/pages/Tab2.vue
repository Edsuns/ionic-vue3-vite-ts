<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Tab 2</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content class="ion-padding">
      <ion-refresher slot="fixed" @ionRefresh="doRefresh($event)">
        <ion-refresher-content></ion-refresher-content>
      </ion-refresher>

      <ion-list>
        <ion-item v-for="item in items">
          <ion-label>
            <h2>{{ item }}</h2>
            <h3>Lorem ipsum dolor sit amet, consectetur adipiscing elit</h3>
          </ion-label>
        </ion-item>
      </ion-list>

      <ion-infinite-scroll @ionInfinite="loadData($event)">
        <ion-infinite-scroll-content
          loading-text="Loading more data..."
        ></ion-infinite-scroll-content>
      </ion-infinite-scroll>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import {
  IonHeader,
  IonToolbar,
  IonTitle,
  IonButton,
  IonContent,
  IonRefresher,
  IonRefresherContent,
  IonInfiniteScroll,
  IonInfiniteScrollContent,
  IonItem,
  IonLabel,
  IonList,
  IonPage,
} from '@ionic/vue'
import { defineComponent, ref } from 'vue'

export default defineComponent({
  components: {
    IonHeader,
    IonToolbar,
    IonTitle,
    IonButton,
    IonContent,
    IonRefresher,
    IonRefresherContent,
    IonInfiniteScroll,
    IonInfiniteScrollContent,
    IonItem,
    IonLabel,
    IonList,
    IonPage,
  },
  setup() {
    const names = [
      'Burt Bear',
      'Charlie Cheetah',
      'Donald Duck',
      'Eva Eagle',
      'Ellie Elephant',
      'Gino Giraffe',
      'Isabella Iguana',
      'Karl Kitten',
      'Lionel Lion',
      'Molly Mouse',
      'Paul Puppy',
      'Rachel Rabbit',
      'Ted Turtle',
    ]
    const chooseRandomName = () => {
      return names[Math.floor(Math.random() * names.length)]
    }

    const items = ref<string[]>([])
    const pushData = () => {
      const max = items.value.length + 20
      const min = max - 20
      for (let i = min; i < max; i++) {
        items.value.push(chooseRandomName())
      }
    }

    const loadData = (ev: CustomEvent) => {
      setTimeout(() => {
        pushData()
        console.log('Loaded data')
        ev.target.complete()

        // App logic to determine if all data is loaded
        // and disable the infinite scroll
        if (items.value.length == 1000) {
          ev.target.disabled = true
        }
      }, 500)
    }

    const doRefresh = (event: CustomEvent) => {
      console.log('Begin async operation')

      const data: string[] = []
      for (let i = 0; i < 20; i++) {
        data.push(chooseRandomName())
      }

      setTimeout(() => {
        console.log('Async operation has ended')
        items.value = data
        event.target.complete()
      }, 1000)
    }

    pushData()

    return {
      doRefresh,
      loadData,
      items,
    }
  },
})
</script>
