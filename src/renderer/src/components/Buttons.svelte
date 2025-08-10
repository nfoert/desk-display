<script>
    let open = false;
</script>

<div class="flex flex-col absolute top-0 left-0 h-screen z-10 py-8 pl-2
            bg-gradient-to-r from-10% to-transparent to-90% backdrop-blur-sm
            transition-all duration-500 ease-in-out justify-between px-4"
     class:w-screen={open}
     class:w-20={!open}
     class:from-slate-900={open}
     class:from-transparent={!open}>
    
    {#each [1, 2, 3, 4] as num}
        <div class="flex flex-row items-center text-white transition-all duration-500 ease-in-out">
            <i class="ph-bold ph-circle transition-opacity duration-300 ease-in-out" 
               class:opacity-100={open} 
               class:opacity-50={!open}></i>

            <div class="ml-2 overflow-hidden transition-all duration-500 ease-in-out"
                 style="max-width: {open ? '120px' : '0px'}"
                 id="button-{num}">
                <p class="whitespace-nowrap transition-opacity duration-300 ease-in-out"
                   class:opacity-100={open}
                   class:opacity-0={!open}>
                    Button {num}
                </p>
            </div>
        </div>
    {/each}
</div>
