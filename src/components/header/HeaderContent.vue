<template lang="pug">
  ods-main-header(
    headerLogoText="product"
    logoUrl="/"
    breadcrumbSeparator=">"
    actionsMenuIcon="overflow-menu"
    :showSuitesMenu="false"
    :showBreadcrumbs="true"
    :environment="env"
    :showActionsMenu="false"
    :showUserMenu="true"
    ref="header")
    template(slot="actions")
      header-actions
    template(slot="userAvatar")
      img(src="@/assets/images/header/avatar.svg")
    template(slot="user")
      user-menu
    template(slot="suites")
      suites-menu
    template(slot="notifications")
      header-notifications
    template(slot="clientLogo")
      div.ods-main-header__client-logo
        img(
          src="@/assets/images/header/logo-cliente.svg"
          alt="logo")
</template>

<script>
import HeaderActions from '@/components/header/HeaderActions'
import UserMenu from '@/components/header/UserMenu'
import SuitesMenu from '@/components/header/SuitesMenu'
import HeaderCustomContent from '@/components/header/HeaderCustomContent'
import HeaderNotifications from '@/components/header/HeaderNotifications'
import cssVars from '@/assets/scss/base/_variables.scss'

export default {
  name: 'HeaderContent',
  components: {
    HeaderActions,
    UserMenu,
    SuitesMenu,
    HeaderCustomContent,
    HeaderNotifications
  },

  data () {
    return {
      cssVars: cssVars
    }
  },

  computed: {
    env () {
      return process.env.ENV_TAG
    }
  },

  methods: {
  }
}
</script>

<style lang="scss" scoped>
  .ods-main-header__client-logo {
    width: 100px;
    img {
      width: 100%;
      max-width: 100%;
    }
  }
</style>
