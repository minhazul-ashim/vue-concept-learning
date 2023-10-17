<template>
  <!-- moustache template  -->
  <h1>Hello {{ name }}</h1>
  <!-- Text Binding  -->
  <h1 v-text="name"></h1>
  <!-- HTML binding  -->
  <h1 v-html="nameHtml"></h1>
  <!-- Attribute Binding, can be applicable on any attribute  -->
  <h1 v-bind:id="nameId" v-bind:dataTestId="dataId">Hello from Attribute Binding</h1>

  <!-- Class Binding in different types  -->

  <h1 v-bind:class="'base'">This is CLASS BINDING basic</h1>

  <h1 v-bind:class="['base', 'warning']">This is CLASS BINDING with arrays</h1>

  <h1 v-bind:class="[isSuccess && 'success', isDanger && 'danger', 'base']">
    This is CLASS BINDING with array expressions
  </h1>

  <h1 v-bind:class="isSuccess && 'success'">This is CLASS BINDING using logical operator</h1>

  <h1 v-bind:class="isWarning ? 'safe' : 'danger'">This is CLASS BINDING using Ternary operator</h1>

  <h1
    v-bind:class="{
      warning: isWarning,
      base: isSuccess,
      'under-lined': isSuccess
    }"
  >
    This is CLASS BINDING using objects
  </h1>

  <!-- Inline Style Binding  -->
  <h1 v-bind:style="{ color: 'red', textTransform: 'capitalize' }">This is inline style binding</h1>

  <h1 v-bind:style="{ color: textColor }">This is inline style binding</h1>

  <h1 v-bind:style="styleObj">This is inline style binding</h1>

  <h1 v-bind:style="[styleObj, anotherStyleObj]">This is inline style binding</h1>
</template>

<script lang="ts">
export default {
  name: 'App',
  data() {
    return {
      name: 'Ashim',
      nameHtml: '<i><h6>This is bolded Ashim</h6></i>',
      nameId: 'nameID',
      dataId: 'dataID',
      isWarning: true,
      isSuccess: true,
      isDanger: false,
      textColor: 'green',
      styleObj: {
        color: 'green',
        fontSize: '96px'
      },
      anotherStyleObj: {
        background: 'black',
        letterSpacing: '10px'
      }
    }
  }
}
</script>

<style scoped>
.success {
  color: green;
}

.warning {
  color: rgb(255, 166, 0);
}

.danger {
  color: red;
}

.safe {
  color: blue;
}

.base {
  padding: 8px 20px;
  border: 1px solid #e6e6e6;
  border-radius: 12px;
}

.under-lined {
  text-decoration: underline;
}
</style>
