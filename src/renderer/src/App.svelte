<script lang="ts">
  const ipcHandle = (): void => window.electron.ipcRenderer.send('ping')
</script>

<h1>Hello world!</h1>
