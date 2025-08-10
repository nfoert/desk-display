<script>
    import spotify_icon from "../assets/spotify.png";
    import google_calendar_icon from "../assets/google-calendar.png";
    import todoist_icon from "../assets/todoist.png";
    import home_assistant_icon from "../assets/home-assistant.png";

    let open = true;

    const delays = [0, 100, 200, 100, 200, 300];

    // setInterval(() => {
    //     open = !open;

    //     if (open) {
    //         window.dispatchEvent(new CustomEvent("buttons_set_mode", { detail: { name: "menu", show: true } }));
    //     } else {
    //         window.dispatchEvent(new CustomEvent("buttons_set_mode", { detail: { name: "main", show: false } }));
    //     }
    // }, 3000);
</script>

<div class="flex flex-row z-5 w-screen h-screen absolute top-0 left-0 transition-all duration-300 ease-in-out bg-slate-900/50"
     class:opacity-0={!open}
     class:opacity-100={open}
     class:backdrop-blur-sm={open}
     class:backdrop-blur-none={!open}>
    
    <div class="grid grid-cols-3 grid-rows-2 gap-4 p-10 text-white text-2xl">

        <!-- Clock -->
        <div class="border-white border-2 aspect-square rounded-2xl flex justify-center items-center transition-all bg-slate-700/50 hover:bg-slate-800 hover:scale-105 active:scale-95 overflow-hidden"
             style="transition-delay: {open ? delays[0] : 0}ms"
             class:scale-100={open}
             class:scale-0={!open}>
            <i class="ph-bold ph-clock"></i>
        </div>

        <!-- Spotify -->
        <div class="border-white border-2 aspect-square rounded-2xl flex justify-center items-center transition-all bg-black hover:scale-110 active:scale-95 overflow-hidden"
             style="transition-delay: {open ? delays[1] : 0}ms"
             class:scale-100={open}
             class:scale-0={!open}>
            <img class="scale-50" src={spotify_icon} alt="Spotify Logo">
        </div>

        <!-- Google Calendar -->
        <div class="border-white border-2 aspect-square rounded-2xl flex justify-center items-center transition-all bg-white hover:scale-110 active:scale-95 overflow-hidden"
             style="transition-delay: {open ? delays[2] : 0}ms"
             class:scale-100={open}
             class:scale-0={!open}>
            <img class="scale-50" src={google_calendar_icon} alt="Google Calendar Logo">
        </div>

        <!-- Todoist -->
        <div class="border-white border-2 aspect-square rounded-2xl flex justify-center items-center transition-all bg-[#e44232] hover:scale-110 active:scale-95 overflow-hidden"
             style="transition-delay: {open ? delays[3] : 0}ms"
             class:scale-100={open}
             class:scale-0={!open}>
            <img class="scale-100" src={todoist_icon} alt="Todoist Logo">
        </div>

        <!-- Home Assistant -->
        <div class="border-white border-2 aspect-square rounded-2xl flex justify-center items-center transition-all bg-[#18bcf2] hover:scale-110 active:scale-95 overflow-hidden"
             style="transition-delay: {open ? delays[4] : 0}ms"
             class:scale-100={open}
             class:scale-0={!open}>
            <img class="scale-85" src={home_assistant_icon} alt="Home Assistant Logo">
        </div>

        <!-- Gear -->
        <div class="border-white border-2 aspect-square rounded-2xl flex justify-center items-center transition-all bg-slate-700/50 hover:bg-slate-800 hover:scale-110 active:scale-95 overflow-hidden"
             style="transition-delay: {open ? delays[5] : 0}ms"
             class:scale-100={open}
             class:scale-0={!open}>
            <i class="ph-bold ph-gear"></i>
        </div>
    </div>
</div>
