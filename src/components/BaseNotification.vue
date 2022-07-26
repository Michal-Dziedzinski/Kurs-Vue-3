<template>
  <div class="notification" :class="{ 'notification--hidden': !isVisible }">
    <div class="notification__icon">
      <svg viewBox="0 0 24 24" preserveAspectRatio="none">
        <path
          d="M12 2.4A9.588 9.588 0 002.4 12c0 5.311 4.288 9.6 9.6 9.6 5.311 0 9.6-4.289 9.6-9.6 0-5.312-4.289-9.6-9.6-9.6zm1.515 14.933c0 .47-.405.875-.875.875h-1.323a.893.893 0 01-.875-.875v-5.59c0-.49.405-.874.875-.874h1.323c.469 0 .875.405.875.875v5.59zm-1.537-7.915c-.982 0-1.792-.81-1.792-1.813s.811-1.814 1.792-1.814c1.003 0 1.813.811 1.813 1.814 0 1.003-.81 1.813-1.813 1.813z"
        ></path>
      </svg>
    </div>
    <span v-if="message" class="notification__message">{{ message }}</span>
    <button class="notification__close" @click="hideNotification">
      <div>
        <svg viewBox="0 0 24 24" preserveAspectRatio="none">
          <path
            d="M21.261 2.22a.748.748 0 00-1.057 0l-8.464 8.463-8.463-8.464a.748.748 0 10-1.058 1.058l8.464 8.463-8.464 8.464a.748.748 0 101.058 1.057l8.463-8.463 8.464 8.463a.748.748 0 101.057-1.057l-8.463-8.464 8.463-8.463a.748.748 0 000-1.058z"
          ></path>
        </svg>
      </div>
    </button>
  </div>
</template>

<script>
export default {
  name: 'BaseNotification',
  props: {
    message: {
      type: String,
      default: '',
    },
    isVisible: {
      type: Boolean,
      default: false,
    },
  },
  emits: ['hide-notification'],
  setup(_, { emit }) {
    const hideNotification = () => {
      emit('hide-notification');
    };
    return {
      hideNotification,
    };
  },
};
</script>

<style lang="scss" scoped>
.notification {
  position: fixed;
  display: flex;
  align-items: center;
  box-sizing: border-box;
  width: 100%;
  padding: 16px 8px;
  box-shadow: 0 4px 11px rgba(#1d1f22, 0.1);
  border-radius: 5px;
  background: #0468db;
  color: #fff;
  bottom: 0;
  right: 0;
  transition: transform 0.3s ease-in;
  &__close {
    background-color: transparent;
    border-width: 0;
    cursor: pointer;
    margin-left: auto;
    width: 0.85rem;
    height: 0.85rem;
    outline: none;
    svg {
      fill: #fff;
      width: 0.85rem;
      height: 0.85rem;
    }
  }
  &__message {
    font-size: 18px;
  }
  &__icon {
    margin: 0 24px 0 0;
    svg {
      fill: #fff;
      width: 2rem;
      height: 2rem;
    }
  }
  &--hidden {
    transform: translateY(68px);
  }
}
</style>
