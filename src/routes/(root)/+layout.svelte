<script>
    import "../../app.css";
    import Person from "../../svgs/Person.svelte";
    import Projects from "../../svgs/Projects.svelte";
    import Socials from "../../svgs/Socials.svelte";
    import Moon from "../../svgs/Moon.svelte";
    import Sun from "../../svgs/Sun.svelte";

    let dark = true;
    function toggleTheme() { dark = !dark; }
</script>

<div class="{dark ? "dark" : ""}">
    <div lang="" class="dark:bg-slate-900 bg-slate-50">
        <main class="flex flex-col justify-center max-w-sm text-center sm:text-left sm:max-w-5xl mx-auto">
            <nav class="flex sm:flex-row flex-col items-center text-slate-50 text-md my-8 sm:my-12 font-semibold">
                <a href="/#aboutme" class="flex flex-row items-center my-2 sm:my-0 mx-2 px-4 py-1 dark:bg-slate-600 bg-slate-300 rounded-md dark:hover:bg-slate-700 hover:bg-slate-400 dark:text-slate-50 text-slate-800">
                    <Person />
                    <span class="pl-2">About Me</span>
                </a>
                <a href="/#projects" class="flex flex-row items-center my-2 sm:my-0 mx-2 px-4 py-1 dark:bg-slate-600 bg-slate-300 rounded-md dark:hover:bg-slate-700 hover:bg-slate-400 dark:text-slate-50 text-slate-800">
                    <Projects />
                    <span class="pl-2">Projects</span>
                </a>
                <a href="/#socials" class="flex flex-row items-center my-2 sm:my-0 mx-2 px-4 py-1 dark:bg-slate-600 bg-slate-300 rounded-md dark:hover:bg-slate-700 hover:bg-slate-400 dark:text-slate-50 text-slate-800">
                    <Socials />
                    <span class="pl-2">Socials</span>
                </a>
                <button class="flex flex-row items-center my-2 sm:my-0 mx-2 px-4 py-1 dark:bg-slate-600 bg-slate-300 rounded-md dark:hover:bg-slate-700 hover:bg-slate-400 dark:text-slate-50 text-slate-800" on:click={toggleTheme}>
                    {#if dark}
                        <Moon />
                    {:else}
                        <Sun />
                    {/if}
                    <span class="pl-2">Toggle Theme</span>
                </button>
            </nav>

            <slot />
        </main>
    </div>
</div>