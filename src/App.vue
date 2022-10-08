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
    <GreenCard name="LiDAR Voxel Generator" image="/livoxgen.png" description="LiVoxGen is a C++ program that 'voxelizes' LiDAR data by partitioning a LAS file into columns of volumetric pixels and counting the LiDAR points inside each voxel. It is hosted on GitHub." 
      client="NASA" date="Spring 2015" service="Data Processing" url="http://megankress.github.io/LiVoxGen/#" />
    <GreenCard name="The Living Breathing Forest" image="/sciday.png" description="This website corresponds to an interactive 30-minute activity at the 2017 GWIS Middle School Girls Math and Science Day."
      client="GWIS Mid-Michigan Chapter" date="March 2017" service="Outreach" url="http://megankress.github.io/" />
  </div>

  <div class="w-full bg-slate-500 grid grid-cols-8 p-4 mt-10" id="resources">
     <span class="grid text-xl col-span-4 text-blue-200">Coding Resources</span>
  </div>

  <input type="text" placeholder="Filter by search term..." v-model="searchTermString" class="m-5 rounded-lg p-2"  />

  <div class="w-full grid grid-cols-8 p-4 mt-2">
     <span class="grid text-xl col-span-4 text-blue-200">Organizations</span>
  </div>
  <div class="grid sm:grid-cols-4 grid-cols-2">
    <BlueCard name="Code.org" description="A nonprofit dedicated to providing access to computer science in K-12 schools. It is the organizer of the annual Hour of Code campaign."
      url="https://code.org/" :searchTerm="searchTermString"/>
    <BlueCard name="CSEdWeek" description='"Computer Science Education Week is an annual call to action to inspire K-12 students to learn computer science, advocate for equity, and celebrate the contributions of students, teachers, and partners to the field."'
      url="https://www.csedweek.org/" :searchTerm="searchTermString"/>
    <BlueCard name="Computer Science Teachers Association" description="(CSTA) A teacher-led community that provides resources for K-12 educators."
      url="https://www.csteachers.org/" :searchTerm="searchTermString"/>
    <BlueCard name="The National Center for Women & Information Technology" description="(NCWIT) An organization of change leaders aiming to increase participation of girls and women in computing in an intersectional way."
      url="https://www.csteachers.org/" :searchTerm="searchTermString"/>
  </div>

  <div class="w-full grid grid-cols-8 p-4 mt-10">
     <span class="grid text-xl col-span-4 text-blue-200">Toys/Games</span>
  </div>
  <div class="grid sm:grid-cols-4 grid-cols-2">
    <BlueCard name="Coding Games for Beginners^^" description="A compilation of web-based games from HP Tech Takes"
      url="https://www.hp.com/us-en/shop/tech-takes/coding-games-for-beginners" :searchTerm="searchTermString" />
    <BlueCard name="STEM Toys and Games^^" description="A collection of STEM activities from FUN.com"
      url="https://www.fun.com/stem-toys-and-games.html" :searchTerm="searchTermString" />
    <BlueCard name="Arduino" description="Open source boards and software used for interactive projects. The website includes documentation, forums, and teacher guides and resources."
      url="https://www.arduino.cc/" :searchTerm="searchTermString" />
    <BlueCard name="Dash & Dot" description="Robots and apps to teach kids math and coding. Site includes learn to code curriculums and STEM funding guides."
      url="https://www.makewonder.com/" :searchTerm="searchTermString" />
    <BlueCard name="LEGO Mindstorms/LEGO Education SPIKE" description="Learning systems for the classroom to encourage creativity, collaboration, and critical thinking. Resources include lesson/unit plans and professional development information."
      url="https://education.lego.com/en-us/" :searchTerm="searchTermString" />
    <BlueCard name="Minecraft Education Edition" description="Lesson plans for the popular video game Minecraft that span STEM, Coding, SEL, History, Language Arts, and 21st Century Skills."
      url="https://education.minecraft.net/en-us" :searchTerm="searchTermString" />
    <BlueCard name="Digital Dream Labs" description="Consumer robots and educational video games for learning how to code."
      url="https://www.digitaldreamlabs.com/" :searchTerm="searchTermString" />
    <BlueCard name="Raspberry Pi" description="A UK-based nonprofit that produces low-cost single-board computers and software to advance the field of computing education."
      url="https://www.raspberrypi.org/" :searchTerm="searchTermString" />
    <BlueCard name="Robot Turtles" description="A board game for younger children (ages 3-8) that teaches the fundamentals of computer programming."
      url="https://www.robotturtles.com/" :searchTerm="searchTermString" />
    <BlueCard name="Sphero" description="A collection of codeable robots, design-and-build kits, software, and curriculum guides for PK-12 education."
      url="https://sphero.com/" :searchTerm="searchTermString" />
    <BlueCard name="Code Master^" description="A coding/logic game for kids 8 and up."
      url="https://www.thinkfun.com/products/code-master/" :searchTerm="searchTermString" />
    <BlueCard name="lightbot" description="A game to solve puzzles through programming."
      url="https://lightbot.com/" :searchTerm="searchTermString" />
  </div>


  <div class="w-full grid grid-cols-8 p-4 mt-10">
     <span class="grid text-xl col-span-4 text-blue-200">Websites</span>
  </div>
  <div class="grid sm:grid-cols-4 grid-cols-2">
    <BlueCard name="Codecademy" description="Free and paid coding lesson tracks."
      url="https://www.codecademy.com/" :searchTerm="searchTermString" />
    <BlueCard name="Code.org" description="Resources for parents and educators to spread CS education throughout the US."
      url="https://www.code.org/" :searchTerm="searchTermString" />
    <BlueCard name="Khan Academy" description="Various HTML and JavaScript educational videos."
      url="https://www.khanacademy.org/computing/computer-programming" :searchTerm="searchTermString" />
    <BlueCard name="freeCodeCamp" description="A free collection of lessons and certification tracks."
      url="https://www.freecodecamp.org/" :searchTerm="searchTermString" />
    <BlueCard name="MIT App Inventor" description="A visual programming environment to build apps for mobile devices."
      url="https://appinventor.mit.edu/" :searchTerm="searchTermString" />
    <BlueCard name="Scratch" description="A coding language to create and share stories, apps, and games."
      url="https://scratch.mit.edu/" :searchTerm="searchTermString" />
    <BlueCard name="Tynker" description="A paid coding platform for kids for home and school use."
      url="https://www.tynker.com/" :searchTerm="searchTermString" />

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
