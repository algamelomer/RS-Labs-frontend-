<template>
    <div class="relative w-full">
        <!-- Label -->
        <label v-if="label" :class="labelClass">{{ label }}</label>

        <!-- Select Input -->
        <select
            :value="modelValue"
            @change="$emit('update:modelValue', $event.target.value)"
            :class="[baseSelectClass, selectClass]"
            :aria-label="label || 'Select input'"
        >
            <option
                v-for="option in options"
                :key="option.value"
                :value="option.value"
                :disabled="option.disabled"
            >
                {{ option.label }}
            </option>
        </select>

        <!-- Caret Icon -->
        <div :class="[baseCaretClass, caretClass]">
            <slot name="caret">
                <img :src="caretIcon" class="w-3.5 h-3" alt="Caret icon" />
            </slot>
        </div>
    </div>
</template>

<script setup>
import defaultCarret from '@/assets/icons/carret.svg';

defineProps({
    modelValue: {
        type: [String, Number],
        required: true,
    },
    options: {
        type: Array,
        required: true,
        validator: (val) =>
            val.every((opt) => 'value' in opt && 'label' in opt),
    },
    label: String,
    caretIcon: {
        type: String,
        default: defaultCarret, // Use the imported variable directly
    },
    // Styling props
    baseSelectClass: {
        type: String,
        default: 'px-4 py-2 pr-8 w-full h-14 text-base bg-white border rounded-lg appearance-none',
    },
    selectClass: String,
    baseCaretClass: {
        type: String,
        default: 'absolute inset-y-0 right-0 flex items-center px-4 pointer-events-none',
    },
    caretClass: String,
    labelClass: String,
});

defineEmits(['update:modelValue']);
</script>