<template>
  <div class="home">
    <div class="text-center mb-4">
      <h1 id="welcome"></h1>
      <h3 class="uppercase" id="dev"></h3>
    </div>

    <div id="who-div" class="d-none m-2 border-dotted-block quaternary">
      <h2 id="who-title" class="tertiary">Who I am?</h2>
      <p id="who"></p>
    </div>
    <div id="contact-me-div" class="d-none m-2 border-dotted-block quaternary">
      <h2 id="contact-title" class="tertiary">Do you want to contact?</h2>
      <p id="contact"></p>
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
      10
    );
    await this.typeWriter(
      "dev",
      '<span class="quaternary">FULL-STACK</span> Developer.',
      10
    );

    document
      .getElementById("who-div")
      .style.setProperty("display", "block", "important");
    await this.typeWriter("who-title", "Who I am?", 10);
    await this.typeWriter(
      "who",
      'I am <span class="green">Mert Yılmaz</span>. I am <span class="green">17</span> years old and I am a high school student. I am still learning new stuff in programming. I am an <span class="green">.NET</span>, <span class="green">JavaScript</span>, <span class="green">TypeScript</span>, and <span class="green">Vue</span> developer. Beside them, I am also interested in <span class="green">DevOps</span>.',
      10
    );
    document
      .getElementById("contact-me-div")
      .style.setProperty("display", "block", "important");
    await this.typeWriter("contact-title", "Do you want to contact?", 10);
    await this.typeWriter(
      "contact",
      'You can find on me my <span class="green">e-mail</span> address or on my <span class="green">Discord account</span>.',
      10
    );
  },
};
</script>
