<template>
  <q-page class="flex ">

    <h5> Chat page</h5>
    <q-footer elevated>

        <q-toolbar>

         <q-input
            class="full-width"
            id="label"
            outlined
            bg-color="white"
            rounded
            v-model="text"
            label="Message"
            dense>

            <template v-slot:after>
              <q-btn round dense flat icon="send"  color="white"/>
            </template>

          </q-input>

        </q-toolbar>

      </q-footer>

  </q-page>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({

})
</script>

<style>
  #label{
    margin-bottom: 20px;
  }
</style>
