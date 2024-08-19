<script lang="ts">
import Calculator from '../assets/images/icon-calculator.svg'
import Karma from '../assets/images/icon-karma.svg'
import TeamBuilder from '../assets/images/icon-team-builder.svg'
import Supervisor from '../assets/images/icon-supervisor.svg'
export default {
  data() {
    return {
      cards: [
        {
          title: 'Supervisor',
          text: 'Monitors activity to identify project roadblocks',
          imgLink: Supervisor,
          borderColor: 'var(--primary-c-cyan)'
        },
        {
          title: 'Team Builder',
          text: 'Scans our talent network to create the optimal team for your project',
          imgLink: TeamBuilder,
          borderColor: 'var(--primary-c-red)'
        },
        {
          title: 'Karma',
          text: 'Regularly evaluates our talent to ensure quality',
          imgLink: Karma,
          borderColor: 'var(--primary-c-orange)'
        },
        {
          title: 'Calculator',
          text: 'Uses data from past projects to provide better delivery estimates',
          imgLink: Calculator,
          borderColor: 'var(--primary-c-blue)'
        }
      ]
    }
  }
}
</script>

<template>
  <v-card
    v-for="card in cards"
    :key="card.title"
    :food-title="card.title"
    :food-text="card.text"
    class="mx-auto my-8"
    :style="{ borderColor: card.borderColor }"
    elevation="16"
    max-width="344"
  >
    <v-card-item>
      <v-card-title> {{ card.title }}</v-card-title>
    </v-card-item>
    <v-card-text> {{ card.text }} </v-card-text>
    <v-img height="80px" :src="card.imgLink"></v-img>
  </v-card>
</template>
