<template>
  <div class="wrapper">
    amazing web component
    <pre class="pre">
      your name is {{ name }}
    </pre>
    <hr />
    <slot></slot>
    <hr />
    {{ adate }}
    <hr />
    <button>say my name</button>
  </div>
</template>

<script>
import { formatDistance, subDays } from "date-fns";
export default {
  name: "wc-displayname",
  props: ["name"],
  data() {
    return {
      adate: formatDistance(subDays(new Date(), 3), new Date(), {
        addSuffix: true,
      }),
    };
  },
};
</script>

<style>
:host .wrapper {
  border: 5px solid blue;
}
button {
  background: red;
}
</style>
