<script>
import Dropdown from './Dropdown.vue'

export default {
   name: 'DropdownList',
   props: {
      qaList: {
         type: Array,
         default: () => []
      },
   },
   components: { Dropdown }
}
</script>

<template>
<div class="dropdown-list__container">
   <div
      v-for="(qa, index) in qaList"
      :key="index"
      class="dropdown-list__dropdown-container"
   >
      <Dropdown
         class="dropdown-list__dropdown"
         :question="qa.question"
         :answer="qa.answer"
      />
   </div>
</div>
</template>
