<template>
  <div class="home">
    <div class="text-center">
      <h1 class="d-none" id="welcome"></h1>
      <h3 class="d-none uppercase" id="dev"></h3>
    </div>

    <div
      id="who-div"
      onclick="github()"
      class="d-none border-dotted-block quaternary"
    >
      <h2 id="who-title" class="tertiary">Who I am?</h2>
      <p id="who"></p>
    </div>
    <div
      id="hire-me-div"
      onclick="github()"
      class="d-none border-dotted-block quaternary"
    >
      <h2 id="hire-title" class="tertiary">Hire me?</h2>
      <p id="hire"></p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
  methods: {
    typeWriter: async function (id, txt, speed = 50) {
      document.getElementById(id).style.display = "block";
      for (let i = 0; i < txt.length; i++) {
        document.getElementById(id).innerHTML = txt.substr(0, i);
        // document.getElementById(id).innerHTML += txt.charAt(i);
        await new Promise((resolve) => setTimeout(resolve, speed));
      }
      document.getElementById(id).innerHTML = txt;
    },
  },

  async mounted() {
    await this.typeWriter(
      "welcome",
      'Hello, I am <span class="quaternary">Alosha</span>!',
      50
    );
    await this.typeWriter(
      "dev",
      '<span class="quaternary">FULL-STACK</span> Developer.',
      25
    );

    document.getElementById("who-div").style.display = "block";
    await this.typeWriter("who-title", "Who I am?", 50);
    await this.typeWriter(
      "who",
      'Hi there! I am <span class="green">Mert Yılmaz</span>. I am <span class="green">17</span> years old and I am an high school student. I am still learning new stuff in programming. I am an <span class="green">.NET</span>, <span class="green">JavaScript</span>, <span class="green">TypeScript</span>, and <span class="green">Vue</span> developer. Beside them, I am also interested in <span class="green">DevOps</span>.',
      25
    );
    document.getElementById("hire-me-div").style.display = "block";
    await this.typeWriter("hire-title", "Hire Me?");
    await this.typeWriter(
      "hire",
      'If you want to give me a job, you can reach me at my <span class="green">e-mail address</span> or on my <span class="green">Discord account</span>.',
      25
    );
  },
};
</script>
