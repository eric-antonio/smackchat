<template>
  <q-page class="flex  q-pa-md" >


    <q-list
    class="full-width" separator>
      <q-item
        v-for="user in users"
        :key="user.id"
        to="/chat"
        clickable
        v-ripple>
        <q-item-section avatar>
          <q-avatar color="primary" text-color="white">
            {{ user.name.charAt(0) }}
          </q-avatar>
        </q-item-section>

        <q-item-section>
          <q-item-label>{{ user.name }}</q-item-label>

        </q-item-section>

        <q-item-section side>

          <q-badge :color="user.online? 'green-6' : 'grey-4'">
            {{user.online? 'Online': 'Ofline'}}
          </q-badge>

        </q-item-section>

      </q-item>

    </q-list>

  </q-page>
</template>

<script>
  import { defineComponent } from 'vue'

  // Script da q-list
export default {
  setup () {
    return {
      users:[ {
        id: 1,
        name: 'Ruddy Jedrzej',
        online: true,
      }, {
        id: 2,
        name: 'Mallorie Alessandrini',
        online: false,
      }, {
        id: 3,
        name: 'Elisabetta Wicklen',
        online: true,
      }, {
        id: 4,
        name: 'Seka Fawdrey',
        online: false,
      }, {
        id: 5,
        name: 'Fernada Fredericky',
        online: true,
      }]
    }
  }
}
</script>

<style>
</style>
