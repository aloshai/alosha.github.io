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
import Typewriter from "typewriter-effect/dist/core";

export default {
  name: "Home",
  async mounted() {
    new Typewriter("#welcome", {
      loop: false,
      delay: 25,
    })
      .typeString('Hello, I am <span class="quaternary">Alosha</span>!')
      .callFunction(() => {
        new Typewriter("#dev", {
          loop: false,
          delay: 25,
        })
          .typeString('<span class="quaternary">FULL-STACK</span> Developer.')
          .callFunction(() => {
            document
              .getElementById("who-div")
              .style.setProperty("display", "block", "important");

            new Typewriter("#who-title", {
              loop: false,
              delay: 25,
            })
              .typeString("Who I am?")
              .callFunction(() => {
                new Typewriter("#who", {
                  loop: false,
                  delay: 25,
                })
                  .typeString(
                    'I am <span class="green">Mert Yılmaz</span>. I am <span class="green">17</span> years old and I am a high school student. I am still learning new stuff in programming. I am an <span class="green">.NET</span>, <span class="green">JavaScript</span>, <span class="green">TypeScript</span>, and <span class="green">Vue</span> developer. Beside them, I am also interested in <span class="green">DevOps</span>.'
                  )
                  .callFunction(() => {
                    document
                      .getElementById("contact-me-div")
                      .style.setProperty("display", "block", "important");

                    new Typewriter("#contact-title", {
                      loop: false,
                      delay: 25,
                    })
                      .typeString("Do you want to contact?")
                      .callFunction(() => {
                        new Typewriter("#contact", {
                          loop: false,
                          delay: 25,
                        })
                          .typeString(
                            'You can find on me my <span class="green">e-mail</span> address or on my <span class="green">Discord account</span>.'
                          )
                          .start();
                      })
                      .start();
                  })
                  .start();
              })
              .start();
          })
          .start();
      })
      .start();
  },
};
</script>
