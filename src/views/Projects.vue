<template>
  <div class="projects">
    <div class="row justify-content-center">
      <div
        v-for="(project, i) in projects"
        :key="i"
        class="col-lg col-sm-12 p-1"
      >
        <div class="border-dotted-block quaternary">
          <h3 class="tertiary">{{ project.name }}</h3>
          <p>{{ project.description }}</p>
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
          description: "Large Community.",
          tags: ["Ready"],
        },
                {
          name: "Mongosha",
          description: "Easy-to-use MongoDB database manager.",
          tags: ["Developing", "Ready", "v2.1.7"],
        },
                {
          name: "Discord Bots Store",
          description: "DiscordBots.Store will be a platform where you can sell your Discord bot projects.",
          tags: ["Developing", "Not Ready"],
        },
      ],
    };
  },
};
</script>