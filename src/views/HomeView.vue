<template lang="">
  <TheHeader />
  <main class="p-4">
    <section class="row g-4 align-items-start">
      <SideBar class="col-lg-4 col-sm-6" />
      <StudentsTable class="col-lg-8 col-sm-6" />
    </section>
  </main>

  <TheFooter />
</template>
<script>
import TheHeader from '../components/TheHeader.vue'
import TheFooter from '../components/TheFooter.vue'
import StudentsTable from '../components/StudentsTable.vue'
import SideBar from '../components/SideBar.vue'
export default {
  components: {
    TheHeader,
    TheFooter,
    StudentsTable,
    SideBar
  }
}
</script>
<style lang=""></style>
