<template>
  <Layout class="app">
    <div class="content">
      <div class="content__header">
        <h1 class="content__header-title">GLP</h1>
      </div>
      <div class="main">
        <div class="categories">
          <ul class="categories__list" >
            <li
                class="categories__list-item"
                v-for="tab in tabs"
                :key="tab"
                :class="{categoryActive: tab === currentTab}"
                @click="onChangeTabHandler(tab)"
            >
              {{tab}}
            </li>
          </ul>
        </div>
        <div class="controls">
          <Control name="Цены" :controls="prices" @price-control="priceChangeHandler"/>
          <Control name="Вид расчета" :controls="payment" @payment-control="paymentChangeHandler"/>
          <Control name="Тип будки" :controls="booth" @booth-control="boothChangeHandler"/>
        </div>
        <div class="tables">
          <Table
              title="Оптимальные цены"
              :currentBooth="currentBooth"
              :currentPayment="currentPayment"
              :currentPrice="currentPrice"/>
          <Table
              title="Минимально возможные цены"
              :currentBooth="currentBooth"
              :currentPayment="currentPayment"
              :currentPrice="currentPrice"/>
        </div>
        <div class="button">
          <button class="button-save" @click="onSaveHandler">Сохранить изменения</button>
        </div>
      </div>
    </div>
  </Layout>
</template>

<script>
import '@/styles/global.css'
import '@/styles/main.scss'
import Layout from "@/layouts/Layout";
import Control from "@/components/Control";
import Table from "@/components/Table";

export default {
  name: 'App',
  components: {Layout, Table, Control},
  data: () => ({
    tabs: ['Данные', 'Документы', 'Контакты', 'Тарифы', 'Арбитраж'],
    currentTab: 'Тарифы',
    prices: ['Для клиента', 'Для водителя'],
    payment: ['По ставке', 'По часам', 'По точкам', 'КМ + МИН', 'Грузчики'],
    booth: ['Тент', 'Промтоварные', 'Изотерма', 'Реф'],
    currentPrice: 'Для клиента',
    currentPayment: 'По часам',
    currentBooth: 'Тент',
  }),
  methods: {
    onChangeTabHandler(tab) {
      this.currentTab = tab
    },
    boothChangeHandler(control) {
      this.currentBooth = control
    },
    priceChangeHandler(control) {
      this.currentPrice = control
    },
    paymentChangeHandler(control) {
      this.currentPayment = control
    },
    onSaveHandler() {
      alert(`Сохранено!\nЦены: ${this.currentPrice}\n` + `Вид расчета: ${this.currentPayment}\n` + `Тип будки: ${this.currentBooth}`)
    }
  }
}
</script>

