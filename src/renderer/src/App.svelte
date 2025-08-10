<script lang="ts">
  import Clock from './components/Clock.svelte' 
  import Buttons from './components/Buttons.svelte';
  import Menu from './components/Menu.svelte';

  const ipcHandle = (): void => window.electron.ipcRenderer.send('ping')
</script>

<div class="flex justify-center items-center bg-slate-800 w-screen h-screen">
  <Buttons></Buttons>
  <Clock></Clock>

  <Menu></Menu>
</div>
