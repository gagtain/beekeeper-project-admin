<template>

  <section class="page-content">
  <div v-show="showContent">
  <section class="search-and-user">
    <form>
      <input type="search" placeholder="Search Pages...">
      <button type="submit" aria-label="submit form">
        <svg aria-hidden="true">
          <use xlink:href="#search"></use>
        </svg>
      </button>
    </form>
    <div class="admin-profile">
      <span class="greeting">Hello admin</span>
      <div class="notifications">
        <span class="badge">1</span>
        <svg>
          <use xlink:href="#users"></use>
        </svg>
      </div>
    </div>
  </section>
  </div>
  <NuxtPage/>
  </section>
</template>

<style src="~/assets/styles/new.css" scoped></style>
<script>
export default {
  data() {
      return{
      showContent: true,
      }
    },
    created(){
      if (this.$route.path == '/admin/login'){
        this.showContent = false
      }

    },
  watch: {
    '$route.path'() {
      if (this.$route.path != '/admin/login'){
        this.showContent = true
      } else {
        this.showContent = false
      }
    }
  }
}
</script>
