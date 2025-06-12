<script setup>
defineProps({
  text: {
    type: String,
    required: true
  },
  href: {
    type: String,
    default: '#'
  },
  variant: {
    type: String,
    default: 'primary',
    validator: (value) => ['primary', 'secondary', 'outline'].includes(value)
  },
  size: {
    type: String,
    default: 'medium',
    validator: (value) => ['small', 'medium', 'large'].includes(value)
  },
  disabled: {
    type: Boolean,
    default: false
  },
  ariaLabel: {
    type: String,
    default: ''
  }
});
</script>

<template>
  <a :href="disabled ? undefined : href" class="button" :class="[
    `button--${variant}`,
    `button--${size}`,
    { 'button--disabled': disabled }
  ]" :aria-disabled="disabled" :aria-label="ariaLabel || text" :tabindex="disabled ? -1 : 0" role="button">
    {{ text }}
  </a>
</template>

<style scoped>
.button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  color: var(--color-text-light, #ffffff);
  border: none;
  border-radius: 2rem;
  font-weight: 700;
  cursor: pointer;
  text-decoration: none;
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
  text-align: center;
  white-space: nowrap;
}

/* Variants */
.button--primary {
  background-color: var(--color-purple);
}

.button--primary:hover:not(.button--disabled) {
  background-color: var(--color-purple-hover);
  transform: translateY(-1px);
}

.button--secondary {
  background-color: var(--color-purple-dark);
}

.button--secondary:hover:not(.button--disabled) {
  background-color: var(--color-purple-darker);
  transform: translateY(-1px);
}

.button--outline {
  background-color: transparent;
  border: 2px solid var(--color-purple);
  color: var(--color-purple);
}

.button--outline:hover:not(.button--disabled) {
  background-color: var(--color-purple);
  color: var(--color-text-light);
  transform: translateY(-1px);
}

/* Sizes */
.button--small {
  padding: 0.5rem 1.5rem;
  font-size: 0.875rem;
}

.button--medium {
  padding: 1rem 2.5rem;
  font-size: 1rem;
}

.button--large {
  padding: 1rem 2.5rem;
  font-size: 1.125rem;
}

/* States */
.button--disabled {
  opacity: 0.6;
  cursor: not-allowed;
  pointer-events: none;
}

/* Focus styles */
.button:focus-visible {
  outline: 2px solid var(--color-purple);
  outline-offset: 2px;
}

/* Active state */
.button:active:not(.button--disabled) {
  transform: translateY(1px);
}

/* Loading state */
.button--loading {
  cursor: wait;
}

.button--loading::after {
  content: '';
  position: absolute;
  width: 1rem;
  height: 1rem;
  border: 2px solid currentColor;
  border-radius: 50%;
  border-right-color: transparent;
  animation: button-loading 0.75s linear infinite;
}

@keyframes button-loading {
  from {
    transform: rotate(0deg);
  }

  to {
    transform: rotate(360deg);
  }
}

/* Responsive adjustments */
@media (max-width: 768px) {
  .button--medium {
    padding: 0.875rem 2rem;
  }

  .button--large {
    padding: 1rem 2.5rem;
  }
}

@media (max-width: 480px) {
  .button {
    width: 100%;
  }

  .button--medium {
    padding: 0.75rem 1.5rem;
  }
}
</style>