<template>
  <section v-if="hasFruit">
    <h1>Fruits</h1>
    <ul>
      <li 
        v-for="fruit in fruits" 
        :key="fruit">
        {{ fruit }}
        </li>
    </ul>
  </section>
  <section>
    <h1>Reverse Fruits</h1>
    <ul>
      <li 
        v-for="fruit in reverseFruit"
        :key="fruit">
        {{ fruit }}
        </li>
    </ul>
  </section>
</template>

<script>
export default {
  data() {
    return {
      fruits: [
        'Apple', 'Banana', 'Cherry'
      ]
    }
  },
  // computed: 계산된 데이터는 데이터 옵션에 정의한 특정한 데이터를 추가적으로 연산을 통해 정의를 한 다음
  // 그 값은 반환해서 사용할 수 있는 새로운 계산된 데이터
  computed: {
    hasFruit() {
      return this.fruits.length > 0
    },
    reverseFruit() {
      return this.fruits.map(fruit => {
        // 'Apple' => ['A','p','p','l','e']
        // => ['e','l','p','p','A'] => 'elppA'
        return fruit.split('').reverse().join('')
      })
    }
  }
}
</script>
