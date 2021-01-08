<template>
  <div id="controls" class="w-1/4 flex-grow p-2">
    <fieldset class="flex flex-col border p-2 space-y-1">
      <legend>Simulation</legend>
      <button class="bg-white" @click="$emit('start')">Start</button>
      <button class="bg-white" @click="$emit('pause')">Pause</button>
    </fieldset>
    <fieldset class="flex flex-col border p-2 space-y-1">
      <legend>Entity</legend>

      <button class="bg-white" @click="$emit('add-location', 'source')">
        Add Source
      </button>
      <button class="bg-white" @click="$emit('add-location', 'destination')">
        Add Destination
      </button>
      <button
        class="bg-white"
        @click="$emit('add-location', 'busy-destination')"
      >
        Add Busy Destination
      </button>
      <button class="bg-white" @click="$emit('add-agent')">Add Agent</button>
    </fieldset>
    <fieldset class="flex flex-col border p-2">
      <legend>Setting</legend>
      <select id="updateSettingKey">
        <option value="assignIdleAgentToOpenJobStrategy">foo</option>
      </select>
      <input id="updateSettingValue" type="text" />
      <button id="updateSetting">Update</button>
    </fieldset>
    <fieldset class="flex flex-col border p-2">
      <legend>Data</legend>
      <button id="export">Export</button>
      <button id="import">Import</button>
    </fieldset>
  </div>
</template>

<script>
export default {
  name: 'GameControls',
}
</script>
