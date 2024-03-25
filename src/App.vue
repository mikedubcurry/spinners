<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://vuejs.org/api/sfc-script-setup.html#script-setup
import { ref } from "@vue/reactivity";
import BasicSpinner from "./components/Basic.vue";
import DotJump from "./components/DotJump.vue";
import Dna from "./components/Dna.vue";

let loading = ref(false);

function wait() {
  loading.value = true;
  return new Promise((resolve) => {
    setTimeout(() => {
      resolve();
      loading.value = false;
    }, 10000);
  });
}

function handleChange(e) {
  selectedSpinner.value = e.target.value;
  console.log(selectedSpinner);
}

let spinners = [
  { component: BasicSpinner, name: "basic" },
  { component: DotJump, name: "dots" },
  { component: Dna, name: 'dna' }
];
let selectedSpinner = ref(0);
</script>

<template>
  <component
    v-if="loading"
    v-bind:is="spinners[selectedSpinner].component"
  ></component>

  <button @click="wait">Wait</button>
  <select @change="handleChange">
    <option
      v-for="(spinner, index) in spinners"
      :key="spinner.name"
      :value="index"
    >
      {{ spinner.name }}
    </option>
  </select>
  <h1>Lorem</h1>
  <h2>Ipsum</h2>
  <section>
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloremque esse
    magnam, eligendi labore nobis ut praesentium dolor sapiente voluptatem,
    pariatur aspernatur. Modi saepe quidem omnis nemo esse obcaecati facere
    corporis!
  </section>
  <h2>Ipsum</h2>
  <section>
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloremque esse
    magnam, eligendi labore nobis ut praesentium dolor sapiente voluptatem,
    pariatur aspernatur. Modi saepe quidem omnis nemo esse obcaecati facere
    corporis!
    <h3>Dolor</h3>
    <p>
      Lorem ipsum dolor sit amet consectetur, adipisicing elit. Optio nam id
      veniam ab! Voluptas possimus sit cum. Recusandae accusantium quae modi ex
      earum, nihil, rem hic nesciunt dolorem quas dolore! Culpa iusto enim
      quibusdam modi reiciendis corporis asperiores! Odit facere, at sed
      voluptas debitis aut quod dolorem iusto illum praesentium laboriosam,
      tenetur a ipsum! Deserunt quidem omnis vitae dolor ut.
    </p>
  </section>
  <h2>Sit</h2>
  <section>
    Lorem ipsum, dolor sit amet consectetur adipisicing elit. Ad vel non velit
    officia beatae magni inventore aliquam eius animi quia incidunt nihil a
    nulla libero, ex commodi harum exercitationem molestias.
  </section>
  <h2>amet</h2>
  <section>
    Lorem ipsum dolor sit amet, consectetur adipisicing elit. Aspernatur
    architecto facere amet nostrum ipsum hic facilis labore, quam, nisi possimus
    repellat nemo nobis dignissimos molestias pariatur cum omnis! Repellat, eos!
    Quis quos magnam optio totam et nulla odit quod itaque, aut amet voluptas
    voluptatem iusto beatae deleniti in molestiae architecto corporis vel iure
    quisquam repellendus tempora nemo vero eum? Nostrum. Nobis, eum! Cum itaque
    dolores quibusdam, doloremque quos rerum minus modi quidem officia neque sed
    unde suscipit earum tempore quod, vel pariatur in, corporis quisquam
    perspiciatis sint a ipsam odit!
  </section>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
