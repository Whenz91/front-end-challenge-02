<script setup>
import Input from './components/Input.vue';

const sampleCodes = {
  default: '<Input label="Label name" id="unique id" />',
  hasError: '<Input label="Label name" id="unique id" error />',
  disabledInput: '<Input label="Label name" id="unique id" disabled />',
  inputWithText: '<Input label="Label name" id="unique id" helperText="Some text" />',
  inputWithTextAndError: '<Input label="Label name" id="unique id" error helperText="Some text" />',
  inputStartIcon: '<Input label="Label name" id="unique id" startIcon="call" />',
  inputEndIcon: '<Input label="Label name" id="unique id" endIcon="lock" />',
  hasDefValue: '<Input label="Label name" id="unique id" defaultValue="Text" />',
  inputSizeSm: '<Input label="Label name" id="unique id" size="sm" />',
  inputSizeMd: '<Input label="Label name" id="unique id" size="md" />',
  inputFullWidth: '<Input label="Label name" id="unique id" fullWidth" />',
  inputMultilines: '<Input label="Label name" id="unique id" multiline row=4 />'
}
</script>

<template>
 <main>
   <h1>Inputs</h1>

   <pre><code>{{ sampleCodes.default }}</code></pre>
   <Input label="Label" id="uuid-1" />

   <pre><code>{{ sampleCodes.hasError }}</code></pre>
   <Input label="Label" id="uuid-2" error />

   <pre><code>{{ sampleCodes.disabledInput }}</code></pre>
   <Input label="Label" id="uuid-3" disabled />

   <ul class="flex no-list my-20">
     <li>
        <pre><code>{{ sampleCodes.inputWithText }}</code></pre>
        <Input label="Label" id="uuid-4" helperText="Some text" />
     </li>
     <li>
        <pre><code>{{ sampleCodes.inputWithTextAndError }}</code></pre>
        <Input label="Label" id="uuid-5" error helperText="Some text" />
     </li>
   </ul>

   <ul class="flex no-list my-20">
     <li>
        <pre><code>{{ sampleCodes.inputStartIcon }}</code></pre>
        <Input label="Label" id="uuid-6" startIcon="call" />
     </li>
     <li>
        <pre><code>{{ sampleCodes.inputEndIcon }}</code></pre>
        <Input label="Label" id="uuid-7" endIcon="lock" />
     </li>
   </ul>

   <pre><code>{{ sampleCodes.hasDefValue }}</code></pre>
   <Input label="Label" id="uuid-8" defaultValue="Text" />

    <ul class="flex no-list my-20">
     <li>
        <pre><code>{{ sampleCodes.inputSizeSm }}</code></pre>
        <Input label="Label" id="uuid-9" size="sm" />
     </li>
     <li>
        <pre><code>{{ sampleCodes.inputSizeMd }}</code></pre>
        <Input label="Label" id="uuid-10" size="md" />
     </li>
   </ul>

   <pre><code>{{ sampleCodes.inputFullWidth }}</code></pre>
   <Input label="Label" id="uuid-11" fullWidth defaultValue="Text" />

   <pre><code>{{ sampleCodes.inputMultilines }}</code></pre>
   <Input label="Label" id="uuid-12" multiline row=4 />
   
 </main>
</template>

<style>
@import './assets/base.css';

h1 {
  font-size: 24px;
  font-weight: 500;
  margin-bottom: 28px;
}

code {
  font-family: var(--ff-ubuntu);
  font-weight: 400;
}

.flex {
  display: flex;
  column-gap: 125px;
}
.no-list {
  list-style-type: none;
  margin: 0;
  padding: 0;
}
.my-20 {
  margin-top: 20px;
  margin-bottom: 20px;
}

</style>
