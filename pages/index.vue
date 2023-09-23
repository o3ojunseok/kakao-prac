<template>
  <a @click="loginWithKakao">
    <img src="/kakao_login_medium_narrow.png"/>
  </a>
</template>

<script>
export default {
  name: 'IndexPage',
  methods: {
    kakaoInit() {
      Kakao.init('3802a5e2aca8230cb8cf145c47efc1bb')
      Kakao.isInitialized()
    },

    async loginWithKakao() {
      await Kakao.Auth.authorize({
        redirectUri: `${window.location.origin}/kakao-callback`
      })
    }
  },
  mounted() {
    this.kakaoInit()
  }

}
</script>

<style>

</style>