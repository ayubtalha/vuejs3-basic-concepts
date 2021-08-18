<!--USING TELEPORT - CHANGES IN INDEX.HTML-->
<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal" :class="{ sale: theme === 'sale' }">
      <slot>Defaul Slot</slot>
      <div class="actions">
        <slot name="links-one"></slot>
      </div>
      <div class="actions">
        <slot name="links-two"></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["theme"],
  methods: {
    closeModal() {
      this.$emit("close");
    },
  },
};
</script>

<style>
.modal {
  font-family: Arial, Helvetica, sans-serif;
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: white;
  border-radius: 10px;
}
.sale {
  font-family: Arial, Helvetica, sans-serif;
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: green;
  border-radius: 10px;
}
.backdrop {
  top: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}
.modal h1 {
  color: tomato;
}
.modal p {
  font-style: normal;
}
.modal .actions {
  text-align: center;
  margin: 30px 0px 10px 0px;
  color: #333;
}
</style>

<!--CHALLENGE - CREATING ANOTHER MODAL
<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal" :class="{ sale: theme === 'sale' }">
      <slot>Defaul Slot</slot>
      <div class="actions">
        <slot name="links-one"></slot>
      </div>
      <div class="actions">
        <slot name="links-two"></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["theme"],
  methods: {
    closeModal() {
      this.$emit("close");
    },
  },
};
</script>

<style>
.modal {
  font-family: Arial, Helvetica, sans-serif;
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: white;
  border-radius: 10px;
}
.sale {
  font-family: Arial, Helvetica, sans-serif;
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: green;
  border-radius: 10px;
}
.backdrop {
  top: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}
.modal h1 {
  color: tomato;
}
.modal p {
  font-style: normal;
}
.modal .actions {
  text-align: center;
  margin: 30px 0px 10px 0px;
  color: #333;
}
</style>
-->

<!--SLOTS - FOR SENDING CUSTOM TEMPLATES TO OTHER COMPONENTS
<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal" :class="{ sale: theme === 'sale' }">
      <slot>Defaul Slot</slot>
      <div class="actions">
        <slot name="links"></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["theme"],
  methods: {
    closeModal() {
      this.$emit("close");
    },
  },
};
</script>

<style>
.modal {
  font-family: Arial, Helvetica, sans-serif;
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: white;
  border-radius: 10px;
}
.sale {
  font-family: Arial, Helvetica, sans-serif;
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: green;
  border-radius: 10px;
}
.backdrop {
  top: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}
.modal h1 {
  color: tomato;
}
.modal p {
  font-style: normal;
}
.modal .actions {
  text-align: center;
  margin: 30px 0px 10px 0px;
  color: #333;
}
</style>
-->

<!-- CLICK EVENTS MODIFIERS
<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal" :class="{ sale: theme === 'sale' }">
      <h1>{{ header }}</h1>
      <p>{{ text }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ["header", "text", "theme"],
  methods: {
    closeModal() {
      this.$emit("close");
    },
  },
};
</script>

<style>
.modal {
  font-family: Arial, Helvetica, sans-serif;
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: white;
  border-radius: 10px;
}
.sale {
  font-family: Arial, Helvetica, sans-serif;
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: green;
  border-radius: 10px;
}
.backdrop {
  top: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}
.modal h1 {
  color: tomato;
}
.modal p {
  font-style: normal;
}
</style>
-->

<!-- EMITTING CUSTOM EVENTS
<template>
  <div class="backdrop" @click="closeModal">
    <div class="modal" :class="{ sale: theme === 'sale' }">
      <h1>{{ header }}</h1>
      <p>{{ text }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ["header", "text", "theme"],
  methods: {
    closeModal() {
      this.$emit("close");
    },
  },
};
</script>

<style>
.modal {
  font-family: Arial, Helvetica, sans-serif;
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: white;
  border-radius: 10px;
}
.sale {
  font-family: Arial, Helvetica, sans-serif;
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: green;
  border-radius: 10px;
}
.backdrop {
  top: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}
.modal h1 {
  color: tomato;
}
.modal p {
  font-style: normal;
}
</style>
-->

<!-- PROPS 
<template>
  <div class="backdrop">
    <div class="modal" :class="{ sale: theme === 'sale' }">
      <h1>{{ header }}</h1>
      <p>{{ text }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ["header", "text", "theme"],
};
</script>

<style>
.modal {
  font-family: Arial, Helvetica, sans-serif;
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: white;
  border-radius: 10px;
}
.sale {
  font-family: Arial, Helvetica, sans-serif;
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: green;
  border-radius: 10px;
}
.backdrop {
  top: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}
.modal h1 {
  color: tomato;
}
.modal p {
  font-style: normal;
}
</style>
-->

<!-- MULTIPLE COMPONENETS AND SCOPED STYLIN 
<template>
  <div class="backdrop">
    <div class="modal">
      <h1>Modal Title</h1>
      <p>Modal content</p>
    </div>
  </div>
</template>

<style>
.modal {
  font-family: Arial, Helvetica, sans-serif;
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: white;
  border-radius: 10px;
}
.backdrop {
  top: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}
/* .modal is class given to h1 above */
.modal h1 {
  color: tomato;
}
/* .modal p {
  font-style: normal;
} */
</style>
-->
