<script>
    import Link from "../../../components/Link.svelte";
    import Tag from "../../../components/Tag.svelte";
    import Bullets from "../../../components/Bullets.svelte";
    import Image from "../../../components/Image.svelte";
    import ChevronRight from "../../../svgs/ChevronRight.svelte";
    import ChevronDown from "../../../svgs/ChevronDown.svelte";
    import { projects } from "../../../projects.json";
    const project = projects[0];

    let screenshotCollapsed = true;
    function toggleScreenshot() { screenshotCollapsed = !screenshotCollapsed; }
</script>

<head>
    <title>Alex | SirArchibald.dev</title>
    <script src="https://kit.fontawesome.com/d576307fab.js" crossorigin="anonymous"></script>
    <meta name="description" content="Alex is a stats and utilities Discord bot for MCC and MCC Island, built with Node.js and Discord.js. It started out as a project to view MCC event information and statistics, but I plan to grow the project to include more features in the future.">
    <meta name="keywords" content="SirArchibald, Alex, Discord, Discord bot, Discord.js, Node.js, MCC Island, MCC">
</head>

<div>
    <h1 class="dark:text-slate-50 text-4xl font-bold mb-4 text-center sm:text-left">🤖 Alex</h1>
    <div class="flex flex-col sm:flex-row">
        <div>
            {#each project.tags as tag}
                <Tag label={tag} />
            {/each}
        </div>
        <div>
            <a href="https://alex.sirarchibald.dev"><i class="fa-solid fa-globe dark:text-slate-50 text-slate-700 fa-2xl mt-8 sm:mt-3.5 ml-2 hover:text-blue-400 dark:hover:text-blue-400"></i></a>
            <a href="https://github.com/sirarchibald97/alex"><i class="fa-brands fa-github dark:text-slate-50 text-slate-700 fa-2xl mt-8 sm:mt-3.5 ml-2 hover:text-blue-400 dark:hover:text-blue-400"></i></a>
        </div>
    </div>

    <!-- ABOUT -->
    <p class="dark:text-slate-50 text-lg pt-4 sm:pl-4 text-center sm:text-left">
        Alex is a stats and utilities Discord bot for MCC and MCC Island, built with Node.js and Discord.js. It started out 
        as a project to view MCC event information and statistics, but I plan to grow the project to include more features
        in the future.
    </p>
    <p class="dark:text-slate-50 text-lg pt-4 sm:pl-4 text-center sm:text-left">
        Currently Alex features commands to grab information from the MCC Event API, including teams, scores and world 
        records. It can also show all the hidden badges available on MCC Island, as well as how to get them, and contains 
        a lookup feature for finding how and where to craft cosmetics that you may be missing.
    </p>
    <p class="dark:text-slate-50 text-lg pt-4 sm:pl-4 text-center sm:text-left">
        Alex also has a web-based dashboard where you can invite the bot to your server and customise certain settings.
        You can check out the website at <Link href="https://alex.sirarchibald.dev" text="alex.sirarchibald.dev"/>.
        <br />
        The codebase for Alex, as well as the web dashboard, is open source and available on GitHub at <Link href="https://github.com/sirarchibald97/alex" text="github.com/sirarchibald97/alex" />
        and <Link href="https://github.com/sirarchibald97/alex-web" text="github.com/sirarchibald97/alex-web" /> respectively.
    </p>

    <!-- FEATURES -->
    <p class="dark:text-slate-50 text-2xl font-semibold mt-6 mb-4 pl-4 border-l-4 border-slate-400 text-left">Features</p>
    <div class="text-slate-800 dark:text-slate-50 text-lg ml-2 sm:ml-6 text-center sm:text-left">
        <Bullets bullets={[
            "View information about the most recent MCC event, or the next one, including the teams",
            "See the scores of the previous of MCC event, including team and individual placements",
            "Browse MCC world records in the Hall of Fame (now legacy)",
            "Lookup hidden badges and cosmetics you are missing on MCC Island",
            "Set a customisable reminder for the MCC Island daily reset"
        ]} />
    </div>

    <!-- FUTURE UPDATES -->
    <p class="dark:text-slate-50 text-2xl font-semibold mt-6 pl-4 border-l-4 border-slate-400 text-left">Future Updates</p>
    <div class="text-slate-800 dark:text-slate-50 text-lg ml-2 mb-2 sm:ml-6 text-left">
        <p class="dark:text-slate-50 text-lg pt-4 text-center sm:text-left">
            The first major update I plan to add, is a feature to lookup and view information and statistics about players
            on MCC Island. This will include things such as their rank, trophies, badges, cosmetics and more, however this
            addition is subject to the release of the MCC Island API.
        </p>
        <p class="dark:text-slate-50 text-lg pt-4 text-center sm:text-left">
            The next is adding several more utilty features to the bot, including expanding the existing database of 
            cosmetics to allow players to lookup any cosmetic on the Island as well as the ability to view wiki pages
            for any item, location or cosmetic.
        </p>
        <p class="dark:text-slate-50 text-lg pt-4 text-center sm:text-left">
            Lastly, I plan to create an encompanying Fabric mod which will include, amongst other features, an in-game
            quest tracker, a player statistic viewer, Discord Rich Presence and more!
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
        <Image src="/images/alex/alex-teams.png" caption="The /teams command" />
        <Image src="/images/alex/alex-results.png" caption="The /results command" />
        <Image src="/images/alex/alex-teamresults.png" caption="The /results teams command" />
        <Image src="/images/alex/alex-playerresults.png" caption="The /results players command" />
        <Image src="/images/alex/alex-gameresults.png" caption="The /results games command" />
        <Image src="/images/alex/alex-badges.png" caption="The /badges command" />
        <Image src="/images/alex/alex-cosmetics.png" caption="The /cosmetics command" />
    </div>
</div>