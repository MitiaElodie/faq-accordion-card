<script>
import { OnClickOutside } from '@vueuse/components'
export default {
  name: 'Dropdown',
  components: { OnClickOutside },
  props: {
    question: {
      type: String,
      default: '',
    },
    answer: {
      type: String,
      default: '',
    },
  },

  data() {
    return {
      isOpen: false,
    }
  },

  methods: {
    onClickOutside() {
      this.isOpen = false;
    },

    onClickInside() {
      this.isOpen = !this.isOpen;
    }
  }
}
</script>

<template>
  <OnClickOutside @trigger="onClickOutside">  
    <div
      class="dropdown__container"
      :class="{ 'dropdown--open': isOpen }"
      @click="onClickInside"
    >
      <div class="dropdown__question-container">
        <span
          class="dropdown__question"
          
        >{{ question }}</span>
        <div class="dropdown__icon-container">
          <img src="../assets/icon-arrow-down.svg" alt="Icon" class="dropdown__icon" />
        </div>
      </div>
      <div
        v-if="isOpen"
        class="dropdown__answer-container"
      >
        {{ answer }}
      </div>
    </div>
  </OnClickOutside>
</template>


<style lang="scss">
@use '../styles/constants.scss';

.dropdown {
  &__container {
    padding: 20px 0px;
    line-height: 1.8em;

    &:hover {
      cursor: pointer;

      &:not(.dropdown--open) .dropdown__question {
        color: constants.$soft-red;
      }
    }
  }
  
  &__question-container {
    display: flex;
    justify-content: space-between;
  }

  &__answer-container {
    margin-top: 10px;
    color: constants.$dark-grayish-blue;
  }

  &--open {

    & .dropdown__question {
      font-weight: 700;
      color: constants.$very-dark-desaturated-blue;
    }
  }
}
</style>
