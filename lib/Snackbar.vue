<template>
  <div v-if="isVisible" class="snackbar" :class="{ focused: focused }">
    <span>{{ message }}</span>
    <button v-if="actionText" @click="handleAction">{{ actionText }}</button>
  </div>
</template>

<script>
export default {
  name: 'Snackbar',
  props: {
    message: String,
    actionText: String,
    action: Function,
    focused: Boolean,
    timeout: {
      type: Number,
      default: 4000, // Default timeout of 4 seconds
    },
  },
  data() {
    return {
      isVisible: false, // Snackbar is initially not visible
      snackbarTimeout: null, // Variable to hold timeout
    };
  },
  methods: {
    hideSnackbar() {
      this.isVisible = false; // Hide the snackbar
    },
    handleAction() {
      if (this.action) {
        this.action(); // Trigger the action passed from the parent component
      }
    },
    showSnackbar() {
      // Show snackbar and set timeout
      this.isVisible = true;
      if (this.snackbarTimeout) {
        clearTimeout(this.snackbarTimeout); // Clear existing timeouts to prevent multiple snackbars
      }
      this.snackbarTimeout = setTimeout(() => {
        this.hideSnackbar(); // Hide Snackbar after timeout
      }, this.timeout);
    },
  },
  mounted() {
    // Trigger the snackbar to show on mount
    this.showSnackbar();
  },
  beforeDestroy() {
    clearTimeout(this.snackbarTimeout); // Cleanup timeout when component is destroyed
  },
};
</script>

<style scoped>
.snackbar {
  background-color: #424242; /* Regular Snackbar - dark grey */
  color: white;
  font-size: 14px;
  font-weight: bold;
  height: 48px;
  min-width: 344px;
  max-width: 512px;
  border-radius: 4px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.25);
  position: fixed;
  bottom: 24px; /* 24px from the bottom-left corner */
  left: 24px;  /* 24px from the left */
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 12px;
  transition: background-color 0.3s ease-in-out, transform 0.3s ease, box-shadow 0.3s ease;
}

button {
  background: none;
  border: none;
  color: #81c784; /* Regular button color - Green */
  font-size: 14px;
  cursor: pointer;
  text-decoration: none; /* Underline for button text */
}

.snackbar.focused {
  /* Keeping the same background color as normal snackbar, no change */
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.25); /* Keep the original shadow */
  transform: scale(1); /* No scaling needed */
}

.snackbar.focused span {
  font-size: 14px; /* Regular text size in focused state */
  font-weight: bold;
}

.snackbar.focused button {
  color: #dc8aff; /* Text color for focused state - Purple */
  text-decoration: none; /* Remove underline in focused state */
}

.snackbar.focused button:hover {
  color: #dc8aff; /* Darker purple color on hover */
  text-decoration: underline; /* Underline button text on hover */
}
</style>
