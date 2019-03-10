<template>
  <div>
    <button 
      class="bg-transparent hover:bg-blue text-blue-dark font-semibold hover:text-white py-2 px-4 border border-blue hover:border-transparent rounded" 
      @click="googleLogin">sign in with google</button>
    <button 
      class="bg-transparent hover:bg-blue text-blue-dark font-semibold hover:text-white py-2 px-4 border border-blue hover:border-transparent rounded" 
      @click="twitterLogin">sign in with twitter</button>
  </div>
</template>

<script>
import firebase from '@/plugins/firebase'
export default {
  name: 'Home',
  methods: {
    googleLogin: function() {
      firebase.auth().signInWithRedirect(new firebase.auth.GoogleAuthProvider())
    },
    twitterLogin: function() {
      firebase
        .auth()
        .signInWithRedirect(new firebase.auth.TwitterAuthProvider())
    }
  }
}
</script>
