<script>
    import Link from "$lib/components/Link.svelte";
    import Tag from "$lib/components/Tag.svelte";
    import Bullets from "$lib/components/Bullets.svelte";
    import Image from "$lib/components/Image.svelte";
    import GoBackArrow from "$lib/svgs/GoBackArrow.svelte";
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
    <h1 class="dark:text-slate-50 text-4xl font-bold mb-4 text-center sm:text-left">🏘️ Adventure Parkour</h1>
    <div class="flex flex-col sm:flex-row">
        <a href="/hypixel" class="flex flex-row gap-x-2 mr-2 items-center text-sm px-4 py-1 dark:bg-slate-600 bg-slate-300 rounded-md dark:hover:bg-slate-700 hover:bg-slate-400 dark:text-slate-50 text-slate-800">
            <span class="w-4 h-4 self-center"><GoBackArrow /></span>
            <span>Back</span>
        </a>
        {#each project.tags as tag}
            <Tag label={tag} />
        {/each}
    </div>

    <!-- ABOUT -->
    <br />
    <p class="dark:text-slate-50 text-lg pt-4 sm:pl-4 text-center sm:text-left">
        Adventure Parkour was a parkour Housing released in May 2023. The project started as a fairly basic parkour course but quickly grew and evolved with several advanced features and other aspects which 
        made it stand out in the community. 
    </p>
    <p class="dark:text-slate-50 text-lg pt-4 sm:pl-4 text-center sm:text-left">
        The basic premise of the course was 175 indivual parkour levels split over 5 floors, with each floor steadily increasing in difficulty. Each floor had its own theme to create a sense of progression and 
        add a fun aspect of adventuring to the housing to keep players engaged. Floors 1-4 were specifically made to be quite simple and completable by the average player in order to increase player retention.
    </p>

    <!-- THE GAME -->
    <p class="dark:text-slate-50 text-2xl font-semibold mt-6 pl-4 border-l-4 border-slate-400 text-left">Game Features</p>
    <p class="dark:text-slate-50 text-lg pt-4 sm:pl-4 text-center sm:text-left">
        Outside of the basic parkour courses, the housing featured a handful of supporting features to make the parkour better and more engaging for players.
    </p>

    <div class="flex flex-col gap-y-4 mt-4">
        <!-- SKIP -->
        <div>
            <p class="dark:text-slate-50 text-xl font-semibold pt-4 sm:pl-4 text-center sm:text-left">Skips</p>
            <p class="dark:text-slate-50 text-lg sm:pl-4 text-center sm:text-left">
                In earlier housings, the creators would have to teleport players across levels or open staff-only doors in order for players to skip levels they were stuck on. In order to fix this, we added custom items
                called <strong>skips</strong>. These when used would grant the player a few seconds of a jump boost effect to allow them to jump over a level and skip it. A chat message and sound effect are sent to the player
                to show that a skip was used.
            </p>
            <p class="dark:text-slate-50 text-lg mt-2 sm:pl-4 text-center sm:text-left">
                Each player was given two skips, one iron block and one gold block to ensure they do not stack into a single inventory slot. Players could gain more skips by restarting the parkour.
            </p>
            <div class="w-2/3">
                <Image src="/images/adventure_parkour/parkour_skips.png" caption="The skip items given out in Adventure Parkour" />
            </div>
        </div>

        <!-- SCOREBOARD -->
        <div>
            <p class="dark:text-slate-50 text-xl font-semibold pt-4 sm:pl-4 text-center sm:text-left">Customised Scoreboard</p>
            <p class="dark:text-slate-50 text-lg sm:pl-4 text-center sm:text-left">
                The Housing scoreboard shows a few useful bits of information including the current date and time and the server you are in. The Housing scoreboard is also customisable, so we added serveral other global
                statistics such as the number of current guests, the number of total cookies, the number of players that have joined and the number of fails. The scoreboard also shows other information about the parkour 
                such as the number of floors, the number of levels and your current parkour time.
            </p>
            <div class="w-2/3">
                <Image src="/images/adventure_parkour/custom_scoreboard.png" caption="The custom scoreboard created in Adventure Parkour" />
            </div>
        </div>

        <!-- HOUSING RANKS -->
        <div>
            <p class="dark:text-slate-50 text-xl font-semibold pt-4 sm:pl-4 text-center sm:text-left">Housing Ranks</p>
            <p class="dark:text-slate-50 text-lg sm:pl-4 text-center sm:text-left">
                Housing features a system of ranks which players can be given. We utilised ranks in Adventure Parkour to show off achievements earned by players and also to grant certain perks as rewards for completing 
                the parkour and the challenges.
            </p>
            <p class="dark:text-slate-50 text-lg mt-2 sm:pl-4 text-center sm:text-left">
                The ranks that were obtainable to players were:
            </p>
            <div class="text-slate-800 dark:text-slate-50 text-lg ml-2 sm:ml-6 text-center sm:text-left">
                <Bullets bullets={[
                    "Floor 1 - All players start with this rank",
                    "Floor 2 - Awarded for reaching Floor 2 of the parkour",
                    "Floor 3 - Awarded for reaching Floor 3 of the parkour",
                    "Floor 4 - Awarded for reaching Floor 4 of the parkour",
                    "Floor 5 - Awarded for reaching Floor 5 of the parkour",
                    "Master - Awarded for fully completing the parkour",
                    "Legend - Awarded for completing the parkour on Challenge Mode",
                    "Eternal - Awarded for completing the parkour on Ultimate Mode"
                ]} />
            </div>
            <p class="dark:text-slate-50 text-lg mt-2 sm:pl-4 text-center sm:text-left">
                Only the final three ranks awarded any perks:
            </p>
            <div class="text-slate-800 dark:text-slate-50 text-lg ml-2 sm:ml-6 text-center sm:text-left">
                <Bullets bullets={[
                    "Master - Use of /fly, /tp and /end to easily explore the Housing & a custom trophy item",
                    "Legend - Able to start the Ultimate Mode challenge & a custom trophy item",
                    "Eternal - The highest rank in the Housing (bragging rights)"
                ]} />
            </div>
        </div>

        <!-- CHALLENGES -->
        <div>
            <p class="dark:text-slate-50 text-xl font-semibold pt-4 sm:pl-4 text-center sm:text-left">Challenges</p>
            <p class="dark:text-slate-50 text-lg sm:pl-4 text-center sm:text-left">
                In order to retain players for longer and keep them engaged with our parkour, we added a custom challenge system. These challenges required beating the parkour with certain debuffs which made it
                far harder. We had two different challenges for players to do, however more could easily be added into the system.
            </p>
            <p class="dark:text-slate-50 text-lg mt-2 sm:pl-4 text-center sm:text-left">
                The first of the two challenges we added was <strong>Challenge Mode</strong>. This required players to complete the entire parkour course with the Nausea effect which causes visual disorientation. This was created
                to offer the more dedicated and skilled players a way to test their skills. Once completed, the players is teleported to a special area only accessible after completing Challenge Mode where they are
                rewarded with the Legend rank. 
            </p>
            <div class="flex flex-col md:flex-row gap-x-4">
                <Image src="/images/adventure_parkour/challenge_mode.png" caption="The NPC used to begin Challenge Mode" />
                <Image src="/images/adventure_parkour/legend_area.png" caption="The special area where players can claim Legend rank" />
            </div>

            <p class="dark:text-slate-50 text-lg mt-2 sm:pl-4 text-center sm:text-left">
                Once Challenge Mode is complete, players are able to attempt <strong>Ultimate Mode</strong>. This was designed to be an especially hard task for only the most skilled players, and required them to complete the entire course with the
                Slowness 2 effect. This reduces a players speed by 30% and makes certain jumps far more difficult. This challenge was designed to take a long time and a lot of effort to complete to appeal to the completionists
                and increase players retention even more. 
            </p>
            <p class="dark:text-slate-50 text-lg mt-2 sm:pl-4 text-center sm:text-left">
                Upon completing the course, players in Ultimate Mode are teleported to a special floor named Floor 0 which has 5 super hard parkour levels. Once these are completed
                they finally earn the Eternal rank. Extensive testing had to be completed for this challenge to ensure that every parkour level was even possible with Slowness 2, and certain levels did end up
                being changed to accomodate this feature.
            </p>
            <div class="flex flex-col md:flex-row gap-x-4">
                <Image src="/images/adventure_parkour/ultimate_mode.png" caption="The NPC used to begin Ultimate Mode" />
                <Image src="/images/adventure_parkour/floor_0.png" caption="The hidden Floor 0 required to earn Eternal rank" />
            </div>

            <p class="dark:text-slate-50 text-lg mt-2 sm:pl-4 text-center sm:text-left">
                Upon completing either of the challenges, a public announcement is made to the entire Housing congratulating the player. This also served as an incentive to convince other players to attempt the
                challenges and keep playing our Housing. A quit button was also added which allowed players to restart the parkour and have the debuffs removed if they no longer wanted to play one of our challenges.
            </p>
            <div class="flex flex-col md:flex-row gap-x-4">
                <Image src="/images/adventure_parkour/eternal_rank.png" caption="The NPC used to begin Ultimate Mode" />
                <Image src="/images/adventure_parkour/quit_challenge.png" caption="The hidden Floor 0 required to earn Eternal rank" />
            </div>
        </div>

        <!-- ANTICHEAT -->
        <div>
            <p class="dark:text-slate-50 text-xl font-semibold pt-4 sm:pl-4 text-center sm:text-left">Anticheat</p>
            <p class="dark:text-slate-50 text-lg sm:pl-4 text-center sm:text-left">
                One of the largest problems in video games today is cheating and exploiting. Practically every game will have some form of cheating take place during its lifetime and because of this it is very important
                that developers and designers take possible exploiting into account when building games. In order to counteract cheating in this Housing, we were able to use a couple of tools to help us.
            </p>
            <p class="dark:text-slate-50 text-lg mt-2 sm:pl-4 text-center sm:text-left">
                Limitations of the platform we were using meant that the system we designed would never be 100% foolproof, however it used several checks to try and ensure that players completing the parkour illigitimately 
                were prevented from doing so. The checks we used included:
            </p>
            <div class="text-slate-800 dark:text-slate-50 text-lg ml-2 sm:ml-6 text-center sm:text-left">
                <Bullets bullets={[
                    "Has the player started the parkour?",
                    "Does the player have the correct rank?",
                    "Is their parkour timer under X seconds?"
                ]} />
            </div>
            <p class="dark:text-slate-50 text-lg mt-2 sm:pl-4 text-center sm:text-left">
                These checks together ensured that any player completing the parkour had triggered the start timer, had the rank of the final floor, meaning they had definitely passed through each floor, and that their timer
                was slower than the minimum time required to complete the parkour. This system was not perfect, but it was a good start to preventing cheating in our Housing.
            </p>
        </div>
    </div>

    <!-- RETENTION STRATEGIES -->
    <p class="dark:text-slate-50 text-2xl font-semibold mt-6 pl-4 border-l-4 border-slate-400 text-left">Retention Strategies</p>
    <p class="dark:text-slate-50 text-lg pt-4 sm:pl-4 text-center sm:text-left">
        When designing any game, you want to retain a player's attention for as long as possible so they will keep playing and enjoying your game. In Adventure Parkour, we employed several strategies to 
        increase the retention of our players. 
    </p>
    <div class="flex flex-col gap-y-4">
        <div>
            <p class="dark:text-slate-50 text-xl font-semibold pt-4 sm:pl-4 text-center sm:text-left">Difficulty</p>
            <p class="dark:text-slate-50 text-lg sm:pl-4 text-center sm:text-left">
                The difficulty of the parkour was a key factor in retaining players. The parkour was designed to be easy to complete for as many players as possible. This was done by making the first 4 floors of the parkour
                quite simple and easy to complete. This was to ensure that players would not get stuck and quit the parkour early on, a strategy similar to the "near miss effect" in gambling. The final floor was designed to 
                be much harder and require a lot more skill to complete to appeal to the more competitive players. 
            </p>
        </div>
        <div>
            <p class="dark:text-slate-50 text-xl font-semibold pt-4 sm:pl-4 text-center sm:text-left">Challenges</p>
            <p class="dark:text-slate-50 text-lg sm:pl-4 text-center sm:text-left">
                The challenges were designed to be a long term goal for players to work towards. Because they were far more difficult to complete, they appealed a lot more to the competitive players, making up for the relative
                ease of the parkour itself. They also provided the added benefit of keeping players in the Housing longer which boosted our guest count and increased our reach.
            </p>
        </div>
        <div>
            <p class="dark:text-slate-50 text-xl font-semibold pt-4 sm:pl-4 text-center sm:text-left">Vanity & Status</p>
            <p class="dark:text-slate-50 text-lg sm:pl-4 text-center sm:text-left">
                The Housing ranks were added as a way for players to show off their achievements to other players. The more you have completed in the Housing, the higher the rank and the more "bragging rights" you have. A few
                of our ranks offer special perks however the majority of them are cosmetic only and serve as a way for players to feel special and exclusive. This is a very exploitable trait in players and can be used as we
                have to greatly increase retention by appealing to player's want for special or rare things. 
            </p>
        </div>
        <div>
            <p class="dark:text-slate-50 text-xl font-semibold pt-4 sm:pl-4 text-center sm:text-left">"Third Party" Content</p>
            <p class="dark:text-slate-50 text-lg sm:pl-4 text-center sm:text-left">
                On top of the parkour course, the challenges and the surrounding features, we also created a huge amount of "third party" content in the Housing. This refers to builds and items which are not directly related
                to the parkour but are explorable by players who have completed it. This content was designed to be an extra fun activity after the main attraction and to keep players in our Housing. More specifically, we made
                use of a scavenger hunt system to encourage players to interact in the community and stay in the housing to "complete" it, once again taking advantage of the psychology of players.
            </p>
        </div>
    </div>

    <!-- PERFORMANCE -->
    <p class="dark:text-slate-50 text-2xl font-semibold mt-6 pl-4 border-l-4 border-slate-400 text-left">Statistics & Performance</p>
    <p class="dark:text-slate-50 text-lg pt-4 sm:pl-4 text-center sm:text-left">
        We created a system of statistics to help us track the performance of our Housing and measure its success. As of December 2023, the Housing has had:
    </p>
    <div class="dark:text-slate-50 text-lg pt-4 sm:pl-4 text-center sm:text-left">
        <Bullets bullets={[
            "42,000+ unique players",
            "9,700+ parkour completions",
            "39,000+ skips used",
            "6,500,000+ fails",
            "47 cheaters caught",
            "1,300+ players with Legend rank",
            "400+ players with Eternal rank"
        ]} />
    </div>
    <p class="dark:text-slate-50 text-lg pt-4 sm:pl-4 text-center sm:text-left">
        On top of this, we also created a rating system to allow players to select a rating of our Housing out of "Good", "OK" and "Bad". The results of this are:
    </p>
    <div class="dark:text-slate-50 text-lg pt-4 sm:pl-4 text-center sm:text-left">
        <Bullets bullets={[
            "Good: 7,000+",
            "OK: 1,600+",
            "Bad: 300+"
        ]} />
    </div>
    <p class="dark:text-slate-50 text-lg pt-4 sm:pl-4 text-center sm:text-left">
        Whilst some qualitative data to combine with this would provide a much more 
    </p>
</div>