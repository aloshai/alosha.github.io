<template>
  <div class="projects">
    <div class="row justify-content-center">
      <div
        v-for="(project, i) in projects"
        :key="i"
        class="col-lg-4 col-md-6 col-sm-12 p-1"
      >
        <div
          @click="go(project.target)"
          style="display: flex; flex-direction: column"
          class="border-dotted-block quaternary"
        >
          <h3 class="tertiary">{{ project.name }}</h3>
          <p style="flex-grow: 1">{{ project.description }}</p>
          <div v-if="project.tags.length > 0" class="row p-2">
            <div
              v-for="(tag, j) in project.tags"
              :key="j"
              class="col-2 p-2 tag"
            >
              {{ tag }}
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      projects: [
        {
          name: "Serendia Squad",
          description:
            "Charity, Community, Consultation and open source co-project sharing squad.",
          tags: ["Project", "Website"],
          target: "https://serendiasquad.xyz/",
        },
        {
          name: "Mongosha",
          description: "Easy-to-use MongoDB database manager.",
          tags: ["Open Source", "Ready", "v2.1.7"],
          target: "https://www.npmjs.com/package/mongosha",
        },
        {
          name: "Discord Bots Store",
          description:
            "DiscordBots.Store will be a platform where you can sell your Discord bot projects.",
          tags: ["Not Ready", "Open Source"],
          target: "https://discordbots.store/",
        },
        {
          name: "Betsha",
          description:
            "Color guessing game I developed with Socket.io, express and Vue.",
          tags: ["Pre-Release", "Open Source"],
          target: "https://github.com/betsha",
        },
        {
          name: "Sha.NET",
          description: "A framework I developed for FiveM RPG.",
          tags: ["Developing", "Not Ready", "Open Source"],
          target: "https://github.com/ShaFramework",
        },
        {
          name: "Vehicle Sales",
          description: "A website that will do things such as vehicle advertisements, sale or rental. (You can buy or advertise)",
          tags: ["Open Source", "Website"],
          target: "https://github.com/aloshai",
        },
      ],
    };
  },

  methods: {
    go(str) {
      window.open(str);
    },
  },
};
</script>