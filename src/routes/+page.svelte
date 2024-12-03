<script>
    let title = "Generators";
    let description = "Welcome to the AmethystDev Generator Tools. Choose your tool below to get started with generating UUIDs or create your custom Minecraft Bedrock Manifest!";
</script>

<!-- Main Content -->
<div class="min-h-screen bg-gray-900 text-white flex flex-col justify-center items-center py-10">
  <!-- Hero Section -->
  <div class="text-center px-4">
    <h1 class="text-4xl md:text-6xl font-bold text-primary-300 mb-6">{title}</h1>
    <p class="text-lg md:text-xl font-light text-primary-200 mb-8 max-w-3xl mx-auto">
      {description}
    </p>
    
    <div class="space-x-4 flex flex-wrap justify-center">
      <!-- UUID Generator Link -->
      <a href="/uuid" class="btn btn-secondary px-8 py-3 text-lg font-semibold border-2 border-primary-400 hover:bg-primary-400 transition-transform transform hover:scale-105">
        UUID Generator
      </a>
      <!-- Manifest Generator Link -->
      <a href="/minecraft" class="btn btn-secondary px-8 py-3 text-lg font-semibold border-2 border-primary-400 hover:bg-primary-400 transition-transform transform hover:scale-105">
        Manifest Generator
      </a>
    </div>
  </div>

  <!-- Features Section -->
  <div class="mt-20 text-center px-4 max-w-3xl mx-auto">
    <h2 class="text-3xl font-bold text-primary-300 mb-6">Why Use Our Tools?</h2>
    <div class="grid grid-cols-1 md:grid-cols-2 gap-12">
      <!-- Feature 1 -->
      <div class="bg-primary-800 p-6 rounded-lg shadow-md hover:scale-105 transition-all">
        <h3 class="text-2xl font-semibold text-primary-200 mb-4">UUID Generator</h3>
        <p class="text-lg text-primary-200">
          Generate a UUID to have an identification for a project!
        </p>
      </div>

      <!-- Feature 2 -->
      <div class="bg-primary-800 p-6 rounded-lg shadow-md hover:scale-105 transition-all">
        <h3 class="text-2xl font-semibold text-primary-200 mb-4">Manifest Generator</h3>
        <p class="text-lg text-primary-200">
          Easily create a custom manifest for your Minecraft Bedrock add-ons. Customize your addon name, description, version, and more with an intuitive form.
        </p>
      </div>
    </div>
  </div>
</div>

<!-- Footer Section (Optional) -->
<div class="bg-primary-800 text-center text-primary-200 py-4 mt-20">
  <p class="text-sm">© 2024 Minecraft Generator Tools - All rights reserved.</p>
</div>
