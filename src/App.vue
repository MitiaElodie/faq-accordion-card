<script>
import DropdownList from './components/DropdownList.vue'

export default {
  name: 'App',
  components: {
    DropdownList
  },

  data() {
    return {
      qaList: [
        {
          question: 'How many team members can I invite?',
          answer: 'You can invite up to 2 additional users on the Free plan. There is no limit on team members for the Premium plan.',
        },
        {
          question: 'What is the maximum file upload size?',
          answer: 'No more than 2GB. All files in your account must fit your allotted storage space.',
        },
        {
          question: 'How do I reset my password?',
          answer: 'Click “Forgot password” from the login page or “Change password” from your profile page. A reset link will be emailed to you.',
        },
        {
          question: 'Can I cancel my subscription?',
          answer: 'Yes! Send us a message and we’ll process your request no questions asked.',
        },
        {
          question: 'Do you provide additional support?',
          answer: 'Chat and email support is available 24/7. Phone lines are open during normal business hours.',
        },
      ]
    }
  }
}
</script>

<template>
  <main>
    <div class="faq__container">
      <div class="faq__content">
        <div class="faq__img-container faq__img-container--desktop">
          <img class="faq__img-person" alt="Someone browsing the faq" src="./assets/illustration-woman-online-desktop.svg"/>
          <img class="faq__img-box" alt="Mail box" src="./assets/illustration-box-desktop.svg"/>
        </div>

        <div class="faq__img-container faq__img-container--mobile">
          <img class="faq__img-person" alt="Someone browsing the faq" src="./assets/illustration-woman-online-mobile.svg"/>
        </div>
        <div class="faq__question-list">
          <h1 class="faq__title">FAQ</h1>
          <DropdownList
            class="faq__dropdown-list"
            :qa-list="qaList"
          />
        </div>
      </div>
    </div>
  </main>
  <footer>
    <div class="attribution">
      Challenge by <a href="https://www.frontendmentor.io?ref=challenge" target="_blank">Frontend Mentor</a>. 
      Coded by <a href="https://www.frontendmentor.io/profile/MitiaElodie">Anjara Mitia Elodie</a>.
    </div>
  </footer>
</template>

<style lang="scss">
@use './styles/constants.scss';
:root {
  --question-list-padding: 60px;
}

.faq {
  &__container {
    display: flex;
    align-items: center;
    justify-content: center;
    min-height: 100vh;
    font-size: 14px;
    background: linear-gradient(constants.$soft-violet, constants.$soft-blue)
  }

  &__content {
    display: flex;
    margin: 20px;
    width: 800px;
    border-radius: 20px;
    background-color: white;
  }

  &__img-container,
  &__question-list {
    width: 50%;
  }

  &__img-container {
    &--desktop {
      display: block;
      background-image: url('./assets/bg-pattern-desktop.svg');
      background-repeat: no-repeat;
      background-position: top left;
      background-size: cover;
    }

    &--mobile {
      display: none;
    }
  }

  &__question-list {
    padding: var(--question-list-padding);
  }

  &__dropdown-list {
    margin: 10px 0px;
  }
}

@media screen and (max-width: 600px) {
:root {
  --question-list-padding: 40px;
}
.faq {
  &__content {
    flex-direction: column;
  }

  &__img-container,
  &__question-list {
    width: 100%;
  }

  $img-length: 250px;
  &__img-container {
    &--desktop {
      display: none;
    }

    &--mobile {
      display: flex;
      justify-content: center;
      background-image: url('./assets/bg-pattern-mobile.svg');
      background-size: $img-length;
      background-repeat: no-repeat;
      background-position: 50% 20px;
    }
  }

  &__img-person {
    width: $img-length;
    height: $img-length;
    position: relative;
    margin-top: -120px;
  }

  &__title {
    text-align: center;
  }
}
}

.attribution { font-size: 11px; text-align: center; }
.attribution a { color: hsl(228, 45%, 44%); }
</style>
