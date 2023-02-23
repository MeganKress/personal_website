<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import HelloWorld from './components/HelloWorld.vue'
import Card from './components/Card.vue'
import GreenCard from './components/GreenCard.vue'
import BlueCard from './components/BlueCard.vue'
import PurpleCard from './components/PurpleCard.vue'
import { computed } from '@vue/runtime-core'

const props = defineProps({
  searchTermString: String,
})

let screenWidth = computed(() => {
  return screen.width
})

</script>

<template>
<div class="bg-slate-700 pb-4">
  <div class="z-50 w-full bg-slate-600 grid md:grid-cols-8 grid-cols-1 p-4 sticky top-0">
    <span class="grid text-xl uppercase md:col-span-4 col-span-1 text-yellow-200">Megan Kress</span>
    <a href="#about"><span class="text-white uppercase text-center col-span-1 hover:font-bold hover:text-yellow-200 hover:cursor-pointer">About</span></a>
    <a href="#projects"><span class="text-white uppercase text-center col-span-1 hover:font-bold hover:text-yellow-200 hover:cursor-pointer">Projects</span></a>
    <a href="#resources"><span class="text-white uppercase text-center col-span-1  hover:font-bold hover:text-yellow-200 hover:cursor-pointer">Coding Resources</span></a>
    <a href="#contact"><span class="text-white uppercase text-center col-span-1 hover:font-bold hover:text-yellow-200 hover:cursor-pointer">Contact</span></a>
  </div>

  <div class="w-full bg-slate-500 grid grid-cols-8 p-4 mt-10" id="about">
     <span class="grid text-xl col-span-4 text-yellow-200">About Me</span>
  </div>
  <div class="grid grid-cols-1">
    <Card name="Education" description="As a researcher in the Michigan State University Forestry department, I looked at the intersections of various STEM fields. I worked on creating data processing and classification programs in R and C++." 
      :points="['Processing, visualizing, and analyzing terabytes of airborne LiDAR data in R and Python', 'Modeling spatial data in R', 'Creating web-based, interactive maps and data visualizations in R (Shiny) and Python (Jupyter notebooks)', 'Processing three-dimensional point clouds using parallel programming in C++']"/>
    <Card name="Career" description="As a software developer, I create VueJS components on the front end of a vehicle simulator and data product." 
      :points="['Building web application data displays using JavaScript charting and grid libraries', 'Creating and updating Laravel models, views, and controllers', 'Maintaining and debugging the Java-based back end for a vehicle fuel economy simulator', 'Communicating with subject matter experts (automotive engineers) to incorporate calculations and table updates to a rules engine', 'Managing SQL and NoSQL databases', 'Deploying server updates to AWS']" />

  </div>

  <div class="w-full bg-slate-500 grid grid-cols-8 p-4 mt-10" id="projects">
     <span class="grid text-xl col-span-4 text-green-200">Projects</span>
  </div>
  <div class="grid sm:grid-cols-2 grid-cols-1">
    <GreenCard name="COLE Interface" 
      project_requirements="This is a project for Dr. Andy Finley’s research lab. The goal is to create a tool to be used by people in the forestry field to access Forest Inventory & Analysis (FIA) data." 
      approach="I created an interactive map and forms for users to select their desired span of information. I used an existing library to interact with the FIA API." 
      code="https://github.com/MeganKress/cole_interface" 
      technology_stack="R and R Shiny (HTML and JavaScript)" 
      date="December 2021 - present" 
      url="http://147.182.132.240:3838/cole_interface/" />
    <GreenCard name="Personal Website" 
      project_requirements="My goal was to create a portfolio site with an interactive VueJS element. I also wanted to provide coding resources to the community." 
      approach="I used Tailwind for formatting and Vue for different card components. I also used Vue for an interactive search feature under the Resources section." 
      code="https://github.com/MeganKress/personal_website" 
      technology_stack="HTML, VueJS, Tailwind" 
      date="October 2022 - present" 
      url="http://megankress.com" />
    <GreenCard name="LiDAR Voxel Generator (LiVoxGen)" 
      project_requirements="LiVoxGen is a C++ program that “voxelizes” LiDAR data by partitioning a LAS file into columns of volumetric pixels and counting the LiDAR points inside each voxel. This was a graduate school research project." 
      approach="I used the libLAS library for reading in the three-dimensional points. I then used a feature of the library to draw a sphere around the voxel in order to increase efficiency in counting the actual number of points within the voxel. I used a kd-tree library for faster 3-dimensional searching." 
      code="https://github.com/MeganKress/LiVoxGen" 
      technology_stack="C++" 
      date="2015" 
      url="http://megankress.github.io/LiVoxGen/" />
  </div>

  <div class="w-full bg-slate-500 grid grid-cols-8 p-4 mt-10" id="resources">
     <span class="grid text-xl col-span-4 text-blue-200">Coding Resources</span>
  </div>

  <input type="text" placeholder="Filter by search term..." v-model="props.searchTermString" class="m-5 rounded-lg p-2"  />

  <div class="w-full grid grid-cols-8 p-4 mt-2">
     <span class="grid text-xl col-span-4 text-blue-200">Organizations</span>
  </div>
  <div class="grid sm:grid-cols-4 grid-cols-2">
    <BlueCard name="Code.org" description="A nonprofit dedicated to providing access to computer science in K-12 schools. It is the organizer of the annual Hour of Code campaign."
      url="https://code.org/" :searchTerm="props.searchTermString"/>
    <BlueCard name="CSEdWeek" description='"Computer Science Education Week is an annual call to action to inspire K-12 students to learn computer science, advocate for equity, and celebrate the contributions of students, teachers, and partners to the field."'
      url="https://www.csedweek.org/" :searchTerm="props.searchTermString"/>
    <BlueCard name="Computer Science Teachers Association" description="(CSTA) A teacher-led community that provides resources for K-12 educators."
      url="https://www.csteachers.org/" :searchTerm="props.searchTermString"/>
    <BlueCard name="The National Center for Women & Information Technology" description="(NCWIT) An organization of change leaders aiming to increase participation of girls and women in computing in an intersectional way."
      url="https://www.csteachers.org/" :searchTerm="props.searchTermString"/>
  </div>

  <div class="w-full grid grid-cols-8 p-4 mt-10">
     <span class="grid text-xl col-span-4 text-blue-200">Toys/Games</span>
  </div>
  <div class="grid sm:grid-cols-4 grid-cols-2">
    <BlueCard name="Coding Games for Beginners^^" description="A compilation of web-based games from HP Tech Takes"
      url="https://www.hp.com/us-en/shop/tech-takes/coding-games-for-beginners" :searchTerm="props.searchTermString" />
    <BlueCard name="STEM Toys and Games^^" description="A collection of STEM activities from FUN.com"
      url="https://www.fun.com/stem-toys-and-games.html" :searchTerm="props.searchTermString" />
    <BlueCard name="Arduino" description="Open source boards and software used for interactive projects. The website includes documentation, forums, and teacher guides and resources."
      url="https://www.arduino.cc/" :searchTerm="props.searchTermString" />
    <BlueCard name="Dash & Dot" description="Robots and apps to teach kids math and coding. Site includes learn to code curriculums and STEM funding guides."
      url="https://www.makewonder.com/" :searchTerm="props.searchTermString" />
    <BlueCard name="LEGO Mindstorms/LEGO Education SPIKE" description="Learning systems for the classroom to encourage creativity, collaboration, and critical thinking. Resources include lesson/unit plans and professional development information."
      url="https://education.lego.com/en-us/" :searchTerm="props.searchTermString" />
    <BlueCard name="Minecraft Education Edition" description="Lesson plans for the popular video game Minecraft that span STEM, Coding, SEL, History, Language Arts, and 21st Century Skills."
      url="https://education.minecraft.net/en-us" :searchTerm="props.searchTermString" />
    <BlueCard name="Digital Dream Labs" description="Consumer robots and educational video games for learning how to code."
      url="https://www.digitaldreamlabs.com/" :searchTerm="props.searchTermString" />
    <BlueCard name="Raspberry Pi" description="A UK-based nonprofit that produces low-cost single-board computers and software to advance the field of computing education."
      url="https://www.raspberrypi.org/" :searchTerm="props.searchTermString" />
    <BlueCard name="Robot Turtles" description="A board game for younger children (ages 3-8) that teaches the fundamentals of computer programming."
      url="https://www.robotturtles.com/" :searchTerm="props.searchTermString" />
    <BlueCard name="Sphero" description="A collection of codeable robots, design-and-build kits, software, and curriculum guides for PK-12 education."
      url="https://sphero.com/" :searchTerm="props.searchTermString" />
    <BlueCard name="Code Master^" description="A coding/logic game for kids 8 and up."
      url="https://www.thinkfun.com/products/code-master/" :searchTerm="props.searchTermString" />
    <BlueCard name="lightbot" description="A game to solve puzzles through programming."
      url="https://lightbot.com/" :searchTerm="props.searchTermString" />
  </div>


  <div class="w-full grid grid-cols-8 p-4 mt-10">
     <span class="grid text-xl col-span-4 text-blue-200">Websites</span>
  </div>
  <div class="grid sm:grid-cols-4 grid-cols-2">
    <BlueCard name="Codecademy" description="Free and paid coding lesson tracks."
      url="https://www.codecademy.com/" :searchTerm="props.searchTermString" />
    <BlueCard name="Code.org" description="Resources for parents and educators to spread CS education throughout the US."
      url="https://www.code.org/" :searchTerm="props.searchTermString" />
    <BlueCard name="Khan Academy" description="Various HTML and JavaScript educational videos."
      url="https://www.khanacademy.org/computing/computer-programming" :searchTerm="props.searchTermString" />
    <BlueCard name="freeCodeCamp" description="A free collection of lessons and certification tracks."
      url="https://www.freecodecamp.org/" :searchTerm="props.searchTermString" />
    <BlueCard name="MIT App Inventor" description="A visual programming environment to build apps for mobile devices."
      url="https://appinventor.mit.edu/" :searchTerm="props.searchTermString" />
    <BlueCard name="Scratch" description="A coding language to create and share stories, apps, and games."
      url="https://scratch.mit.edu/" :searchTerm="props.searchTermString" />
    <BlueCard name="Tynker" description="A paid coding platform for kids for home and school use."
      url="https://www.tynker.com/" :searchTerm="props.searchTermString" />

  </div>

  <div class="w-full bg-slate-500 grid grid-cols-8 p-4 mt-10" id="contact">
     <span class="grid text-xl col-span-4 text-purple-200">Contact</span>
  </div>
  <div class="bg-purple-200 p-4 rounded-lg m-4 shadow-purple-300/50 shadow-md">
    <iframe class="mx-auto" v-if="screenWidth > 640" src="https://docs.google.com/forms/d/e/1FAIpQLSdpdX7YTCwrHJavrk2j1iYawolnz9aXctkJUxe9RIiCtgNuAQ/viewform?embedded=true" width="640" height="677" frameborder="0" marginheight="0" marginwidth="0">Loading…</iframe>
    <iframe class="mx-auto" v-else src="https://docs.google.com/forms/d/e/1FAIpQLSdpdX7YTCwrHJavrk2j1iYawolnz9aXctkJUxe9RIiCtgNuAQ/viewform?embedded=true" width="240" height="677" frameborder="0" marginheight="0" marginwidth="0">Loading…</iframe>
  </div>
</div>
</template>

<style>
</style>
