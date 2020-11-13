<template>
  <div class="control">
    <h3 class="control__name">{{name}}</h3>
    <button
        v-for="control in controls"
        :key="control"
        class="control-btn"
        :class="{active: pricesType === control || paymentType === control || boothType === control}"
        @click="onClickHandler(control, name)"
    >
      {{control}}
    </button>
  </div>
</template>

<script>
import '@/styles/control.scss'

export default {
  name: 'Control',
  props: ['name', 'controls'],
  data: () => ({
    pricesType: 'Для клиента',
    paymentType: 'По часам',
    boothType: 'Тент',
  }),
  methods: {
    onClickHandler(control, name) {
      switch (name) {
        case "Цены":
          this.pricesType = control
          this.$emit('price-control', control)
          break
        case "Вид расчета":
          this.paymentType = control
          this.$emit('payment-control', control)
          break
        case "Тип будки":
          this.boothType = control
          this.$emit('booth-control', control)
          break
      }
    }
  }
}
</script>
