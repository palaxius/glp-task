<template>
  <div class="wrapper-table">
    <h3 class="table-title">{{title}}</h3>
    <table class="table">
      <thead>
      <tr>
        <th>Тоннаж ТС</th>
        <th>Тип ТС</th>
        <th>Мин-но / мах часов в ставке</th>
        <th>Подача ТС</th>
        <th>Экспедир.</th>
        <th>Тариф по ставке</th>
        <th>Переработка за час</th>
        <th>Гидроборт</th>
        <th>Въезд ТТК, МОЖД</th>
        <th>Границы</th>
        <th>Стоимость</th>
        <th>Ручная разгрузка</th>
        <th>Перегруз</th>
        <th>Платная парковка</th>
        <th>Инкасация</th>
        <th>Водитель - Грузчик за час</th>
        <th>Водитель - Грузчик время</th>
      </tr>
      </thead>
      <tbody>
      <tr>
        <td>1 т</td>
        <td>{{currentBooth}}</td>
        <td>{{currentPrice === 'Для клиента' ? '8:00' : '4:00'}}</td>
        <td>1</td>
        <td>1</td>
        <td>{{ randomData * 10 }}</td>
        <td>{{ randomData }}</td>
        <td>{{ randomData }}</td>
        <td></td>
        <td>0</td>
        <td>18</td>
        <td/>
        <td/>
        <td/>
        <td/>
        <td/>
        <td/>
      </tr>
      <tr>
        <td>1,5 т</td>
        <td>{{currentBooth}}</td>
        <td>{{currentPrice === 'Для клиента' ? '8:00' : '4:00'}}</td>
        <td>1</td>
        <td>1</td>
        <td>{{ randomData * 11 }}</td>
        <td>{{ randomData }}</td>
        <td>{{ randomData }}</td>
        <td/>
        <td/>
        <td/>
        <td/>
        <td/>
        <td/>
        <td/>
        <td/>
        <td/>
      </tr>
      <tr>
        <td>3 т</td>
        <td>{{currentBooth}}</td>
        <td>{{currentPrice === 'Для клиента' ? '8:00' : '4:00'}}</td>
        <td>1</td>
        <td>1</td>
        <td>{{ randomData * 12 }}</td>
        <td>{{ randomData }}</td>
        <td>{{ randomData }}</td>
        <td/>
        <td/>
        <td/>
        <td/>
        <td/>
        <td/>
        <td/>
        <td/>
        <td/>
      </tr>
      <tr>
        <td>5 т</td>
        <td>{{currentBooth}}</td>
        <td>{{currentPrice === 'Для клиента' ? '8:00' : '4:00'}}</td>
        <td>1</td>
        <td>1</td>
        <td>{{ randomData * 13 }}</td>
        <td>{{ randomData }}</td>
        <td>{{ randomData }}</td>
        <td/>
        <td/>
        <td/>
        <td/>
        <td/>
        <td/>
        <td/>
        <td/>
        <td/>
      </tr>
      <tr>
        <td>7 т</td>
        <td>{{currentBooth}}</td>
        <td>{{currentPrice === 'Для клиента' ? '8:00' : '4:00'}}</td>
        <td>1</td>
        <td>1</td>
        <td>{{ randomData * 14 }}</td>
        <td>{{ randomData }}</td>
        <td>{{ randomData }}</td>
        <td/>
        <td/>
        <td/>
        <td/>
        <td/>
        <td/>
        <td/>
        <td/>
        <td/>
      </tr>
      <tr>
        <td>10 т</td>
        <td>{{currentBooth}}</td>
        <td>{{currentPrice === 'Для клиента' ? '8:00' : '4:00'}}</td>
        <td>1</td>
        <td>1</td>
        <td>{{ randomData * 15 }}</td>
        <td>{{ randomData }}</td>
        <td>{{ randomData }}</td>
        <td/>
        <td/>
        <td/>
        <td/>
        <td/>
        <td/>
        <td/>
        <td/>
        <td/>
      </tr>
      <tr>
        <td>20 т</td>
        <td>{{currentBooth}}</td>
        <td>{{currentPrice === 'Для клиента' ? '8:00' : '4:00'}}</td>
        <td>1</td>
        <td>1</td>
        <td>{{ randomData * 16 }}</td>
        <td>{{ randomData }}</td>
        <td>{{ randomData }}</td>
        <td/>
        <td/>
        <td/>
        <td/>
        <td/>
        <td/>
        <td/>
        <td/>
        <td/>
      </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import '@/styles/table.scss'
export default {
  name: 'Table',
  randomDataPrice: Math.random(),
  props: ['title', 'currentBooth', 'currentPayment', 'currentPrice'],
  data: () => ({
    randomDataPrice: null
  }),
  computed: {
    randomData() {
      return this.currentPayment === 'По ставке' ? 490
          : this.currentPayment === 'По часам' ? 550
          : this.currentPayment === 'По точкам' ? 780
          : this.currentPayment === 'КМ + МИН' ? 950
          : 700
    }
  },
}
</script>

