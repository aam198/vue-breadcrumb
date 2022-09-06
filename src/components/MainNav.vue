<template>
  <nav> 
    <ol class="breadcrumb">
      <li
        v-for="(crumb, ci) in crumbs"
        :key="ci"
        class="breadcrumb-item align-items-center">
        <button class="btn btn-link" :class="{disabled: isLast(ci) }" @click="selected(crumb)"> 
          {{ crumb }}
        </button>
      </li>
    </ol>
  </nav>
</template>

<script>
export default {
  props: {
    crumbs: {
      type: Array,
      required: true
    }
  }
  
}
</script>