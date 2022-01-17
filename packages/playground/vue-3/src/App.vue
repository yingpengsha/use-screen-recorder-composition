<template>
  <h1>use-screen-recorder-composition</h1>
  <div>
    <button
      v-if="['idle', 'permission-requested', 'error'].includes(screenRecorder.status)"
      @click="screenRecorder.actions.startRecording()"
    >
      start recording
    </button>
    <button
      v-if="['recording', 'paused'].includes(screenRecorder.status)"
      @click="screenRecorder.actions.stopRecording()"
    >
      stop recording
    </button>
    <template v-if="['recording', 'paused'].includes(screenRecorder.status)">
      <button
        v-if="screenRecorder.status === 'paused'"
        @click="screenRecorder.actions.resumeRecording()"
      >
        resume recording
      </button>
      <button v-else @click="screenRecorder.actions.pauseRecording()">
        pause recording
      </button>
    </template>
    <button
      v-if="['stopped'].includes(screenRecorder.status)"
      @click="screenRecorder.actions.resetRecording()"
    >
      reset recording
    </button>
  </div>
  <video
    v-if="screenRecorder.blobUrl"
    :src="screenRecorder.blobUrl"
    autoplay
    controls
  />
</template>

<script setup lang="ts">
import useScreenRecorder from "use-screen-recorder-composition";
const screenRecorder = useScreenRecorder();
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
video {
  max-width: 800px;
  max-height: 500px;
}
</style>
