<script>
    import Person from "../svgs/Person.svelte";
    import Projects from "../svgs/Projects.svelte";
    import Socials from "../svgs/Socials.svelte";
    import Moon from "../svgs/Moon.svelte";
    import Sun from "../svgs/Sun.svelte";

    import Link from "../components/Link.svelte";
    import { tags } from "../tags.json";
    import { projects } from "../projects.json";
    import { socials } from "../socials.json";

    let dark = true;
    function toggleTheme() { dark = !dark; }

    function age() {
        const birthday = new Date(2003, 6, 23);
        const today = new Date();
        let age = today.getFullYear() - birthday.getFullYear();
        const m = today.getMonth() - birthday.getMonth();
        if (m < 0 || (m === 0 && today.getDate() < birthday.getDate())) age--;
        return age;
    }
</script>

<head>
    <title>SirArchibald.dev</title>
    <script src="https://kit.fontawesome.com/d576307fab.js" crossorigin="anonymous"></script>
</head>

<div class="{dark ? "dark" : ""}">
    <div lang="" class="dark:bg-slate-900 bg-slate-50">
        <main class="flex flex-col justify-center max-w-sm text-center sm:text-left sm:max-w-5xl sm:mx-auto">
            <!-- Navbar -->
            <nav class="flex sm:flex-row flex-col items-center text-slate-50 text-md my-8 sm:my-12 font-semibold">
                <a href="#aboutme" class="flex flex-row items-center my-2 sm:my-0 mx-2 px-4 py-1 dark:bg-slate-600 bg-slate-300 rounded-md dark:hover:bg-slate-700 hover:bg-slate-400 dark:text-slate-50 text-slate-800">
                    <Person />
                    <span class="pl-2">About Me</span>
                </a>
                <a href="#projects" class="flex flex-row items-center my-2 sm:my-0 mx-2 px-4 py-1 dark:bg-slate-600 bg-slate-300 rounded-md dark:hover:bg-slate-700 hover:bg-slate-400 dark:text-slate-50 text-slate-800">
                    <Projects />
                    <span class="pl-2">Projects</span>
                </a>
                <a href="#socials" class="flex flex-row items-center my-2 sm:my-0 mx-2 px-4 py-1 dark:bg-slate-600 bg-slate-300 rounded-md dark:hover:bg-slate-700 hover:bg-slate-400 dark:text-slate-50 text-slate-800">
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

            <!-- About Me -->
            <div id="aboutme">
                <h1 class="dark:text-slate-50 text-4xl font-bold mb-4 text-center sm:text-left">👋 Hi, I'm Archie!</h1>
                <p class="dark:text-slate-50 text-lg pt-4 pl-4 text-center sm:text-left">
                    I'm a {age()} year old developer from the UK who loves building fun things! I created this website to showcase some of my own work, teams I have been a part of, as well as 
                    other info about me!
                </p>
                <p class="dark:text-slate-50 text-lg pt-4 pl-4">
                    I have 8 years experience with programming and mostly develop for Minecraft and the web. I'm currently studying an undergraduate degree in Software Engineering, where I am 
                    in my third and final year.
                </p>
                <p class="dark:text-slate-50 text-lg pt-4 pl-4">
                    In my spare time, I enjoy playing video games, reading fantasy novels and swimming! I am also a moderator for <Link href="https://mccisland.net" text="MCC Island" />, a 
                    Minecraft server created by Noxcrew.
                </p>
            </div>

            <hr class="mt-8 mb-4" />

            <!-- Projects -->
            <div id="projects">
                <h1 class="dark:text-slate-50 text-4xl font-bold mt-4">📂 Projects I've worked on!</h1>
                <div class="flex flex-col mt-6">
                    {#each projects as project}
                        <div class="flex flex-col items-center sm:items-start sm:flex-row dark:bg-slate-800 bg-slate-300 rounded-md dark:text-slate-50 text-black my-3 p-2 mx-4 sm:mx-0">
                            <img src="/images/{project.image}" class="w-32 h-32 rounded-md" alt="{project.name} Logo" />
                            <div class="flex flex-col">
                                <div>
                                    <a href={project.link} target="_blank"><span class={`ml-4 text-xl font-semibold ${project.link ? "underline text-blue-500" : ""}`}>{project.name}</span></a>
                                    {#each project.tags as tag}
                                        <span class={`rounded-md px-2 py-1 text-sm mx-1 ${tags[tag].bg} ${tags[tag].text}`}>{tags[tag].label}</span>
                                    {/each}
                                </div>
                                <p class="ml-4 mt-2 text-sm">{project.description}</p>
                            </div>
                        </div>
                    {/each}
                </div>
            </div>

            <hr class="mt-8 mb-4" />

            <!-- Socials -->
            <div id="socials">
                <h1 class="dark:text-slate-50 text-4xl font-bold mt-4 mb-8">📷 Find me online!</h1>
                <div class="grid grid-cols-2 sm:flex sm:flex-row items-center justify-center">
                    {#each socials as social}
                    <a href={social.url}>
                        <div class={`dark:bg-slate-800 bg-slate-300 hover:bg-gradient-to-r ${`hover:${social.from}`} ${`hover:${social.to}`} hover:-translate-y-2 transition-all duration-100 rounded-lg p-8 mx-4 my-2 sm:my-0`}>
                            <i class="{social.icon} dark:text-slate-50 text-slate-700 fa-2xl">
                        </div>
                    </a>
                    {/each}
                </div>
            </div>

            <hr class="mt-10 mb-4" />

            <!-- Footer -->
            <div class="my-6">
                <p class="text-slate-500">© 2023 SirArchibald</p>
            </div>
        </main>
    </div>
</div>
