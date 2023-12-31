<template>
  <div class="wrapper">
    <label :for="idLabel">{{ labelName }}</label>
    <input
      type="text"
      :id="idLabel"
      :placeholder="placeholderInput"
      :disabled="disabledInput"
      :value="initialValue"
      v-if="!withIcon && !isMultiline"
    />
    <textarea
      :id="idLabel"
      :placeholder="placeholderInput"
      :disabled="disabledInput"
      :value="initialValue"
      v-if="isMultiline"
      cols="30"
      rows="4"
    ></textarea>

    <div v-if="withIcon" class="wrapper-icon" :class="withIcon ? withIcon.place : ''">
      <input
        type="text"
        :id="idLabel"
        :placeholder="placeholderInput"
        :disabled="disabledInput"
        :value="initialValue"
      />
      <i>{{ withIcon.icon }}</i>
    </div>

    <span v-if="helperText" class="helper-text">{{ helperText }}</span>
  </div>
</template>

<script>
import { toRefs } from "vue";
export default {
  name: "Input",
  props: {
    labelName: {
      type: String,
      required: true,
    },
    placeholderInput: {
      type: String,
      required: false,
    },
    disabledInput: {
      type: Boolean,
      required: false,
    },
    helperText: {
      type: String,
      required: false,
    },
    withIcon: {
      type: Object,
      required: false,
    },
    initialValue: {
      type: String,
      required: false,
    },
    isMultiline: {
      type: Boolean,
      required: false,
    },
  },
  setup(props) {
    const { labelName } = toRefs(props);

    const dateNow = Date.now() + Math.floor(Math.random() * 900);
    const idLabel = dateNow + labelName.value;

    return {
      idLabel,
    };
  },
};
</script>

<style scoped>
.wrapper {
  display: flex;
  flex-direction: column;
  row-gap: 1vh;
}

label {
  font: 400 12px "Noto Sans JP", sans-serif;
  cursor: pointer;
}

input {
  font: 400 14px "Noto Sans JP", sans-serif;
  border-radius: 8px;
  border: 1px solid var(--InputBorder);
  width: 200px;
  height: 56px;
  padding: 1rem;
}

span.helper-text {
  font: 400 10px "Noto Sans JP", sans-serif;
}

textarea:hover,
input:hover,
.on-hover input {
  border: 1px solid #333333;
  outline: 1px solid #333333;
}

textarea:focus,
input:focus,
.on-focus input {
  border: 1px solid #2962ff;
  outline: none;
}

.error label,
.error .helper-text,
.error:focus {
  color: var(--InputErrorBorder);
}

.error input,
.error:focus {
  border: 1px solid var(--InputErrorBorder);
  outline: none;
}

.error:hover label,
.error:hover .helper-text,
.error.on-hover label {
  color: var(--InputBorder);
}

.error:hover input,
.error.on-hover input {
  border: 1px solid var(--InputBorder);
}

input:disabled,
input:disabled:hover {
  border: 1px solid #e0e0e0;
  outline: none;
}

.wrapper-icon {
  position: relative;
  width: 100%;
}

.wrapper-icon input {
  width: 100%;
  padding: 5% 15%;
  border-radius: 12px;
}

.wrapper-icon i {
  position: absolute;
  font-style: normal;
}

.wrapper-icon.start-icon i {
  right: 88%;
  top: 30%;
}

.wrapper-icon.end-icon i {
  left: 88%;
  top: 30%;
}

.s-sm input {
  height: 40px;
}

.s-md input {
  height: 56px;
}

.fullWidth input {
  width: 100%;
}

textarea {
    font: 400 14px "Noto Sans JP", sans-serif;
    border-radius: 8px;
    border: 1px solid var(--InputBorder);
    padding: 1rem;
    resize: none;
}
</style>