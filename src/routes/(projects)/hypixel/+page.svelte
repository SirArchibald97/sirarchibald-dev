<script>
    import Tag from "$lib/components/Tag.svelte";
    import { projects } from "$lib/projects.json";
    const project = projects.find(p => p.name === "Hypixel Housing");
</script>

<head>
    <title>Hypixel Housings | SirArchibald.dev</title>
    <script src="https://kit.fontawesome.com/d576307fab.js" crossorigin="anonymous"></script>
    <meta name="description" content="This page is under construction!">
    <meta name="keywords" content="SirArchibald, Minecraft, Hypixel, Housing, Hypixel Housing, Parkour, Puzzles, Game Design">
</head>

<div>
    <h1 class="dark:text-slate-50 text-4xl font-bold mb-4 text-center sm:text-left">🏘️ Hypixel Housings</h1>
    <div class="flex flex-col sm:flex-row">
        <div>
            {#each project.tags as tag}
                <Tag label={tag} />
            {/each}
        </div>
    </div>

    <!-- ABOUT -->
    <br />
    <p class="dark:text-slate-50 text-lg sm:pl-4 text-center sm:text-left">
        Hypixel Housing is a gamemode on the Minecraft network Hypixel which allows players to build and publish their own Minecraft experiences. The game provides a variety of custom tools on top of the 
        standard Minecraft gameplay including ranks, NPCs, persistent stats, logic gates and lots more.
    </p>
    <p class="dark:text-slate-50 text-lg pt-4 sm:pl-4 text-center sm:text-left">
        Over the years on Hypixel, I have created a variety of Housing's, the most notable of these being several
        parkour courses and a puzzle map. In this document I will showcase some of the projects I helped produce, how they were built and the thought process behind them.
    </p>

    <!-- FEATURES -->
    <div class="flex flex-col gap-y-2 dark:text-slate-50 text-2xl font-semibold mt-6 pl-4 border-l-4 border-slate-400 text-left">
        <a href="/hypixel/adventure-parkour" class="text-blue-500 hover:underline">Adventure Parkour</a>
        <p class="text-lg font-normal">
            Adventure Parkour was a parkour Housing released in May 2023. The project started as a fairly basic parkour course but quickly grew and evolved with several advanced features and other aspects which 
            made it stand out in the community. 
        </p>
    </div>
    <div class="flex flex-col gap-y-2 dark:text-slate-50 text-2xl font-semibold mt-6 pl-4 border-l-4 border-slate-400 text-left">
        <a href="/hypixel/jumping-simulator" class="text-blue-500 hover:underline">Jumping Simulator</a>
        <p class="text-lg font-normal">
            Jumping Simulator was a solo project I built in 2023. It was based on a feature of Housing called Regions whereby players could jump on different platforms to earn currency. Currency could be used to
            purchase higher tier platforms to earn more currency and so on. The game also featured a leaderboard, custom gear and a PvP arena.
        </p>
    </div>
    <div class="flex flex-col gap-y-2 dark:text-slate-50 text-2xl font-semibold mt-6 pl-4 border-l-4 border-slate-400 text-left">
        <a href="/hypixel/find-the-button" class="text-blue-500 hover:underline">Find the Button</a>
        <p class="text-lg font-normal">
            Find the Button was a classic puzzle map where players had to advance through 30 levels by finding and clicking a button. Each level was themed around something to keep the game interesting for players
            and lots of levels had easter eggs and hidden secrets to find. 
        </p>
    </div>
    <div class="flex flex-col gap-y-2 dark:text-slate-50 text-2xl font-semibold mt-6 pl-4 border-l-4 border-slate-400 text-left">
        <a href="/hypixel/fishing" class="text-blue-500 hover:underline">Fishing</a>
        <p class="text-lg font-normal">
            This unnamed project was never finished fully but was a custom fishing system created inside of a Housing. It featured custom fish drops, items to boost your chances, a currency system to sell fish and
            buy boosts and even custom on-screen animations when fishing up rare drops.
        </p>
    </div>
</div>