<template>
  <div id="mypage">
    <p>こんにちは, {{ user.displayName }}さん</p>
    <button 
      class="bg-transparent hover:bg-blue text-blue-dark font-semibold hover:text-white py-2 px-4 border border-blue hover:border-transparent rounded" 
      @click="logout">ログアウト</button>
  </div>
</template>

<script>
import firebase from '@/plugins/firebase'
export default {
  name: 'Mypage',
  props: ['user'],
  methods: {
    logout: function() {
      firebase.auth().signOut()
    }
  }
}
</script>
