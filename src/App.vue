<template lang="pug">
  .wrapper
    header
      .navbar
        .container
          .navbar-content
            router-link.header-logo(
              to="/"
            ) Film library
            .button-burger(
              @click="menuShow = !menuShow"
              :class="{ active: menuShow }"
            )
              span.line.line-1
              span.line.line-2
              span.line.line-3
            .navbar-list__wrapper(
              :class="{ active: menuShow }"
            )
              ul.navbar-list
                li.navbar-item(
                  v-for="link in LinkMenu" :key="link.title"
                  @click="menuShow = false"
                  :class="{ active: menuShow }"
                )
                  router-link.navbar-link(
                    :to="`${link.url}`"
                  ) {{ link.title }}
    .content-wrapper
      router-view
</template>

<script>
export default {
  data () {
    return {
      menuShow: false,
      LinkMenu: [
        {title: 'Home', url: '/'},
        {title: 'Login', url: '/login'},
        {title: 'Register', url: '/registration'}
      ]
    }
  }
}
</script>

<style lang="stylus">
@import "./assets/stylus/main.styl";
</style>
