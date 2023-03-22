<script lang='ts' setup>
import { defineProps } from 'vue';

const props = defineProps<{
    label: string,
    variant?: string,
    startIcon?: string,
    endIcon?: string,
    size?: string,
    color?: string,
    disableShadow?: boolean,
    disabled?: boolean,
    icon?: boolean
}>();

const getIcon = (src: string) => {
    return new URL(`./icons/${src}.svg`, import.meta.url).href;
};

class Button {
    data(): { label: string, variant: string, size: string, color: string, disableShadow: boolean, disabled: boolean, icon: boolean} {
        return {
            label: props.label,
            variant: 'variant--' + (props.variant || 'default'),
            size: 'size--' + (props.size || 'md'),
            color: 'color--' + (props.color || ''),
            disableShadow: props.disableShadow,
            disabled: props.disabled,
            icon: props.endIcon != undefined || props.startIcon != undefined,
        }
    }
}

const myButton = new Button();
const myData = myButton.data();

</script>

<template>
    <button
        class="my-button" 
        :class="[ 
            myData.size,
            myData.variant,
            myData.color,
            { 'disable-shadow': myData.disableShadow },
            { 'disabled': myData.disabled },
            { 'icon': myData.icon }
        ]"
        :disabled="myData.disabled"
    >
        <img v-if="startIcon" :src="getIcon(startIcon)" class="left-icon">
        {{ label }}
        <img v-if="endIcon" :src="getIcon(endIcon)" class="right-icon">
    </button>
</template>

<style scoped lang="scss">
.my-button {
    display: flex;
    cursor: pointer;
    border-radius: 6px;
    border: none;
    font-family: 'Noto Sans JP', sans-serif;
    font-weight: 500;
}
.variant {
    &--default {
        background-color: #E0E0E0;
        color: #000000;
        &:hover, &:focus {
            background-color: #AEAEAE;
        }
    }

    &--outline {
        background-color: transparent;
        color: #3D5AFE;
        border: 1px solid #3D5AFE;
        &:hover, &:focus {
            background: #2962FF1A;
        }
    }

    &--text {
        background-color: transparent;
        border: none;
        color: #3D5AFE;
        &:hover, &:focus {
            background: #2962FF1A;
        }
    }
}

.disable-shadow {
    box-shadow: none;
    background-color: #3D5AFE;
    color: white;
    &:hover, &:focus {
        background-color: #3D5AFE;
    }
}

.disabled {
    color: #9E9E9E;
    cursor: default;
    &:hover, &:focus {
        background-color: transparent;
    }
}

.size {
    &--sm {
        padding: 6px 12px;
    }
    &--md {
        padding: 8px 16px;
    }
    &--lg {
        padding: 11px 22px;
    }
}

.color {
    &--default {
        background-color: #E0E0E0;
        color: #000000;
        &:hover, &:focus {
            background-color: #AEAEAE;
        }
    }
    &--primary {
        background-color: #3D5AFE;
        color: white;
        &:hover, &:focus {
            background-color: #0039CB;
        }
    }
    &--secondary {
        background-color: #455A64;;
        color: white;
        &:hover, &:focus {
            background-color: #1C313A;
        }
    }
    &--danger {
        background-color: #D32F2F;
        color: white;
        &:hover, &:focus {
            background-color: #9A0007;
        }
    }
}

.icon {
    color: white;
    background-color: #3D5AFE;
    &:hover, &:focus {
        background-color: #3D5AFE;
    }
}

.left-icon {
    margin-right: 8px;
    height: 16px;
}

.right-icon {
    margin-left: 8px;
    height: 16px;
}
</style>