<script setup>
defineProps({
   id: String,
   label: String,
   error: Boolean,
   disabled: Boolean,
   helperText: String,
   startIcon: String,
   endIcon: String,
   defaultValue: String,
   size: String,
   fullWidth: Boolean,
   multiline: Boolean,
   row: Number
})
</script>

<template>
  <div class="input-group" 
    :class="[
    {'error': error}
  ]">
    <label :for="id">{{ label }}</label>
    <span v-if="startIcon" class="material-icons-outlined icon start-icon">{{ startIcon }}</span>
    <textarea 
      v-if="multiline" 
      :id="id" 
      cols="30" 
      :rows="row"
      placeholder="Placeholder"
    ></textarea>

    <input
      v-else 
      type="text" 
      :id="id" 
      placeholder="Placeholder"
      :disabled="disabled ? true : false"
      :value="defaultValue"
      :class="[
        {'hasStartIcon': startIcon},
        {'hasEndIcon': endIcon},
        size == 'sm' ? 'sm-input' : '',
        {'full': fullWidth}
      ]"
    >
    <span v-if="endIcon" class="material-icons-outlined icon end-icon">{{ endIcon }}</span>
    <p v-if="helperText" class="helper-text">{{ helperText }}</p>
  </div>
</template>

<style scoped>
.input-group {
  margin: 16px 0;
  position: relative;
}
.input-group > label {
  font-size: 12px;
}

.input-group > input,
.input-group > textarea {
  display: block;
  margin-top: 4px;
  border: 1px solid var(--color-gray-3);
  border-radius: 8px;
  padding: 18px 12px;
  font-family: var(--ff-poppins);
  font-size: 14px;
  outline: none;
}

.input-group > textarea {
  resize: none;
}

input.hasStartIcon {
  padding: 18px 12px 18px 44px;
}
input.hasEndIcon {
  padding: 18px 44px 18px 12px;
}
input.sm-input {
  padding: 10px 12px;
}
input.full {
  width: 100%;
}

.input-group > .helper-text {
  margin-top: 4px;
  font-size: 10px;
  color: var(--color-gray-3);
}

.input-group > .icon {
  position: absolute;
  font-size: 17px;
  color: var(--color-gray-3);
  z-index: 100;
}
.input-group > .start-icon {
  top: 50%;
  left: 12px;
}
.input-group > .end-icon {
  top: 50%;
  right: 35px;
}


.input-group > input:hover,
.input-group > textarea:hover {
  border-color: var(--color-gray-1);
}
.input-group > input:is(:focus, :focus-visible),
.input-group > textarea:is(:focus, :focus-visible) {
  border-color: var(--color-primary-1);
}
.input-group:focus-within label {
  color: var(--color-primary-1);
}


.input-group > input:disabled {
  background-color: var(--color-gray-6);
  border-color: var(--color-gray-5);
  cursor: not-allowed;
}

.input-group.error > input {
  border: 1px solid var(--color-danger-1);
}
.input-group.error > label,
.input-group.error > .helper-text {
  color: var(--color-danger-1);
}
.input-group.error > input:is(:focus, :focus-visible) {
  border-color: var(--color-danger-1);
}
.input-group.error:focus-within label {
  color: var(--color-danger-1);
}
</style>
