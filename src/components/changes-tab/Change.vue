<template>
  <div
      class="change"
  >
    <a
        class="subject"
        target="_blank"
        v-bind:href="url"
    >
      {{ subject }}
    </a>
    <div class="repository-type">
      <span class="badge">
        {{ type }}
      </span>

      <span class="badge" v-if="!build?.version">
        {{ branch }}
      </span>

      <span class="repository">
        {{ repository }}
      </span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Change',
  props: {
    url: String,
    subject: String,
    repository: String,
    type: String,
    branch: String,
    build: Object,
  },
}
</script>

<style scoped>
.change {
  padding: 8px 0;
}

.change .subject,
.change .repository {
  display: block;

  vertical-align: text-bottom;
}

.change .subject {
  line-height: 28px;

  color: inherit;
  text-decoration: none;
}

.change .repository-type {
  font-size: 12px;
  line-height: 24px;

  display: flex;
  align-items: center;
}

.change .badge {
  border-radius: 12px;
  padding: 0 8px;
  margin-right: 8px;

  background: rgba(0, 0, 0, 0.15);
}

#app.dark .change .badge {
  background: rgba(255, 255, 255, 0.15);
}
</style>