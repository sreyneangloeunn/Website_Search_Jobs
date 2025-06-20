<template>
  <div class="flex flex-col min-h-screen">
    <!-- Content wrapper -->
    <div class="about px-6 py-12 max-w-6xl mx-auto space-y-16 flex-grow">
      <!-- Intro Section -->
      <section class="text-center">
        <h1 class="text-5xl font-bold text-blue-700 mb-4">Welcome to JobSearch</h1>
        <p class="text-lg text-gray-700 max-w-3xl mx-auto">
          JobSearch is your trusted platform to explore IT career paths, get trained by top experts, and find job opportunities that match your skills.
        </p>
        <img
          src="https://media.geeksforgeeks.org/wp-content/uploads/20240311151721/it-career-path-copy.webp"
          alt="IT Careers"
          class="mx-auto mt-6 rounded-xl shadow-lg w-full h-[400px] object-cover"
        />
      </section>

      <!-- Mission & Vision -->
      <section class="grid grid-cols-1 md:grid-cols-2 gap-10">
        <div class="bg-white rounded-xl shadow p-6">
          <h2 class="text-2xl font-semibold text-blue-600 mb-2">Our Mission</h2>
          <p class="text-gray-700">
            To provide accessible, high-quality IT education and connect learners with real-world job opportunities across the globe.
          </p>
        </div>
        <div class="bg-white rounded-xl shadow p-6">
          <h2 class="text-2xl font-semibold text-blue-600 mb-2">Our Vision</h2>
          <p class="text-gray-700">
            Empower individuals to succeed in tech careers and contribute to digital transformation by building future-ready skills.
          </p>
        </div>
      </section>

      <!-- Cards Section -->
      <section>
        <h2 class="text-3xl font-semibold text-blue-700 mb-6 text-center">Why Choose JobSearch?</h2>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
          <Card
            title="Trusted by Learners"
            content="Over 10,000 students trust our platform to grow their IT skills."
            image="https://teacherhow.com/wp-content/uploads/2022/10/Students_Trust_You_-1024x680.jpg"
          />
          <Card
            title="Job-Focused Curriculum"
            content="We build our training around real-world job requirements."
            image="https://www.webstackacademy.com/wp-content/uploads/2024/05/003_fullstack_developer_career_path-4-1-1024x444.jpg"
          />
          <Card
            title="Expert Instructors"
            content="Learn from industry professionals with hands-on experience."
            image="https://site.corsizio.com/uploads/5c48a23d8a53fd6af0f9d73d/events/5ede3b0518eb201f9623707f/photo-biY_Us3gr.png"
          />
        </div>
      </section>
    </div>

    <!-- Full-width Footer -->
    <Footer class="w-full"/>
  </div>
</template>

<script setup>
import Card from '@/components/Card.vue'
import Footer from '@/components/global/layout/Footer.vue'
</script>

<style scoped>
.about img {
  transition: transform 0.3s ease;
}
.about img:hover {
  transform: scale(1.02);
}
</style>
