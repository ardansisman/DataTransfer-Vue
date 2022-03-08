<template>
  <li class="list-group-item">
    Sunucu #{{ serverData.id }}
    <p>Durumu : {{ serverData.status }}</p>
  </li>
</template>
<script>
export default {
  props: ["serverData"],
};
</script>