<template>
  <div>
    <md-button id="side-bar-switch" class="md-icon-button" @click.native="toggleSideNav">
      <md-icon>menu</md-icon>
    </md-button>
    <md-sidenav class="md-left md-fixed" ref="sideBar">
      <div id="user-info">
        <router-link to="/SignIn" @click.native="toggleSideNav">
          <span id="user-name">用户名</span>
          <md-avatar id="user-avatar" class="md-large">
            <img src="//placeimg.com/40/40/people/1" />
          </md-avatar>
        </router-link>
      </div>
      <md-list>
        <md-list-item v-for="link in links">
          <router-link :to="link.to" @click.native="toggleSideNav">
            <md-icon>{{ link.icon }}</md-icon>
            <span>{{ link.text }}</span>
          </router-link>
        </md-list-item>
      </md-list>
    </md-sidenav>
  </div>
</template>

<script>
  export default {
    name: 'sidebar',
    data () {
      return {
        links: [
          { icon: 'search', text: '查询', to: '/Search' },
          { icon: 'shopping', text: '交易', to: '/Deal' },
          { icon: 'subject', text: '流水记录', to: '/Record' },
          { icon: 'face', text: '账号管理', to: '/Signup.html' }
        ]
      }
    },
    methods: {
      toggleSideNav () {
        this.$refs.sideBar.toggle()
      }
    }
  }
</script>

<style scoped>
  #side-bar-switch {
    position: fixed;
    left: 16px;
    top: 16px;
  }

  #user-info {
    width: 100%;
    height: 160px;
    background-color: #234;
  }

  #user-avatar {
    position: absolute;
    top: 128px;
    right: 32px;
    z-index: 99;
  }

  #user-name {
    color: #fff;
    position: absolute;
    top: 128px;
    left: 16px;
  }
</style>
