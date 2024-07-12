<script>
    export let label;

    const colours = {
        "Discord": "text-indigo-800 bg-indigo-500",
        "JavaScript": "text-yellow-700 bg-yellow-300",
        "Node.js": "text-lime-700 bg-lime-300",
        "Svelte": "text-orange-900 bg-orange-400",
        "Kotlin": "text-pink-700 bg-pink-400",
        "Minecraft": "text-green-800 bg-green-400",
        "Paper": "text-orange-800 bg-orange-400",
        "Roblox": "text-red-700 bg-red-400",
        "Lua": "text-sky-700 bg-sky-400",
        "MongoDB": "text-green-800 bg-green-400",
        "MySQL": "text-purple-800 bg-purple-500",
        "SQLite": "text-rose-800 bg-rose-400",
        "Open Source": "text-slate-800 bg-slate-200 dark:bg-slate-300",
    }
</script>

<span class={`rounded-md px-2 py-1 text-sm mx-1 ${colours[label]} `}>{label}</span>