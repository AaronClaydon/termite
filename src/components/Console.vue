<template>
    <div class="console" :id="'terminal-' + 1"></div>
</template>
<script>
// import * as Terminal from 'xterm'
import Terminal from '@/xterm'
export default {
  name: 'Console',
  props: {
    terminal: {
      type: Object,
      default: null
    }
  },
  data () {
    return {
      term: null,
      terminalSocket: null
    }
  },
  methods: {
    runRealTerminal () {
      console.log('webSocket is finished')
    },
    errorRealTerminal () {
      console.log('error')
    },
    closeRealTerminal () {
      console.log('close')
    }
  },
  mounted () {
    console.log('pid : ' + 1 + ' is on ready')
    const terminalContainer = document.getElementById('terminal-' + 1)
    this.term = new Terminal({
      cursorBlink: true,
      cols: 200,
      rows: 200
    })
    this.term.open(terminalContainer)
    // open websocket
    // this.terminalSocket = new WebSocket('ws://127.0.0.1:3000/terminals/' + this.terminal.pid)
    // this.terminalSocket.onopen = this.runRealTerminal
    // this.terminalSocket.onclose = this.closeRealTerminal
    // this.terminalSocket.onerror = this.errorRealTerminal
    // this.term.attach(this.terminalSocket)
    // this.term._initialized = true
    console.log('mounted is going on')
  },
  beforeDestroy () {
    // this.terminalSocket.close()
    this.term.destroy()
  }
}
</script>
