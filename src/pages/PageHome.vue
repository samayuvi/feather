<template>
  <q-page>
    <q-input class="q-px-md q-py-lg new-feed q-mb-sm" autogrow    bottom-slots v-model="newFeatherContent" placeholder="What's going on?" counter maxlength="300" :dense="dense">
        <template v-slot:before>
          <q-avatar size='xl'>
            <img src="https://cdn.quasar.dev/img/avatar5.jpg">
          </q-avatar>
        </template>

        <template v-slot:after>
          <q-btn :disable="!newFeatherContent" unelevated rounded color="primary" label="Feed" no-caps
           @click="addNewFeed"/>

        </template>
      </q-input>
      <q-separator size="10px" color="grey-3" class="divider"/>
        <!-- feeds -->
<template>
    <q-list  separator>
      
      <q-item
      v-for="feed in feeds" :key="feed.date" 
      class="q-py-md">
        <q-item-section avatar top>
          <q-avatar size='xl' >
            <img src="https://cdn.quasar.dev/img/avatar2.jpg">
          </q-avatar>
        </q-item-section>

        <q-item-section>
          <q-item-label class="text-subtitle1">
            <strong>Lena</strong>
            <span class="text-grey-7">@lenakkkk</span>
            </q-item-label>
          <q-item-label class="feed-content text-body1" >{{feed.content}}
          </q-item-label>
          <div class="row justify-between feed-icons">
          <q-btn color="grey" size="sm" flat rounded icon="far fa-comment"></q-btn>
          <q-btn color="grey" size="sm" flat rounded icon="fas fa-retweet"></q-btn>
          <q-btn color="grey" size="sm" flat rounded icon="far fa-heart"></q-btn>
          <q-btn color="grey" size="sm" flat rounded icon="fas fa-share"></q-btn>

        </div>
        </q-item-section>

        <q-item-section side top>
          {{feed.date | relativeDate}}
        </q-item-section>
        
      </q-item>


     

   

      
    </q-list>
</template>
  </q-page>
</template>

<script>
import { formatDistance } from 'date-fns'
export default {
  name: 'PageHome',
  data(){

    return {newFeatherContent: '',
    feeds:[{
      content: 'Lorem ipsum dolor sit amet,'
      +'consectetur adipiscing elit, sed do'
      + 'eiusmod tempor incididunt ut labore'
       + 'et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. ',
      date: 1623249051327
    },{
      content: 'Lorem ipsum dolor sit amet, consectetur.',
      date: 1623249054444
    }
    ]
    }
    
  },
  methods:{
    addNewFeed(){
     let newFeed={
       content: this.newFeatherContent,
       date: Date.now()
     }
     this.feeds.unshift(newFeed)
}
  },
  filters:{
    relativeDate(value){
      return formatDistance(value, new Date())

    }
  }
  
}

</script>

<style lang="sass">

.feed-content
  white-space: pre-line
.divider
 border-top:1px solid
 border-bottom:1px solid
 border-color:$grey-5
.new-feed
 textarea
  font-size:19px
  line-height:1.4!important
.feed-icons
   margin-left:-10px
</style>
