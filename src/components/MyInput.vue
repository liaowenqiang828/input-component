<template>
  <div>
    <label for="my-input" :class="['label', 
    `${error}` === 'true' && 'error_label',
    ]">Label</label>
    <input
      id="my-input" 
      placeholder="Placeholder"
      :class="[
      'my-input',
      `${error}` === 'true' && 'my-input-error',
      `${disabled}` === 'true' && 'my-input-disabled',
      ]"
      :disabled="disabled"
      />
      <PhoneOutlined v-if="startIcon" />
      <LockFilled v-if="endIcon" />
    <span v-if="helpText"
      :class="[
        'help-text',
        `${error}` === 'true' && 'help-text-error',
      ]"
      >{{helpText}}</span>
  </div>
</template>

<script>
import LockFilled from '@ant-design/icons-vue/LockFilled'
import PhoneOutlined from '@ant-design/icons-vue/PhoneOutlined'
export default {
  name: "MyInput",
  components: {
    LockFilled,
    PhoneOutlined,
  },
  props: {
    error: Boolean,
    disabled: Boolean,
    helpText: String,
    startIcon: Boolean,
    endIcon: Boolean,
  },
  setup(props) {
    console.log("props", props)
    return {
    }
  }
}
</script>

<style lang=less scoped>
@import '../style/variable.less';

.label {
  display: block;
}

.error_label {
  color: @error_color;
}

.my-input {
  width: 200px;
  height: 30px;
  border-radius: 5px;
  border: 1px solid @theme_gray;
  padding: 5px;
  outline: none;

  &:hover {
    border-color: @hover_gray;
  } 

  &:focus {
    border-color: @theme_blue;
  }
}

.my-input-error {
  border-color: @error_color;

  &:hover {
    border-color: @hover_gray;
  }

  &:focus {
    border-color: @error_color;
  }
}

.my-input-disabled {
  background-color: @bg_color;

  &:hover, &focus {
    cursor: not-allowed;
    pointer-events: all!important;
  }
}

.help-text {
  display: block;
  color: @theme_light_gray;
}

.help-text-error {
  color: @error_color;
}

</style>