<script>
    import Link from "$lib/components/Link.svelte";
    import Tag from "$lib/components/Tag.svelte";
    import Bullets from "$lib/components/Bullets.svelte";
    import Image from "$lib/components/Image.svelte";
    import ChevronRight from "$lib/svgs/ChevronRight.svelte";
    import ChevronDown from "$lib/svgs/ChevronDown.svelte";
    import { projects } from "$lib/projects.json";
    const project = projects[2];

    let screenshotCollapsed = true;
    function toggleScreenshot() { screenshotCollapsed = !screenshotCollapsed; }
</script>

<head>
    <title>Centurion | SirArchibald.dev</title>
    <script src="https://kit.fontawesome.com/d576307fab.js" crossorigin="anonymous"></script>
    <meta name="description" content="This page is under construction!">
    <meta name="keywords" content="SirArchibald, Lighthouse, Stats, Player Stats, Discord, Discord bot, Discord.js, Node.js, MCC Island, MCC, MCCI">
</head>

<div>
    <h1 class="dark:text-slate-50 text-4xl font-bold mb-4 text-center sm:text-left">🤖 Centurion</h1>
    <div class="flex flex-col sm:flex-row">
        <div>
            {#each project.tags as tag}
                <Tag label={tag} />
            {/each}
        </div>
        <div>
            <a href="https://github.com/sirarchibald97/centurion-public"><i class="fa-brands fa-github dark:text-slate-50 text-slate-700 fa-2xl mt-8 sm:mt-3.5 ml-2 hover:text-blue-400 dark:hover:text-blue-400"></i></a>
        </div>
    </div>

    <!-- ABOUT -->
    <br />
    <p class="dark:text-slate-50 text-lg sm:pl-4 text-center sm:text-left">
        Centurion is a Discord bot bespoke designed and built for the Cent's Lounge Discord community, built with Node.js and Discord.js. The bot started as a simple moderation tool but grew into a fully
        fledged economy bot with a variety of custom features and commands. 
    </p>
    <br />
    <p class="dark:text-slate-50 text-lg sm:pl-4 text-center sm:text-left">
        The economy features a custom levelling system which rewards users for being active in the server, as well as providing randomised "item drops" which users can use to craft other items and earn
        "cents", our custom currency. Other smaller features in the economy included pets, fishing and dungeons! The bot also featured a suite of moderation tools for community moderators to use, including a 
        full punishment system that integrated into Discord's first-party moderation tools.
    </p>
    <br />
    <p class="dark:text-slate-50 text-lg pt-4 sm:pl-4 text-center sm:text-left">
        The codebase for Centurion is open source and available on GitHub at <Link href="https://github.com/sirarchibald97/centurion-public" text="github.com/sirarchibald97/centurion-public" />, 
        however both the bot and the community are no longer maintained.
    </p>

    <!-- FEATURES -->
    <p class="dark:text-slate-50 text-2xl font-semibold mt-6 mb-4 pl-4 border-l-4 border-slate-400 text-left">Features</p>
    <div class="text-slate-800 dark:text-slate-50 text-lg ml-2 sm:ml-6 text-center sm:text-left">
        <Bullets bullets={[
            "Earn XP and items from chatting in the server",
            "Use items to craft new gear and use on other members to earn coins",
            "Unlock new roles and benefits by levelling up",
            "Unlock achievements for completing certain tasks or reaching milestones",
            "Partipate in \"Happy Hours\" for increased XP"
        ]} />
    </div>

    <!-- FUTURE UPDATES -->
    <p class="dark:text-slate-50 text-2xl font-semibold mt-6 pl-4 border-l-4 border-slate-400 text-left">Future Updates</p>
    <div class="text-slate-800 dark:text-slate-50 text-lg ml-2 mb-2 sm:ml-6 text-left">
        <p class="dark:text-slate-50 text-lg pt-4 text-center sm:text-left">
            Whilst the project is no longer maintained, before it was axed there were several features I was working on, the most notable of which was a dungeon crawling minigame. This would have
            allowed members to form dungeon parties and explore randomly generated dungeons with monsters to fight and loot to collect. 
        </p>
        <p class="dark:text-slate-50 text-lg pt-4 text-center sm:text-left">
            The second feature I wanted to implement was an idle fishing system where members could periodically fish for items, coins and other loot! This idea could've been expanded even more into more idle 
            minigames such as mining, farming and more.
        </p>
    </div>

    <!-- SCREENSHOTS -->
    <div class="flex flex-row text-slate-800 dark:text-slate-50">
        <p class="dark:text-slate-50 text-2xl font-semibold mt-3 mb-4 pl-4 border-l-4 border-slate-400">Screenshots</p>
        <button on:click={toggleScreenshot} class="ml-2 text-md">
        {#if screenshotCollapsed}
            <ChevronRight />
        {:else}
            <ChevronDown />
        {/if}
        </button>
    </div>
    <div class={`${screenshotCollapsed ? "hidden" : ""}`}>
        <Image src="/images/centurion/stats.png" caption="The /rank command to view your current level and other stats" />
        <Image src="/images/centurion/levelup.png" caption="Example of a user levelling up in the server by chatting" />
        <Image src="/images/centurion/items.png" caption="Example of a user earning a random item by chatting" />
        <Image src="/images/centurion/inventory.png" caption="The /inventory command where members can see their collected items" />
        <Image src="/images/centurion/pets.png" caption="Example of a member earning a rare pet by reaching level 100" />
        <Image src="/images/centurion/exampleitem.png" caption="Example of a member using an item on another member and stealing some coins" />
        <Image src="/images/centurion/achievements.png" caption="The /achievements command where members can see which they have unlocked and which they haven't" />
    </div>
</div>