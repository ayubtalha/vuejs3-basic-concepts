<!--USING TELEPORT - CHANGES IN INDEX.HTML-->
<template>
  <h1>{{ title }}</h1>
  <p>Welcome ...</p>
  <teleport to=".modals" v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links-one>
        <a href="#">Modal Slot 1</a>
      </template>
    </Modal>
  </teleport>

  <div v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <template v-slot:links-two>
        <a href="#">Modal Slot2</a>
      </template>
    </Modal>
  </div>
  <button @click="toggleModal">Show Modal</button>
  <button @click="toggleModalTwo">Show Modal 2</button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "My first vue App :) ",
      showModal: false,
      showModalTwo: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo;
    },
  },
};
</script>

<style>
#app,
.modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  background-color: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>

<!--CHALLENGE - CREATING ANOTHER MODAL
<template>
  <h1>{{ title }}</h1>
  <p>Welcome ...</p>
  <div v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links-one>
        <a href="#">Modal Slot 1</a>
      </template>
    </Modal>
  </div>

  <div v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <template v-slot:links-two>
        <a href="#">Modal Slot2</a>
      </template>
    </Modal>
  </div>
  <button @click="toggleModal">Show Modal</button>
  <button @click="toggleModalTwo">Show Modal 2</button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "My first vue App :) ",
      showModal: false,
      showModalTwo: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo;
    },
  },
};
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
h1 {
  background-color: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
-->

<!--SLOTS
<template>
  <h1>{{ title }}</h1>
  <p>Welcome ...</p>
  <div v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      // Named slots
      <template v-slot:links>
        <a href="#">Sign up Now</a>
      </template>
      // Default Slots 
      //  <h2>
      //   Here we are Using <span><h1>SLOT</h1></span>
      // </h2>
      // <p>Used SLOT</p>
    </Modal>
  </div>
  <button @click="toggleModal">Show Modal</button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "My first vue App :) ",
      header: "Please sign up here",
      text: "It is all coming from App.vue which is the parent component",
      showModal: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
  },
};
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
h1 {
  background-color: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
-->

<!-- CLICK EVENTS MODIFIERS
<template>
  <h1>{{ title }}</h1>
  <p>Welcome ...</p>
  <div v-if="showModal">
    <Modal :header="header" :text="text" theme="sale" @close="toggleModal" />
  </div>
  <button @click.alt="toggleModal">Show Modal (alt)</button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "My first vue App :) ",
      header: "Please sign up here",
      text: "It is all coming from App.vue which is the parent component",
      showModal: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
  },
};
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
h1 {
  background-color: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
-->

<!-- EMITTING CUSTOM EVENTS
<template>
  <h1>{{ title }}</h1>
  <p>Welcome ...</p>
  <div v-if="showModal">
    <Modal :header="header" :text="text" theme="sale" @close="toggleModal" />
  </div>
  <button @click="toggleModal">Show Modal</button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "My first vue App :) ",
      header: "Please sign up here",
      text: "It is all coming from App.vue which is the parent component",
      showModal: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
  },
};
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
h1 {
  background-color: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
 -->

<!-- PROPS 
<template>
  <p>Hi gee</p>
  <h1>{{ title }}</h1>
  <Modal :header="header" :text="text" theme="sale" />
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "My first vue App :) ",
      header: "Please sign up here",
      text: "It is all coming from App.vue which is the parent component",
    };
  },
};
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
h1 {
  background-color: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
-->

<!-- MULTIPLE COMPONENTS 
<template>
  <p>Hi gee</p>
  <h1>{{ title }}</h1>
  <Modal />
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: { Modal },
  data() {
    return { title: "My first vue App :) " };
  },
};
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
h1 {
  background-color: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
-->

<!-- TEMPLATE REFS -->
<!-- 
<template>
  <h1>{{ title }}</h1>
  <input type="text" ref="name" />
  <button @click="handleClick">Click Me</button>
</template>

<script>
export default {
  name: "App",
  data() {
    return { title: "My first vue App :) " };
  },
  methods: {
    handleClick() {
      console.log(this.$refs.name);
      this.$refs.name.classList.add("active");
      this.$refs.name.focus();
    },
  },
};
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
h1 {
  background-color: black;
}
</style>
 -->
