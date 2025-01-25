<template>
  <div class="relative flex items-center justify-center h-screen animated-gradient">
    <div class="text-center text-white p-6 bg-black bg-opacity-40 rounded-lg shadow-lg">
      <h1 class="text-6xl font-bold mb-4 animate-pulse">Welcome to My DDEV Vue Setup</h1>
      <p class="text-xl mb-8">Kickstart your Vue development with ease and flexibility</p>
      <a
        href="https://robingropp.de"
        rel="noopener noreferrer"
        target="_blank"
        class="px-6 py-3 bg-blue-600 text-white rounded-full hover:bg-blue-700 transition transform hover:scale-105"
      >
        Learn More
      </a>
    </div>
  </div>
</template>

<style>
.animated-gradient {
  background: linear-gradient(120deg, #1e3a8a, #3b82f6, #8b5cf6, #ec4899, #f43f5e);
  background-size: 300% 300%;
  animation: gradient-animation 15s ease infinite;
}

@keyframes gradient-animation {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}
</style>
