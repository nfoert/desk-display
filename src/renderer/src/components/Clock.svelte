<script lang="ts">
  // import { writable } from "svelte/store";

  let now = new Date();
  let colonOpacity = 1;

  setInterval(() => {
    now = new Date();
  }, 1000);

  setInterval(() => {
    colonOpacity = colonOpacity === 1 ? 0.5 : 1
  }, 500);

  function getHours() {
    return now
      .toLocaleTimeString('en-US', {
        hour: '2-digit',
        hour12: true
      })
      .replace(/^0/, '')
      .replace(/ AM| PM/, '');
  }

  function getMinutes() {
    return now.toLocaleTimeString('en-US', {
      minute: '2-digit'
    }).padStart(2, '0');
  }

  function getDate() {
    return now.toLocaleDateString('en-US', {
      month: '2-digit',
      day: '2-digit',
      year: '2-digit'
    });
  }
</script>

<div class="flex flex-col items-center">
  <span class="text-6xl text-white">
    {getHours()}<span class="transition-all ease-in-out duration-300" style={`opacity: ${colonOpacity}`}>:</span>{getMinutes()}
  </span>
  <span class="text-white text-xl mt-1">
    {getDate()}
  </span>
</div>

