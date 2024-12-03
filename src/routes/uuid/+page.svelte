<script>
    let uuid = "Hey! This is where your UUID will appear.";

    function generateUUID() {
        uuid = 'xxxxxxxx-xxxx-4xxx-yxxx-xxxxxxxxxxxx'.replace(/[xy]/g, function (char) {
            const random = Math.random() * 16 | 0;
            const value = char === 'x' ? random : (random & 0x3 | 0x8);
            return value.toString(16);
        });
    }
</script>

<h1 class="text-center text-4xl md:text-6xl font-bold mb-8">UUID Generator</h1>

<div class="flex flex-col justify-start items-center mt-12 space-y-6">
  <button 
    class="btn btn-primary hover:bg-primary-focus shadow-lg transition-transform transform hover:scale-105 h-16 w-48 text-xl"
    on:click={generateUUID}
  >
    Generate UUID
  </button>
  <h2 class="text-lg font-medium text-gray-600">Click the button to generate a UUID</h2>
</div>

<div class="w-[90%] md:w-2/3 mx-auto bg-gray-900 text-primary-200 font-mono p-8 rounded-lg shadow-lg overflow-x-auto h-32 flex items-center justify-center mt-8">
  <pre><code class="whitespace-pre-wrap text-lg">{uuid}</code></pre>
</div>
