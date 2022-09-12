<script>
export default {
  name: "MyButton",
  props: {
    type: {
      type: String,
      default: "button",
    },
    variant: {
      type: String,
      default: "Default",
    },
    isDisabled: {
      type: Boolean,
      default: false,
    },
    size: {
      type: String,
      default: "sm",
    },
    color: {
      type: String,
      default: "",
    },
    iconPosition: {
      type: String,
      default: "start",
    },
    isShadow: {
      type: Boolean,
      default: true,
    },
    startIcon: {
      type: String,
      default: "",
    },
    endIcon: {
      type: String,
      default: "",
    },
  },
  computed: {
    getVariantClassName() {
      let className = "";
      switch (this.variant) {
        case "outline":
          return (className = "outline");
          break;
        case "text":
          return (className = "btn-text");
          break;
        default:
          break;
      }
      return className;
    },
    getSizeClassName() {
      let className = "";
      switch (this.size) {
        case "md":
          return (className = "medium");
          break;
        case "lg":
          return (className = "large");
          break;
        default:
          break;
      }
      return className;
    },
  },
};
</script>

<template>
  <button
    :type="type"
    :class="[
      getVariantClassName,
      getSizeClassName,
      `${color}`,
      isShadow === false ? 'not-shadow' : '',
    ]"
    :disabled="isDisabled"
  >
    <span
      v-if="startIcon !== ''"
      class="material-symbols-outlined"
    >
      {{ startIcon }}
    </span>
    <slot name="text">Default</slot>
    <span
      v-if="endIcon !== ''"
      class="material-symbols-outlined"
    >
      {{ endIcon }}
    </span>
  </button>
</template>

<style lang="scss">
button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  gap: 8px;
  border: 1px solid transparent;
  padding: 0.42rem 0.86rem;
  font-size: 1rem;
  font-weight: 500;
  font-family: inherit;
  cursor: pointer;
  background: #e0e0e0;
  box-shadow: 0px 2px 3px rgba(51, 51, 51, 0.2);
  border-radius: 6px;
}
.medium {
  padding: 0.57rem 1.142rem;
}
.large {
  padding: 0.786rem 1.57rem;
}

button:hover:not(:disabled) {
  background-color: #aeaeae;
}
button:focus:not(:disabled),
button:focus-visible:not(:disabled) {
  outline: 4px auto -webkit-focus-ring-color;
}
button:disabled {
  box-shadow: none;
  color: #9e9e9e;
  &:hover {
    cursor: not-allowed;
  }
}
@media (prefers-color-scheme: light) {
  button {
    background-color: #f9f9f9;
  }
}
.outline {
  border-color: var(--primary-color);
  color: var(--primary-color);
  background-color: #fff;
  box-shadow: none;
}
.outline:hover:not(:disabled) {
  background-color: rgba(41, 98, 255, 0.1);
}
.outline:focus:not(:disabled),
.outline:focus-visible:not(:disabled) {
  outline: 4px auto -webkit-focus-ring-color;
}
.btn-text {
  border-color: transparent;
  color: var(--primary-color);
  background-color: #fff;
  box-shadow: none;
}
.btn-text:hover:not(:disabled) {
  background-color: rgba(41, 98, 255, 0.1);
}
.btn-text:focus:not(:disabled),
.btn-text:focus-visible:not(:disabled) {
  outline: 4px auto -webkit-focus-ring-color;
}
.primary {
  color: #fff;
  background: #2962ff;
  box-shadow: 0px 2px 3px rgba(41, 98, 255, 0.2);
  &:hover:not(:disabled) {
    background-color: #0039cb;
  }
}
.secondary {
  color: #fff;
  background: #455a64;
  box-shadow: 0px 2px 3px rgba(69, 90, 100, 0.2);
  &:hover:not(:disabled) {
    background-color: #1c313a;
  }
}
.danger {
  color: #fff;
  background: #d32f2f;
  box-shadow: 0px 2px 3px rgba(211, 47, 47, 0.2);
  &:hover:not(:disabled) {
    background-color: #9a0007;
  }
}
.not-shadow {
  box-shadow: none;
}
</style>
