<template>
  <Navbar />
  <Messages v-if="isAuthenticated"/>
  <NoAuth v-else/>
</template>

<script>

import { authentication } from './helpers/useFirebase'

export default {

  setup(){

    const { isAuthenticated } = authentication()

    return { isAuthenticated }
  }
}

</script>