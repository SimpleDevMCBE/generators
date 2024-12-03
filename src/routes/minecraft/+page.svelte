<script>
    let uuid = "a866207a-06f0-4463-8d8c-acde4ae50242";  // Default UUID for the header
    let version = "1.0.0";  // Default version
    let description = "Your custom description here.";
    let name = "My Addon";
    let serveruiVersion = "1.4.0-beta"; // Module version
    let serverVersion = "1.16.0-beta"
    let author = "ManifestCreator"
    let manifest = "";

    // Helper function to generate a UUID (for the sake of the example)
    function generateUUID() {
        uuid = 'xxxxxxxx-xxxx-4xxx-yxxx-xxxxxxxxxxxx'.replace(/[xy]/g, function (char) {
            const random = Math.random() * 16 | 0;
            const value = char === 'x' ? random : (random & 0x3 | 0x8);
            return value.toString(16);
        });
    }

    // Function to generate the manifest file in the desired format
    function generateManifest() {
        manifest = JSON.stringify({
            format_version: 2,
            metadata: {
                authors: [author]
            },
            header: {
                name: name,
                description: description,
                min_engine_version: [1, 20, 60],
                uuid: uuid,
                version: parseVersion(version)
            },
            modules: [
                {
                    type: "data",
                    uuid: generateUUID(),
                    version: [
                        1,
                        0,
                        0
                    ]
                },
                {
                    type: "script",
                    language: "javascript",
                    uuid: generateUUID(),
                    entry: "scripts/main.js",
                    version: [
                        1,
                        0,
                        0
                    ]
                }
            ],
            dependencies: [
                {
                    module_name: "@minecraft/server",
                    version: serverVersion
                },
                {
                    module_name: "@minecraft/server-ui",
                    version: serveruiVersion
                }
            ]
        }, null, 2);
    }

    // Parse version from string
    function parseVersion(versionStr) {
        return versionStr.split('.').map(Number);
    }
</script>

<h1 class="text-center text-4xl md:text-6xl font-bold mb-8">Minecraft Bedrock Manifest Generator</h1>

<div class="flex flex-col justify-start items-center mt-12 space-y-6 w-full max-w-xl mx-auto">
    <!-- UUID Input -->
    <div class="flex flex-col w-full">
        <label for="uuid" class="text-lg text-gray-700">UUID</label>
        <input id="uuid" type="text" class="input input-bordered w-full py-2 px-4 rounded-lg text-blue-800" bind:value={uuid} />
        <button on:click={generateUUID} class="mt-2 btn btn-primary hover:bg-primary-focus shadow-lg transition-transform transform hover:scale-105 w-full">Generate New UUID</button>
    </div>

    <!-- Name Input -->
    <div class="flex flex-col w-full">
        <label for="name" class="text-lg text-gray-700">Addon Name</label>
        <input id="name" type="text" class="input input-bordered w-full py-2 px-4 rounded-lg text-blue-800" bind:value={name} />
    </div>

    <!-- Version Input -->
    <div class="flex flex-col w-full">
        <label for="version" class="text-lg text-gray-700">Version</label>
        <input id="version" type="text" class="input input-bordered w-full py-2 px-4 rounded-lg text-blue-800" bind:value={version} />
    </div>

    <!-- Description Input -->
    <div class="flex flex-col w-full">
        <label for="description" class="text-lg text-gray-700">Description</label>
        <textarea id="description" class="textarea textarea-bordered w-full py-2 px-4 rounded-lg text-blue-800" bind:value={description} rows="4"></textarea>
    </div>

    <!-- Module Version Input -->
    <div class="flex flex-col w-full">
        <label for="moduleVersion" class="text-lg text-gray-700">@minecraft/server-ui Version</label>
        <input id="moduleVersion" type="text" class="input input-bordered w-full py-2 px-4 rounded-lg text-blue-800" bind:value={serveruiVersion} />
    </div>
    <div class="flex flex-col w-full">
        <label for="moduleVersion" class="text-lg text-gray-700">@minecraft/server Version</label>
        <input id="moduleVersion" type="text" class="input input-bordered w-full py-2 px-4 rounded-lg text-blue-800" bind:value={serverVersion} />
    </div>

    <div class="flex flex-col w-full">
        <label for="moduleVersion" class="text-lg text-gray-700">Author</label>
        <input id="moduleVersion" type="text" class="input input-bordered w-full py-2 px-4 rounded-lg text-blue-800" bind:value={author} />
    </div>

    <!-- Generate Manifest Button -->
    <button on:click={generateManifest} class="btn btn-primary hover:bg-primary-focus shadow-lg transition-transform transform hover:scale-105 w-full mt-4">
        Generate Manifest
    </button>

    <!-- Generated Manifest Output -->
    {#if manifest}
    <div class="w-full bg-gray-900 text-primary-200 font-mono p-6 rounded-lg shadow-lg overflow-x-auto mt-6">
        <pre><code class="whitespace-pre-wrap text-lg">{manifest}</code></pre>
    </div>
    {/if}
</div>
