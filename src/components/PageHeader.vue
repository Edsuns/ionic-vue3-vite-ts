<template>
  <ion-header :translucent="true">
    <ion-toolbar>
      <ion-buttons slot="start">
        <ion-back-button default-href="/"></ion-back-button>
      </ion-buttons>
      <ion-title>{{ title ?? $route.meta.title }}</ion-title>
    </ion-toolbar>
  </ion-header>
</template>

<script lang="ts" setup>
import { IonBackButton, IonButtons, IonHeader, IonTitle, IonToolbar } from '@ionic/vue'

defineProps<{ title?: string }>()
</script>
