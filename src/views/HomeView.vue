<script setup>
import Card from '@/components/Card.vue'
import Button from '@/components/global/Button.vue'
import Footer from '@/components/global/layout/Footer.vue'
// import Navbar from '@/components/global/layout/navbar.vue'
// import navbar from '@/components/global/layout/navbar.vue'


const jobs = [
  {
    title: 'Frontend Developer',
    description: 'Build responsive websites with HTML, CSS, and Vue.',
    image: 'https://www.orientsoftware.com/Themes/Content/Images/blog/2024-08-12/senior-front-end-dev.webp'
  },
  {
    title: 'Backend Developer',
    description: 'Design robust APIs using Node.js, Python, and databases.',
    image: 'https://miro.medium.com/v2/resize:fit:1200/1*G48L33n3M7FXze_kturcyQ.jpeg'
  },
  {
    title: 'Full Stack Developer',
    description: 'Combine frontend and backend skills to build full apps.',
    image: 'https://miro.medium.com/v2/resize:fit:800/0*XH3rLskyOsCqVV-j.jpg'
  },
  {
    title: 'DevOps Engineer',
    description: 'Automate deployment and manage cloud infrastructure.',
    image: 'https://www.flexjobs.com/blog/wp-content/uploads/2020/05/07184138/DevOps.png'
  },
  {
    title: 'UI/UX Designer',
    description: 'Design modern, user-friendly interfaces. It easy for user to find the info.',
    image: 'https://fronty.com/static/uploads/design_vs.jpg'
  },
  {
    title: 'QA Engineer',
    description: 'Test and improve software reliability and performance.',
    image: 'https://cdn.prod.website-files.com/644748ed8ed80c2808bedb45/668fc455800c13b6c996b53a_21.jpg'
  }
]
</script>

<template>
   
  <main class="max-w-7xl mx-auto px-4 py-10">
    <!-- Welcome Section -->
    <div class="text-center mb-12">
      <h1 class="text-4xl font-bold text-blue-700">Welcome to the Home Page</h1>
      <p class="mt-4 text-gray-600 text-lg">Explore exciting opportunities in the IT industry!</p>
    </div>

    <!-- Job Cards -->
    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
      <Card
        v-for="(job, index) in jobs"
        :key="index"
        :title="job.title"
        :content="job.description"
        :image="job.image"
      >
        <template #footer>
          <Button
            @click="() => alert(`Starting: ${job.title}`)"
          >
            Start Now
          </Button>
        </template>
      </Card>
    </div>
  </main>

  <!-- Footer -->
  <Footer class="w-full"/>
</template>