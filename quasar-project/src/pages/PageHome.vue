<template>
  <q-page>
    <div class="q-py-lg q-px-md">
      <q-input
        bottom-slots
        v-model="newTweetContent"
        placeholder="What's happening?"
        counter
        maxlength="280"
      >
          <template v-slot:before>
            <q-avatar>
              <img src="https://cdn.quasar.dev/img/avatar5.jpg">
            </q-avatar>
          </template>

          <template v-slot:after>
            <q-btn round dense flat icon="send" />
          </template>
        </q-input>
    </div>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'PageHome',
  data() {
    return {
      newTweetContent: ''
    }
  }
})
</script>
