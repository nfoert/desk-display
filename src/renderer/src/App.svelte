<script lang="ts">
  const ipcHandle = (): void => window.electron.ipcRenderer.send('ping')
</script>

<h1 class="font-bold text-3xl">Hello world!</h1>
