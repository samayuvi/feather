<template>
  <q-layout view="lHr lpR fFf">

    <q-header bordered class="bg-white text-black">
      <q-toolbar>
        <q-btn dense flat round icon="menu" @click="left = !left" />

        <q-toolbar-title class="text-weight-bold mobile-hide">
          <q-avatar>
            <img src="https://cdn.quasar.dev/logo-v2/svg/logo-mono-white.svg">
          </q-avatar>
         <span class= "gt-sm">{{$route.name}}</span>        
         <q-icon
         class="q-pa-md lt-md header-icon-mb absolute-center"
         name="fas fa-feather"
         size="sm"
         color="primary"></q-icon>
         </q-toolbar-title>

        <q-btn dense flat round icon="menu" @click="right = !right" />
      </q-toolbar>
    </q-header>

    <q-drawer width="280" show-if-above v-model="left" side="left" bordered>
      <q-icon class="q-pa-md" color="primary" name="fas fa-feather" size="lg"/>
      

      <q-list >
      <q-item clickable v-ripple to="/" exact>
        <q-item-section avatar>
          <q-icon  name="home" size="md"/>
        </q-item-section>

        <q-item-section class="text-h6 text-weight-bold">Home</q-item-section>
      </q-item>

      <q-item clickable v-ripple to="/about" exact>
        <q-item-section avatar>
          <q-icon  name="info" size="md"/>
        </q-item-section>

        <q-item-section class="text-h6 text-weight-bold">About</q-item-section>
      </q-item>

      

      
    </q-list>
    </q-drawer>

    <q-drawer show-if-above v-model="right"  side="right" bordered>
      <q-input color="primary"
       outlined 
       rounded 
       placeholder="Search Twitter" 
       class="q-ma-md"
       dense
       >
       
        <template v-slot:prepend>
          <q-icon name="event" />
        </template>
      </q-input>
       <q-list>
      <q-item>
        <q-item-section>
          <q-item-label overline class="text-grey">Politics</q-item-label>
          <q-item-label class="text-bold">Smth bad happened</q-item-label>
          <q-item-label caption lines="2">Lorem ipsum dolor sit amet consectetur adipisicing elit. Possimus error voluptatum odio ipsa quis impedit, harum tempore.</q-item-label>
        </q-item-section>
        

        <q-item-section side top>
          <q-item-label caption>5 min ago</q-item-label>
          <q-icon name="star" color="yellow" />
        </q-item-section>
      </q-item>

      <q-separator spaced inset />
      <q-item>
        <q-item-section>
          <q-item-label overline class="text-grey">Politics</q-item-label>
          <q-item-label class="text-bold">Smth bad happened</q-item-label>
          <q-item-label caption lines="2">Lorem ipsum dolor sit amet consectetur adipisicing elit. Possimus error voluptatum odio ipsa quis impedit, harum tempore.</q-item-label>
        </q-item-section>
        

        <q-item-section side top>
          <q-item-label caption>5 min ago</q-item-label>
        </q-item-section>
      </q-item>

      <q-separator spaced inset />
      <q-item>
        <q-item-section>
          <q-item-label overline class="text-grey">Politics</q-item-label>
          <q-item-label class="text-bold">Smth bad happened</q-item-label>
          <q-item-label caption lines="2">Lorem ipsum dolor sit amet consectetur adipisicing elit. Possimus error voluptatum odio ipsa quis impedit, harum tempore.</q-item-label>
        </q-item-section>
        

        <q-item-section side top>
          <q-item-label caption>5 min ago</q-item-label>
        </q-item-section>
      </q-item>

      <q-separator spaced inset />
    </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>

  </q-layout>
</template>

<script>
export default {
  data () {
    return {
      left: false,
      right: false
    }
  }
}
</script>
<style lang="sass">
  
</style>