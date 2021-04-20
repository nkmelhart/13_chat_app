<template>
  <div class="container mx-w-2xl mx-auto flex my-4 bg-gray-700 rounded-full">
      <div>
          <img
            class="rounded-full h-12"
            :src="message.userPhotoURL"
            :alt="`Avatar of ${message.userName}`"
            />
      </div>
      <div class="flex flex-grow text-gray-300">
          <div class="flex flex-grow justify-between items-center text-gray300 mx-4">
          <p>{{message.text}}</p>
          <p class="text-sm italic">{{message.userName}}</p>
          </div>
      </div>
  </div>
</template>

<script setup>

    import { defineProps, computed, ref } from 'vue'
    import { authentication } from '../helpers/useFirebase'

        const { user } = authentication()

        const props = defineProps({
            message: {
                type: Object,
                default: () => ({
                    userName: '',
                    userID: '',
                    userPhotoURL: '',
                    text: '',
                    createdAt: '',
                })
            }
        })

</script>