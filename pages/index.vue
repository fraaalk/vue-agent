<template>
  <div class="flex bg-gray-700">
    <div id="scene" class="w-3/4 border relative" @click="handleSceneClick">
      <location
        v-for="(location, i) in locations"
        :key="`location-${i}`"
        v-bind="{ ...location }"
      />
      <agent
        v-for="(agent, i) in agents"
        :key="`agent-${i}`"
        v-bind="{ ...agent }"
      />
    </div>
    <game-controls
      class="w-1/4 flex-grow p-2"
      @add-location="addLocation"
      @add-agent="addAgent"
      @start="toggleGame(true)"
      @end="toggleGame(false)"
    />
  </div>
</template>

<script>
import { ref } from '@nuxtjs/composition-api'
import GameControls from '~/components/game-controls'
import Location from '~/components/location'
import Agent from '~/components/agent'

export default {
  components: {
    GameControls,
    Location,
    Agent,
  },

  setup() {
    const isRunning = ref(false)
    const locations = ref([])
    const agents = ref([])
    let addEntity = false
    let entity = null

    function handleSceneClick(event) {
      if (!addEntity) {
        return
      }

      locations.value.push({
        type: entity,
        x: event.clientX,
        y: event.clientY,
      })

      addEntity = false
      entity = null
    }

    function toggleGame(value) {
      isRunning.value = value
    }

    function addLocation(entityName) {
      entity = entityName
      addEntity = true
    }

    function addAgent() {
      agents.value.push({
        name: 'Agent' + Math.random(200),
      })
    }

    return {
      locations,
      agents,
      addLocation,
      addAgent,
      handleSceneClick,
      toggleGame,
      isRunning,
    }
  },
}
</script>

<style></style>
