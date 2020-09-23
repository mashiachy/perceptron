<template>
  <header class="header">
    <teleport target="header"></teleport>
  </header>
  <Main></Main>
  <footer class="footer">Лабораторая работа 2. Выполнил Шарков Леонид. ЕТ-414.</footer>
</template>

<script>
import Main from './components/Main';

export default {
  components: {Main}
}

</script>

<style lang="sass">
body
  margin: 0

#app
  font-family: Avenir, Helvetica, Arial, sans-serif
  -webkit-font-smoothing: antialiased
  -moz-osx-font-smoothing: grayscale
  color: #2c3e50
  min-height: 100vh
  display: flex
  flex-direction: column
  align-items: stretch

.header, .footer
  text-align: center
  box-shadow: 0 0 5px rgba(23,23,23,0.3)

.header
  padding: 10px 50px
  margin-bottom: 20px

.footer
  padding: 20px 50px
  margin-top: auto
</style>
