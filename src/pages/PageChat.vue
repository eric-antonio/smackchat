<template>
  <q-page class="flex ">

    <div class="q-pa-md column col justify-end" >
      <q-chat-message
      v-for="message in messages"
        :key="message.text"
        
        :name="[message.from]"
        :text="[message.text]"
        :sent="message.from =='me' ? true: false"
      />
    </div>
    <q-footer elevated>

        <q-toolbar>

         <q-input
            class="full-width"
            id="label"
            outlined
            bg-color="white"
            rounded
            v-model="newMessage"
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

  data(){
    return{
      newMessage: '',
      messages:[
        {
          text:'Oi Baby❤️ Tudo bem!',
          from:'me'
        },{
          text:'Olá Honey🥰😍, estou e tu?',
          from:'them'
        },{
          text:'Estiu sim. Estou com saudades🥺, vemonos na sexta?',
          from:'me'
        }
      ]
    }
  }

})
</script>

<style>
  #label{
    margin-bottom: 20px;
  }
</style>
