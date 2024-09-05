<script lang="ts">
import Calculator from '../assets/images/icon-calculator.svg'
import Karma from '../assets/images/icon-karma.svg'
import TeamBuilder from '../assets/images/icon-team-builder.svg'
import Supervisor from '../assets/images/icon-supervisor.svg'
import { useWindowSize, useScreenOrientation } from '@vueuse/core'

export default {
  data() {
    const { width } = useWindowSize()
    const { orientation } = useScreenOrientation()
    let w = width.value
    let o = orientation.value

    return {
      w,
      o,
      cards: [
        {
          title: 'Supervisor',
          text: 'Monitors activity to identify project roadblocks',
          imgLink: Supervisor,
          class: 'mx-auto my-8 Supervisor',
          borderColor: 'var(--primary-c-cyan)'
        },
        {
          title: 'Team Builder',
          text: 'Scans our talent network to create the optimal team for your project',
          imgLink: TeamBuilder,
          class: 'mx-auto my-8 TeamBuilder',
          borderColor: 'var(--primary-c-red)'
        },
        {
          title: 'Karma',
          text: 'Regularly evaluates our talent to ensure quality',
          imgLink: Karma,
          class: 'mx-auto my-8 Karma',
          borderColor: 'var(--primary-c-orange)'
        },
        {
          title: 'Calculator',
          text: 'Uses data from past projects to provide better delivery estimates',
          imgLink: Calculator,
          class: 'mx-auto my-8 Calculator',
          borderColor: 'var(--primary-c-blue)'
        }
      ]
    }
  }
}
</script>

<template>
  <v-container>
    <div
      v-if="
        (w < 600 && o == 'portrait-primary') ||
        (w <= 926 && o == 'landscape-primary') ||
        (w > 600 && w < 1000 && o == 'portrait-primary')
      "
    >
      <v-card
        v-for="card in cards"
        :key="card.title"
        :card-title="card.title"
        :card-text="card.text"
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
    </div>

    <div v-if="(w > 1000 && o == 'portrait-primary') || (w > 926 && o == 'landscape-primary')">
      <div class="grid">
        <div style="align-self: center">
          <v-card style="border-color: var(--primary-c-cyan)" elevation="16" max-width="100%">
            <v-card-item>
              <v-card-title> Supervisor</v-card-title>
            </v-card-item>
            <v-card-text> Monitors activity to identify project roadblocks </v-card-text>
            <v-img
              height="80px"
              src="/four-card-feature-section/assets/images/icon-supervisor.svg"
            ></v-img>
          </v-card>
        </div>
        <div>
          <v-card style="border-color: var(--primary-c-red)" elevation="16" max-width="100%">
            <v-card-item>
              <v-card-title> Team Builder </v-card-title>
            </v-card-item>
            <v-card-text>
              Scans our talent network to create the optimal team for your project
            </v-card-text>
            <v-img
              height="80px"
              src="/four-card-feature-section/assets/images/icon-team-builder.svg"
            ></v-img>
          </v-card>
          <div style="height: 2em"></div>
          <v-card style="border-color: var(--primary-c-orange)" elevation="16" max-width="100%">
            <v-card-item>
              <v-card-title> Karma </v-card-title>
            </v-card-item>
            <v-card-text> Regularly evaluates our talent to ensure quality </v-card-text>
            <v-img
              height="80px"
              src="/four-card-feature-section/assets/images/icon-karma.svg"
            ></v-img>
          </v-card>
        </div>
        <div style="align-self: center">
          <v-card style="border-color: var(--primary-c-blue)" elevation="16" max-width="100%">
            <v-card-item>
              <v-card-title> Calculator </v-card-title>
            </v-card-item>
            <v-card-text>
              Uses data from past projects to provide better delivery estimates
            </v-card-text>
            <v-img
              height="80px"
              src="/four-card-feature-section/assets/images/icon-calculator.svg"
            ></v-img>
          </v-card>
        </div>
      </div>
    </div>
  </v-container>
</template>
