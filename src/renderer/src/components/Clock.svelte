<script lang="ts">
  let now = new Date();
  let colonOpacity = 1;

  setInterval(() => {
    now = new Date();
    colonOpacity = colonOpacity === 1 ? 0.5 : 1;
  }, 1000);

  $: hours = now.toLocaleTimeString('en-US', {
    hour: '2-digit',
    hour12: true
  }).replace(/^0/, '').replace(/ AM| PM/, '');

  $: minutes = now.toLocaleTimeString('en-US', {
    minute: '2-digit'
  }).padStart(2, '0');

  $: date = now.toLocaleDateString('en-US', {
    month: '2-digit',
    day: '2-digit',
    year: '2-digit'
  });
</script>

<style>
  .colon {
    transition: opacity 0.5s ease-in-out;
    display: inline-block;
    width: 0.6ch; /* tight spacing */
    text-align: center;
  }
</style>

<div class="flex flex-col items-center">
  <span class="text-6xl text-white">
    {hours}<span class="colon" style={`opacity: ${colonOpacity}`}>:</span>{minutes}
  </span>
  <span class="text-white text-xl mt-1">
    {date}
  </span>
</div>

