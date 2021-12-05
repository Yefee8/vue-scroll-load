<template>
  <div id="app">
    <header
        class="w-screen h-24 bg-gray-700 flex justify-around items-center opacity-50 hover:opacity-100 transition duration-500">
      <h2 class="underline text-red-500 cursor-pointer font-sans text-xl">About</h2>
      <h1 class="text-3xl block font-serif" style="background: crimson;">Header title</h1>
      <h2 class="underline text-sky-500 cursor-pointer font-sans text-xl">Reach us</h2>
    </header>
    <div class="posts flex flex-wrap justify-around text-white">
        <div v-for="key in showedPosts" :key="key.title" class="post w-2/5 border border-gray-500 min-h-96 mt-12 pb-4 flex flex-col">
          <img
              src="https://images.pexels.com/photos/1001682/pexels-photo-1001682.jpeg?auto=compress&cs=tinysrgb&dpr=1&w=500">
          <br>
          <h1 class="text-center text-2xl">{{key.title}}</h1>
          <br>
          <p class="text-lg text-center mx-4">{{key.desc}}</p>
          <center>
            <button
                class="text-lg rounded p-5 mt-4 border-orange-500 border-2 hover:border-sky-500 transition duration-500">
              Go to the post
            </button>
          </center>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      showedPosts: [
      {
        title: "Lorem ipsum",
        desc: "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s"
      },
        {
          title:"Lorem ipsum2",
          desc:"Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s"
        },
        {
          title: "Lorem ipsum3",
          desc: "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s"
        },
        {
          title:"Lorem ipsum4",
          desc:"Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s"
        },
      ],
      posts: [
        {
          title: "Lorem ipsum",
          desc: "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s"
        },
        {
          title:"Lorem ipsum 2",
          desc:"Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s"
        },
        {
          title: "Lorem ipsum 3",
          desc: "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s"
        },
        {
          title:"Lorem ipsum 4",
          desc:"Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s"
        },
        {
          title: "Lorem ipsum 5",
          desc: "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s"
        },
        {
          title:"Lorem ipsum 6",
          desc:"Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s"
        },
        {
          title: "Lorem ipsum 7",
          desc: "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s"
        },
        {
          title:"Lorem ipsum 8",
          desc:"Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s"
        },
        {
          title: "Lorem ipsum 9",
          desc: "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s"
        },
        {
          title:"Lorem ipsum 10",
          desc:"Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s"
        },
      ]
    }
  },
  created() {
    let x = 0;
      window.addEventListener('scroll', ()=>{
        if(x >= 1){
          console.log(document.body.scrollHeight);
          console.log(window.scrollY);
          if(document.body.scrollHeight <= window.scrollY + 1200){
            if(this.showedPosts.length === this.posts.length){
              return;
            }
            this.showedPosts.push(this.posts[this.showedPosts.length]);
            return;
          }
        }
        else if(window.innerHeight <= Math.ceil(window.scrollY + window.innerHeight * 4/5)) {
          console.log('a. ' + window.innerHeight);
          this.showedPosts.push(this.posts[this.showedPosts.length]);
          return x++;
        }
      });
  }
}
</script>

<style>
body {
  @apply bg-gray-800;
  overflow-x: hidden;
  max-width: 100%;
}

.post {
    animation: rotate ease-in-out 2s forwards;
}

@keyframes rotate {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
</style>
