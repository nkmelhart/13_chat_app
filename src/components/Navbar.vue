<template>
  <div class="bg-purple-900 text-coolGray-300 py-6">
      <div class="container mx-auto flex justify-between items-center">
        <div class="brand flex items-center space-x-2 ">
            <mdi:message-processing-outline class="text-3xl"/>
            <h1 class="text-3xl font-thin tracking-wide">Chit<span class="font-bold text-yellow-300">Chat</span></h1>
        </div>
        <div class="menu">
            <div v-if="!isAuthenticated">
                <button
                class="bg-green-700 text-white py-2 px-4 rounded-full hover:bg-green-900 focus:outline-none focus:ring-4 focus:ring-green-500" @click="googlePopup"
                >Login</button>
            </div>
            <div v-else class="flex items-center space-x-8">
                <p>Welcome {{ user?.displayName }}</p>
                <button
                class="bg-red-700 text-white py-2 px-4 rounded-full hover:bg-green-900 focus:outline-none focus:ring-4 focus:ring-green-500" @click="signOut"
                >Logout</button>
            </div>
        </div>
      </div>
  </div>
</template>

<script>
import {authentication} from '../helpers/useFirebase'

export default {
    setup() {
        const {isAuthenticated, user, googlePopup, signOut } = authentication()

        return{ isAuthenticated, user, googlePopup, signOut}
    }
}
</script>

<style>

</style>