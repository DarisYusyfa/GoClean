<template>
  <div class="min-h-screen bg-gray-100 dark:bg-gray-900 flex flex-col plus-jakarta-sans transition-colors duration-300 relative z-0">
    <Navbar />
    <main class="flex-grow text-gray-900 dark:text-gray-100">
      <slot />
    </main>
    <Footer />
    <DarkModeToggle />
  </div>
</template>
