<script lang="ts">
    let open = false;

    $: style = open
    ? "flex flex-col absolute top-0 left-0 h-screen justify-between py-8 pl-2 bg-gradient-to-r from-black/50 to-transparent pr-10 backdrop-blur-xs transition-all"
    : "flex flex-col absolute top-0 left-0 h-screen justify-between py-8 pl-2 opacity-50 transition-all";
</script>

<div class={style}>
    <div class="flex flex-row gap-1 text-white items-center">
        <i class="ph-bold ph-circle"></i>
        <p class={open ? '' : 'hidden'}>Button 1</p>
    </div>

    <div class="flex flex-row gap-1 text-white items-center">
        <i class="ph-bold ph-circle"></i>
        <p class={open ? '' : 'hidden'}>Button 2</p>
    </div>

    <div class="flex flex-row gap-1 text-white items-center">
        <i class="ph-bold ph-circle"></i>
        <p class={open ? '' : 'hidden'}>Button 3</p>
    </div>

    <div class="flex flex-row gap-1 text-white items-center">
        <i class="ph-bold ph-circle"></i>
        <p class={open ? '' : 'hidden'}>Button 4</p>
    </div>
</div>