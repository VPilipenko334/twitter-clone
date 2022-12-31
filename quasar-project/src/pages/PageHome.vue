<template>
  <q-page>
    <div class="q-py-lg q-px-md">
      <q-input
        bottom-slots
        v-model="newTweetContent"
        placeholder="What's happening?"
        counter
        maxlength="280"
        autogrow
      >
          <template v-slot:before>
            <q-avatar size="xl">
              <img src="https://static.vecteezy.com/system/resources/previews/004/842/371/original/hipster-bear-avatar-vector.jpg">
            </q-avatar>
          </template>

          <template v-slot:after>
            <q-btn
              :disable = "!newTweetContent"
              unelevated
              rounded
              color="primary"
              label="Tweet"
              no-caps
            />
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
