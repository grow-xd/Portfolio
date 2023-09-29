<template>
  <div class="App">
    <DynamicDesignToggler />
  </div>
  
  <section class="bg-black">
    <div class="max-w-lg bg-black px-4 pt-10 py-8 mx-auto text-left md:max-w-none md:text-center">

      <div class="px-10 flex justify-center items-center spaces-x-10">
        <a href="https://github.com/grow-xd">
          <button
            class="py-2 px-4 text-white-600 font-mono font-semibold text-white rounded-full hover:bg-white hover:text-black transition ease-in duration-200 transform hover:-translate-y-1 active:translate-y-0">
            Github
          </button>
        </a>
        <a href="https://twitter.com/growXD_">
          <button
            class="py-2 px-4 text-white-600 font-mono font-semibold text-white rounded-full hover:bg-white hover:text-black transition ease-in duration-200 transform hover:-translate-y-1 active:translate-y-0">
            X / Twitter
          </button>
        </a>
        <a href="https://www.linkedin.com/in/grow-xd/">
          <button
            class="py-2 px-4 text-white-600 font-mono font-semibold text-white rounded-full hover:bg-white hover:text-black transition ease-in duration-200 transform hover:-translate-y-1 active:translate-y-0">
            Linkedin
          </button>
        </a>
        <a href="https://www.instagram.com/rishabh.rg_/">
          <button
            class="py-2 px-4 text-white-600 font-mono font-semibold text-white rounded-full hover:bg-white hover:text-black transition ease-in duration-200 transform hover:-translate-y-1 active:translate-y-0">
            Instagram
          </button>
        </a>
        <a href="mailto:gupta.rg.rishabh@gmail.com">
          <button
            class="py-2 px-4 text-white-600 font-mono font-semibold text-white rounded-full hover:bg-white hover:text-black transition ease-in duration-200 transform hover:-translate-y-1 active:translate-y-0">
            Email
          </button>
        </a>

      </div>
      <h1
        class="text-3xl font-extrabold leading-10 tracking-tight text-left text-white text-center sm:leading-none pt-10 md:text-6xl text-4xl lg:text-7xl">
        <span class="inline md:block">Thank You</span>
        <div></div>
        <span
          class=" mt-2 bg-clip-text text-transparent bg-gradient-to-r from-purple-400 via-emerald-400 to-green-500 md:inline-block">
          Download<span class="bg-clip-text text-transparent bg-gradient-to-r from-teal-500 via-cyon-400 to-purple-300">
            Resume</span> </span>
      </h1>
      <div class="mx-auto rounded-lg font-black mt-5 text-zinc-400 md:mt-12 md:max-w-lg text-center lg:text-lg">
        <a href="https://drive.google.com/file/d/1s4NyoKjg2X934B_u1_tlI25HiqzFN_EH/view?usp=sharing" class="bg-tkb border text-sm text-white py-3 px-7 rounded-full" onClick={signInNow}>
          Download
        </a>
      </div>
    </div>
  </section>
</template>

<script>
import DynamicDesignToggler from './DynamicDesignToggler.vue';

export default {
  components: {
    DynamicDesignToggler,
  },
};
</script>

<style>/* Add your global CSS styles here */</style>
