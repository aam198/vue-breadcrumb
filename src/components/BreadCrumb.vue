<template>
  <nav aria-label="breadcrumb" style="--bs-breadcrumb-divider: '>';"> 
    <ol class="breadcrumb">
      <li
        v-for="(crumb, index) in crumbs"
        :key="index"
        class="breadcrumb-item align-items-center">

        <button class="btn btn-link" :class="{disabled: isLast(index) }" @click="selected(crumb)"> 
          {{ crumb }}
        </button>

      </li>
    </ol>
  </nav>
</template>

<script>
export default {
  props: {
    // To be defined in app.vue
    crumbs: {
      type: Array,
      required: true
    }
  },
  methods: {
    isLast(index){
      return index === this.crumbs.length - 1;
    },
    selected(crumb) {
      this.$emit('selected', crumb);
    }
  }
  
}
</script>

<style scoped>
.breadcrumb {
  background-color: white;
  border: 1px solid rgba(0, 0, 0, 0.125);
  border-radius: 0.37rem;
  justify-content: center;
  max-width: 40%;
  width: 100%;
}

.breadcrumb-item + .breadcrumb-item::before {
  float: none;
}



</style>