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
  	  	<q-form
  	  		@submit="sendMessage"
  	  		class="full-width">
	  	    <q-input
	  	    	v-model="newMessage"
	  	    	bg-color="white"
	  	    	outlined
	  	    	rounded
	  	    	label="Message"
	  	    	dense>

	  	      <template v-slot:after>
	  	        <q-btn
	  	        	round
	  	        	dense
	  	        	flat
	  	        	type="submit"
	  	        	color="white"
	  	        	icon="send" />
	  	      </template>
	  	    </q-input>
  	  	</q-form>
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
  },
  methods:{
    sendMessage(){
      this.messages.push({
        text: this.newMessage,
        from:'me'

      })
    }
  }

})
</script>

<style>

</style>
