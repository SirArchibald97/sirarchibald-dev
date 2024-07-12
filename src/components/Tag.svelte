<script>
    export let label;

    const colours = {
        "Discord": "text-indigo-900 bg-indigo-500",
        "JavaScript": "text-yellow-700 bg-yellow-300",
<<<<<<< HEAD
        "Node.js": "text-lime-700 bg-lime-300",
        "Svelte": "text-orange-900 bg-orange-400",
        "Kotlin": "text-pink-700 bg-pink-400",
        "Minecraft": "text-green-800 bg-green-400",
        "Paper": "text-orange-800 bg-orange-400",
=======
        "Node.js": "text-lime-800 bg-lime-300",
        "Svelte": "text-orange-800 bg-orange-400",
        "Kotlin": "text-pink-800 bg-pink-400",
        "Minecraft": "text-green-900 bg-green-400",
        "Paper": "text-blue-800 bg-blue-400",
>>>>>>> 2de06630135f667eba46643b1bb3dbd2c24a06e9
        "Roblox": "text-red-700 bg-red-400",
        "Lua": "text-sky-800 bg-sky-400",
        "MongoDB": "text-green-800 bg-green-400",
        "MySQL": "text-purple-900 bg-purple-500",
        "SQLite": "text-rose-800 bg-rose-400",
        "Open Source": "text-slate-800 bg-slate-200 dark:bg-slate-300",
    }
</script>

<span class={`rounded-md px-2 py-1 text-sm mx-1 ${colours[label]} `}>{label}</span>