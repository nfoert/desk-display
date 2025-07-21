<script lang="ts">
  import Clock from './components/Clock.svelte'

  const ipcHandle = (): void => window.electron.ipcRenderer.send('ping')
</script>

<div class="flex justify-center items-center bg-slate-800 w-screen h-screen">
  <Clock></Clock>
</div>
