<template>
  <ion-page>
    <PageHeader :title="name" />
    <ion-content :fullscreen="true">
      <ExploreContainer :name="name" />
    </ion-content>
  </ion-page>
</template>

<script lang="ts" setup>
import { IonPage, IonContent } from '@ionic/vue'
import PageHeader from '@/components/PageHeader.vue'
import ExploreContainer from '@/components/ExploreContainer.vue'

defineProps<{ name: string }>()
</script>
