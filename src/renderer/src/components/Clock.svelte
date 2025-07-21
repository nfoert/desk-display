<script lang="ts">
  let now = new Date()

  setInterval(() => {
    now = new Date()
  }, 1000)
</script>

<div class="flex flex-col items-center">
  <span class="text-6xl text-white">
    {now
      .toLocaleTimeString('en-US', {
        hour: '2-digit',
        minute: '2-digit',
        hour12: true
      })
      .replace(/ AM| PM/, '')}
  </span>
  <span class="text-white"
    >{now
      .toLocaleDateString('en-US', { month: '2-digit', day: '2-digit', year: '2-digit' })
      .replace(/(\d{2})\/(\d{2})\/(\d{2})/, '$1/$2/$3')}</span
  >
</div>
