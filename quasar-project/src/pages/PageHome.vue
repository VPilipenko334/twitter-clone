<template>
  <q-page>
    <div class="q-py-lg q-px-md">
      <q-input
        class="new-tweet"
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

        <q-separator inset="item"/>

      <q-list>
        <q-item clickable v-ripple>
          <q-item-section avatar>
            <q-avatar>
              <img src="https://static.vecteezy.com/system/resources/previews/004/842/371/original/hipster-bear-avatar-vector.jpg">
            </q-avatar>
          </q-item-section>

        <q-item-section>
          <q-item-label class="text-grey-5">@veronikapilipenko</q-item-label>
          <q-item-label>
            <span class="text-weight-bold">Veronika</span>
            Lorem ipsum dolor sit, amet consectetur adipisicing elit. Facere exercitationem eligendi ullam excepturi architecto, ea vitae corporis quia ducimus ex quidem inventore quis natus consectetur quas repellendus asperiores quibusdam molestias.
          </q-item-label>
        </q-item-section>

        <q-item-section side top>
          1 min ago
        </q-item-section>
      </q-item>
    </q-list>


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

<style>
.new-tweet {
  font-size: 19px;
  line-height: 1.4 !important
}
</style>