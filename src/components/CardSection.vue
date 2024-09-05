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
              src="data:image/svg+xml,%3csvg%20xmlns='http://www.w3.org/2000/svg'%20width='64'%20height='64'%3e%3cg%20fill='none'%3e%3cpath%20fill='%23676E74'%20d='M56.842%207.158c-9.526-9.563-24.902-9.525-34.428%200-8.025%208.026-9.45%2020.44-3.525%2030.003l-2.513%202.55-1.356%206.144%204.214%204.214%205.093-2.408%202.512-2.55a24.254%2024.254%200%200030.003-3.525c9.563-9.526%209.525-24.902%200-34.428z'/%3e%3cpath%20fill='%23474F54'%20d='M24.327%2047.661l2.512-2.55a24.254%2024.254%200%200030.003-3.525c9.563-9.526%209.525-24.902%200-34.428l-40.26%2040.26%202.652%202.651%205.093-2.408z'/%3e%3cpath%20fill='%2364E1DC'%20d='M54.213%209.787a20.56%2020.56%200%2000-14.585-6.041C28.236%203.746%2019%2012.98%2019%2024.372a20.564%2020.564%200%20006.041%2014.586%2020.564%2020.564%200%200014.586%206.04c11.392%200%2020.626-9.234%2020.626-20.626a20.56%2020.56%200%2000-6.041-14.585z'/%3e%3cpath%20fill='%2300C8C8'%20d='M60.254%2024.372a20.56%2020.56%200%2000-6.041-14.585l-29.17%2029.17A20.564%2020.564%200%200039.627%2045c11.392%200%2020.626-9.235%2020.626-20.627z'/%3e%3cpath%20fill='%23EFEFF4'%20d='M56.239%2023.41c-.184-.307-2.98-4.914-7.281-8.368-2.63-2.113-5.822-3.796-9.33-3.796-9.242%200-16.314%2011.669-16.61%2012.165l-.576.961.575.961c.184.309%202.98%204.916%207.28%208.37%202.631%202.112%205.823%203.795%209.33%203.795%209.243%200%2016.315-11.668%2016.612-12.165l.574-.96-.574-.962z'/%3e%3cpath%20fill='%23DADAE5'%20d='M56.239%2025.333l.574-.96-.574-.962c-.184-.308-2.98-4.915-7.281-8.369l-18.66%2018.66c2.63%202.113%205.822%203.796%209.33%203.796%209.242%200%2016.314-11.668%2016.61-12.165z'/%3e%3cpath%20fill='%2364E1DC'%20d='M43.604%2020.396a5.607%205.607%200%2000-3.976-1.65%205.632%205.632%200%2000-5.626%205.626c0%201.551.631%202.958%201.65%203.976a5.609%205.609%200%20003.976%201.65%205.632%205.632%200%20005.625-5.626c0-1.55-.63-2.957-1.649-3.976z'/%3e%3cpath%20fill='%2300C8C8'%20d='M45.253%2024.372c0-1.55-.63-2.957-1.649-3.976l-7.952%207.952a5.608%205.608%200%20003.976%201.65%205.632%205.632%200%20005.625-5.626z'/%3e%3cpath%20fill='%23676E74'%20d='M40.954%2023.046a1.876%201.876%200%2010-1.326%203.2%201.876%201.876%200%20001.326-3.2z'/%3e%3cpath%20fill='%23474F54'%20d='M41.503%2024.372c0-.517-.21-.986-.55-1.326l-2.65%202.652a1.876%201.876%200%20003.2-1.326z'/%3e%3cpath%20fill='%23575C60'%20d='M20.333%2043.667l-3.957-3.957L0%2056.049l3.975%203.976L7.951%2064l16.376-16.339z'/%3e%3cpath%20fill='%23333637'%20d='M24.327%2047.661l-3.994-3.994L3.975%2060.025%207.951%2064z'/%3e%3c/g%3e%3c/svg%3e"
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
              src="data:image/svg+xml,%3csvg%20xmlns='http://www.w3.org/2000/svg'%20width='64'%20height='64'%3e%3cg%20fill='none'%3e%3cpath%20fill='%23EFEFF4'%20d='M64%2014.454v41.788H0V14.454l3.75-3.787h56.5z'/%3e%3cpath%20fill='%23DADAE5'%20d='M64%2014.454v41.788H32V10.667h28.25z'/%3e%3cpath%20fill='%23474F54'%20d='M0%200h64v15.515H0z'/%3e%3cpath%20fill='%2332393F'%20d='M32%200h32v15.515H32z'/%3e%3cg%20fill='%23FF637B'%3e%3cpath%20d='M7.758%205.818h3.685v3.879H7.758zM15.128%205.818h3.685v3.879h-3.685zM22.497%205.818h3.685v3.879h-3.685z'/%3e%3c/g%3e%3cpath%20fill='%23FF637B'%20d='M45.576%2042.245V64H34.355v-3.71h-3.74V64H19.394V42.245l11.37-9.275h3.105z'/%3e%3cpath%20fill='%23DADAE5'%20d='M11.636%2022.303h41.697v3.879H11.636z'/%3e%3cpath%20fill='%23C9C9D3'%20d='M32%2022.303h20.364v3.879H32z'/%3e%3cpath%20fill='%23E63950'%20d='M45.576%2042.245V64H33.939v-3.71H32V32.97h1.435z'/%3e%3cpath%20fill='%23EFEFF4'%20d='M30.061%2045.576h3.878v3.879h-3.878z'/%3e%3cpath%20fill='%23DADAE5'%20d='M32%2045.576h1.939v3.879H32z'/%3e%3cpath%20fill='%23676E74'%20d='M50.424%2045.779l-2.452%202.706-15.487-13.526-15.488%2013.526-2.452-2.706%2017.94-15.718z'/%3e%3cpath%20fill='%23474F54'%20d='M32%2030.061l18.424%2015.718-2.518%202.706L32%2034.959z'/%3e%3c/g%3e%3c/svg%3e"
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
              src="data:image/svg+xml,%3csvg%20xmlns='http://www.w3.org/2000/svg'%20width='64'%20height='64'%3e%3cg%20fill='none'%3e%3cpath%20fill='%23676E74'%20d='M26.375%2052.625h11.25V64h-11.25z'/%3e%3cpath%20fill='%23333637'%20d='M32%2052.625h5.625V64H32z'/%3e%3cpath%20fill='%234C545A'%20d='M22.625%2047h18.75v9.375h-18.75z'/%3e%3cpath%20fill='%2352585C'%20d='M32%2047h9.375v9.375H32z'/%3e%3cpath%20fill='%23FFDA2D'%20d='M45.012%2036.725c-2.325%201.913-3.637%204.612-3.637%207.425V47h-18.75v-2.85c0-2.85-1.238-5.512-3.3-7.125-5.062-3.938-7.95-9.862-7.95-16.275a20.585%2020.585%200%20017.613-16.013C22.7%201.737%2027.238%200%2032%200c1.462%200%202.962.15%204.425.45%208.1%201.688%2014.475%208.45%2015.9%2016.663%201.275%207.5-1.425%2014.85-7.313%2019.612z'/%3e%3cpath%20fill='%23FDBF00'%20d='M45.012%2036.725c-2.325%201.913-3.637%204.612-3.637%207.425V47H32V0c1.462%200%202.962.15%204.425.45%208.1%201.688%2014.475%208.45%2015.9%2016.663%201.275%207.5-1.425%2014.85-7.313%2019.612z'/%3e%3cpath%20fill='%23676E74'%20d='M18.875%2045.125h26.25v3.75h-26.25z'/%3e%3cpath%20fill='%23FF9100'%20d='M39.956%2010.143l2.651%202.651-3.979%203.978-2.651-2.651z'/%3e%3cpath%20fill='%23FDBF00'%20d='M25.372%2024.727l2.651%202.651-3.979%203.979-2.651-2.651zM30.125%2028.25h3.75v5.625h-3.75z'/%3e%3cpath%20fill='%23FF9100'%20d='M38.628%2024.727l3.979%203.979-2.651%202.651-3.979-3.979zM39.5%2018.875h5.625v3.75H39.5z'/%3e%3cpath%20fill='%23FDBF00'%20d='M24.044%2010.143l3.979%203.979-2.651%202.65-3.979-3.978zM18.875%2018.875H24.5v3.75h-5.625zM30.125%207.625h3.75v5.625h-3.75z'/%3e%3cg%20fill='%23FFDA2D'%3e%3cpath%20d='M0%2018.875h7.625v3.75H0zM6.585%2014.81l-5.75-3.75%202.08-3.12%205.75%203.75zM2.915%2033.56l-2.08-3.12%205.75-3.75%202.08%203.12z'/%3e%3c/g%3e%3cpath%20fill='%23FDBF00'%20d='M56.375%2018.875H64v3.75h-7.625zM61.085%2033.56l-5.75-3.75%202.08-3.12%205.75%203.75zM57.415%2014.81l-2.08-3.12%205.75-3.75%202.08%203.12z'/%3e%3cpath%20fill='%23FF9100'%20d='M32%207.625h1.875v5.625H32zM32%2028.25h1.875v5.625H32z'/%3e%3cpath%20fill='%23333637'%20d='M32%2045.125h13.125v3.75H32z'/%3e%3cpath%20fill='%23FDBF00'%20d='M32%2011.375c-5.175%200-9.375%204.2-9.375%209.375s4.2%209.375%209.375%209.375%209.375-4.2%209.375-9.375-4.2-9.375-9.375-9.375z'/%3e%3cpath%20fill='%23FF9100'%20d='M32%2030.125v-18.75c5.175%200%209.375%204.2%209.375%209.375s-4.2%209.375-9.375%209.375z'/%3e%3cpath%20fill='%23FFDA2D'%20d='M30.125%2018.875h3.75v3.75h-3.75z'/%3e%3cpath%20fill='%23FDBF00'%20d='M32%2018.875h1.875v3.75H32z'/%3e%3c/g%3e%3c/svg%3e"
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
              src="data:image/svg+xml,%3csvg%20xmlns='http://www.w3.org/2000/svg'%20width='64'%20height='64'%3e%3cg%20fill='none'%3e%3cpath%20fill='%23474F54'%20d='M64%200v41.25l-3.75%203.875H3.75L0%2041.25V0z'/%3e%3cpath%20fill='%2332393F'%20d='M64%200v41.25l-3.75%203.875H32V0z'/%3e%3cpath%20fill='%23DADAE5'%20d='M22.625%2050.875h18.75v11.25h-18.75z'/%3e%3cpath%20fill='%23C9C9D3'%20d='M32%2050.875h9.375v11.25H32z'/%3e%3cpath%20fill='%23EFEFF4'%20d='M0%2041.25h64v11.5H0z'/%3e%3cpath%20fill='%23DADAE5'%20d='M32%2041.25h32v11.5H32z'/%3e%3cpath%20fill='%23EFEFF4'%20d='M15.125%2060.25h33.75V64h-33.75z'/%3e%3cpath%20fill='%23DADAE5'%20d='M32%2060.25h16.875V64H32z'/%3e%3cpath%20fill='%23549EF2'%20d='M20.75%207.5c-7.236%200-13.125%205.889-13.125%2013.125S13.514%2033.75%2020.75%2033.75s13.125-5.889%2013.125-13.125S27.986%207.5%2020.75%207.5zm0%2018.75a5.631%205.631%200%2001-5.625-5.625A5.631%205.631%200%200120.75%2015a5.631%205.631%200%20015.625%205.625%205.631%205.631%200%2001-5.625%205.625z'/%3e%3cg%20fill='%23377FD2'%3e%3cpath%20d='M45.125%207.5H56.5v3.75H45.125zM37.625%207.5h3.75v3.75h-3.75zM45.125%2022.5H56.5v3.75H45.125zM37.625%2022.5h3.75v3.75h-3.75zM37.625%2015H56.5v3.75H37.625zM37.625%2030H56.5v3.75H37.625z'/%3e%3c/g%3e%3c/g%3e%3c/svg%3e"
            ></v-img>
          </v-card>
        </div>
      </div>
    </div>
  </v-container>
</template>
