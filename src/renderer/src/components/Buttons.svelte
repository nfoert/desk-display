<script>
  import { onMount } from "svelte"

    let open = false;

    let modes = {
        "main": {
            "button-1": {
                "icon": "",
                "text": "",
                "action": ""
            },
            "button-2": {
                "icon": "",
                "text": "",
                "action": ""
            },
            "button-3": {
                "icon": "",
                "text": "",
                "action": ""
            },
            "button-4": {
                "icon": "ph-bold ph-squares-four",
                "text": "Menu",
                "action": "menu_open"
            }
        },
        "menu": {
            "button-1": {
                "icon": "",
                "text": "",
                "action": ""
            },
            "button-2": {
                "icon": "",
                "text": "",
                "action": ""
            },
            "button-3": {
                "icon": "",
                "text": "",
                "action": ""
            },
            "button-4": {
                "icon": "ph-bold ph-x",
                "text": "Close",
                "action": "menu_close"
            }
        }
    }

    function setMode(mode, show=false) {
        if (mode in modes) {
            document.querySelector("#button-1 p").innerHTML = modes[mode]["button-1"]["text"];
            document.querySelector("#button-1 > i").classList = modes[mode]["button-1"]["icon"];

            document.querySelector("#button-2 p").innerHTML = modes[mode]["button-2"]["text"];
            document.querySelector("#button-2 > i").classList = modes[mode]["button-2"]["icon"];

            document.querySelector("#button-3 p").innerHTML = modes[mode]["button-3"]["text"];
            document.querySelector("#button-3 > i").classList = modes[mode]["button-3"]["icon"];

            document.querySelector("#button-4 p").innerHTML = modes[mode]["button-4"]["text"];
            document.querySelector("#button-4 > i").classList = modes[mode]["button-4"]["icon"];

            if (show) {
                open = true;

                setTimeout(() => {
                    open = false;
                }, 2000)
            }
        }
    }

    onMount(() => {
        window.addEventListener('buttons_set_mode', (event) => {
            event.stopImmediatePropagation();
            const { name, show } = event.detail;
            
            setMode(name, show);
        });
        
        setTimeout(() => {
            setMode("main");
        }, 100);
    });
</script>

<div class="flex flex-col absolute top-0 left-0 h-screen z-10 py-8 pl-4
            bg-gradient-to-r from-10% to-transparent to-90%
            transition-all duration-500 ease-in-out justify-between px-4"
     class:w-screen={open}
     class:w-20={!open}
     class:from-slate-900={open}
     class:from-transparent={!open}>
    
    {#each [1, 2, 3, 4] as num}
        <div class="flex flex-row items-center text-white transition-all duration-500 ease-in-out" id={`button-${num}`}>
            <i class="ph-bold ph-circle transition-opacity duration-300 ease-in-out" 
               class:opacity-100={open} 
               class:opacity-30={!open}></i>

            <div class="ml-2 overflow-hidden transition-all duration-500 ease-in-out"
                 style="max-width: {open ? '120px' : '0px'}">
                <p class="whitespace-nowrap transition-opacity duration-300 ease-in-out"
                   class:opacity-100={open}
                   class:opacity-0={!open}>
                    Button {num}
                </p>
            </div>
        </div>
    {/each}
</div>
