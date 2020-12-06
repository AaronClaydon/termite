<template>
  <div class="home">
    <div>
      <Console />
      <b-tabs content-class="mt-3" justified>
        <b-tab title="First" active><p>I'm the first tab</p></b-tab>
        <b-tab title="Second"><p>I'm the second tab</p></b-tab>
        <b-tab title="Very, very long title"><p>I'm the tab with the very, very long title</p></b-tab>
        <b-tab title="Disabled" disabled><p>I'm a disabled tab!</p></b-tab>
      </b-tabs>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import Console from '@/components/Console.vue'

export default {
  name: 'Home',
  components: {
    // HelloWorld,
    Console
  }
}
</script>
