<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div class="input">
    <input type="text" placeholder="Pesquisar..." v-model="searchQuery" />

    <span class="input__clear">&times;</span>
  </div>
</template>

<script>
export default {
  props: {
    value: {
      type: String,
      required: true,
    }
  },
  computed: {
    searchQuery: {
      get() {
        return this.value
      },
      set(val) {
        this.$emit('input', val);
      }
    }
  }
}
</script>

<style scoped>
.input {
  display: flex;
  width: 100%;
  position: relative;
}

.input input {
  width: 100%;
  padding: 8px 22px 8px 10px;
  font-size: 1rem;
  border: 1px solid #e3e3e3;
  background-color: #fafafa;
  border-radius: 6px;
  outline: none;
}
.input input:focus {
  border-color: rgb(189,61,255);
}
.input .input__clear {
  position: absolute;
  top: 6px;
  right: 6px;
  font-size: 18px;
  color: red;
}
.input .input__clear:hover {
  cursor: pointer;
}
</style>