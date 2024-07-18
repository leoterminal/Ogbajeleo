<template>
    <Navbar />

    <div class="border max-w-4xl mx-auto p-4 my-8">
      <div class="text-center mb-4 bg-secondary-gray py-4">
        <h1 class="sm:text-7xl text-4xl font-bold mt-6">{{ fullName }}</h1>
        <div class="flex justify-center items-center gap-4 mt-2">
          <a href="/static/media/resume.a4a25eac3e6a4a255311.pdf" class=" w-fit px-6 py-2.5 my-2 flex gap-4 items-center border-2 hover:shadow-lg hover:scale-105 rounded-[30px] cursor-pointer" download="" target="_blank" rel="noreferrer">Resume<span class="group-hover:rotate-270 duration-300">
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="size-6">
                <path stroke-linecap="round" stroke-linejoin="round" d="M3 16.5v2.25A2.25 2.25 0 0 0 5.25 21h13.5A2.25 2.25 0 0 0 21 18.75V16.5M16.5 12 12 16.5m0 0L7.5 12m4.5 4.5V3" />
              </svg>
              
          </span></a>
        </div>
        <p class="text-2xl font-bold">{{ jobTitle }}</p>
      </div>
  
      <div class="mb-6 border-t-2 py-3">
        <h2 class="text-2xl font-semibold ">About Me</h2>
        <p class="sm:text-lg text-sm py-4">{{ about }}</p>
      </div>
  
      <div class="mb-6">
        <h2 class="text-2xl font-bold mb-2">Core Technologies</h2>
        <p>{{ coreTechnologies }}</p>
      </div>
  
      <div class="mb-6">
        <h2 class="text-2xl font-bold mb-2">Familiar With</h2>
        <p>{{ familiarWith }}</p>
      </div>
  
      <div class="mb-6">
        <h2 class="text-2xl font-bold mb-2">On The Job</h2>
        <p>{{ onTheJob }}</p>
      </div>
  
      <div class="mb-6 border-y-2 py-3">
        <h2 class="text-2xl font-bold mb-2">Experience</h2>
        <div class="py-4" v-for="experience in experiences" :key="experience.company">
          <h3 class="text-2xl font-bold">{{ experience.company }} </h3>
          <h3 class="text-lg font-semibold">{{ experience.position }} </h3>

          <p class="text-lg font-medium">{{ experience.duration }}</p>
          <ul class="list-disc list-inside px-3 ">
            <li v-for="point in experience.highlights" :key="point">{{ point }}</li>
          </ul>
        </div>
      </div>
  
      <div class="mb-6">
        <h2 class="text-2xl font-bold mb-2">Education</h2>
        <p>{{ education }}</p>
      </div>
  
      <div>
        <h2 class="text-2xl font-bold mb-2">Projects</h2>
        <router-link to="/projects" class=" py-4 cursor-pointer font-semibold my-3  underline ">See Projects ...</router-link >

      </div>
    </div>
  </template>

  <script setup lang="ts">
import { ref } from 'vue';
import Navbar from "@/components/Navbar.vue";

 const fullName = ref('Ogbaje Leo Arome');
    const jobTitle = ref('Frontend Developer');
    const about = ref(`A highly committed, consistent, and resilient individual with a drive to create exceptional user experiences through the use of HTML, CSS, Javascript, ReactJs, VueJs, and other technologies seeking a position to leverage strong technical and problem-solving skills and extensive web development knowledge to achieve organizational efficiency, reduce page load speeds, and optimize user interfaces `);
    const coreTechnologies = ref(`HTML/CSS, Tailwindcss, Javascript [ES6], ReactJs, NextJs, Vue Js, CSS-in-JS, Git, Redux, Github, Figma,  `);
    const familiarWith = ref(`Typescript, Node Js,  PWAs, SEO.`);
    const onTheJob = ref(`Version Control, Best Practices`);
    const experiences = ref([
      {
        company: 'Queryfier LLC',
        position: 'Frontend Developer',
        duration: 'Feb 2024 - Present',
        highlights: [
          'Collaborated with a team of developers to build a document validation and evaluation system with AI functionalities using Vue.js and related libraries.',
          'Designed and implemented user interface features for document validation, evaluation, and AI integration.',
          'Ensured responsiveness and optimized performance of the application for a seamless user experience',
          'Successfully delivered the project within established timelines, showcasing strong project management skills and commitment to meeting client requirements.'
        ]
      },
      {
        company: 'TIIDELab Initiative',
        position: 'Frontent Developer ',
        duration: 'June 2023 - December 2023',
        highlights: [
          'Played a pivotal role in the development and implementation of INsure, a cutting-edge insurance sales management application designed to streamline lead tracking and enhance the efficiency of insurance agents.',
          'Leveraged expertise in front-end technologies, including HTML, CSS, JavaScript, and React to create an intuitive and visually appealing user interface, contributing significantly to a positive user experience.',
          'Demonstrated a keen understanding of industry best practices, adhering to coding standards, and implementing responsive design principles to guarantee a consistent and engaging experience across various devices.',
          'Successfully delivered the project within established timelines, showcasing strong project management skills and commitment to meeting client requirements.'
        ]
      },
      
    ]);
    const education = ref(`Federal Polytechnic Idah — HND, Computer Science (2019-2022)`);

</script>




