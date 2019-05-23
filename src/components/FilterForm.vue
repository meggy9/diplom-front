<template>
  <div class="form">
    {{ orgTypeName }}
    <input type="date" placeholder="Дата">
    <br>
    <input type="text" placeholder="ФИО руководителя">
    <br>
    <select v-model="rightForm">
      <option disabled value="">Вид организации:</option>
      <option v-for="option in organizationTypeList" :value="option.value" :key="option.value">{{ option.label }}</option>
    </select><br>
    <label>Сведения о формах социального обслуживания</label><br>
    <label v-for="option in serviceFormList" :key="option.label">
      <input type="checkbox" v-model="option.status" />
      {{ option.label }}<br>
    </label>
    <label>Сведения о видах социальных услуг</label><br>
    <label v-for="option in serviceTypeList" :key="option.label">
      <input type="checkbox" v-model="option.status" />
      {{ option.label }}<br>
    </label>
    <label>Форма собственности</label><br>
    <label v-for="option in rightFormList" :key="option.label">
      <input type="checkbox" v-model="option.status" />
      {{ option.label }}<br>
    </label>
  </div>
</template>

<script>
export default {
  name: 'FilterForm',
  props: {
    value: String,
    msg: String
  },
  data() {
    return {
      someData: '',
      organizationName: '',
      rightForm: '',
      organizationTypeList: [
        {
          value: '1',
          label: 'Детский дом-интернат для умственно отсталых детей'
        },
        {
          value: '2',
          label: 'Дом интернат для престарелых и инвалидов'
        },
        {
          value: '3',
          label: 'Психоневрологический интернат'
        },
        {
          value: '4',
          label: 'Реабилитационный центр для детей и подростков с ограниченными возможностями'
        },
        {
          value: '5',
          label: 'Социальный приют для детей и подростков'
        },
        {
          value: '6',
          label: 'Центр социальной адаптации для лиц без определенного места жительства и занятий'
        },
        {
          value: '7',
          label: 'Центр социальной помощи семье и детям'
        },
        {
          value: '8',
          label: 'Центр реабилитации инвалидов'
        },
        {
          value: '9',
          label: 'Центр социального обслуживания населения'
        }
      ],
      rightFormList: [
        {
          label: 'государственная',
          status: 'true'
        },
        {
          label: 'муниципальная',
          status: 'true'
        },
        {
          label: 'частная',
          status: 'true'
        }
      ],
      serviceFormList: [
        {
          label: 'стационарная',
          status: true
        },
        {
          label: 'полустационарная',
          status: true
        },
        {
          label: 'на дому',
          status: true
        }
      ],
      serviceTypeList: [
        {
          label: 'социально-бытовые',
          status: true
        },
        {
          label: 'социально-медицинские',
          status: true
        },
        {
          label: 'социально-психологические',
          status: true
        },
        {
          label: 'социально-педагогические',
          status: true
        },
        {
          label: 'социально-трудовые',
          status: true
        },
        {
          label: 'социально-правовые',
          status: true
        },
        {
          label: 'срочные социальные услуги',
          status: true
        },
        {
          label: 'услуги в целях повышения коммуникативного потенциала получателей социальных услуг, имеющих ограничения жизнедеятельности ',
          status: true
        }
      ]
    }
  },
  computed: {
    orgTypeName() {
      if (!this.rightForm) return
      return this.organizationTypeList.find((item) => {
        return item.value === this.rightForm
      }).label
    }
  },
  methods: {
    // someDataOut() {
    //   this.someData =
    // }
  }
}
</script>

<style scoped lang="scss">
  
</style>
