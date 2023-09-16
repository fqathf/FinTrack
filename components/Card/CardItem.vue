<template>
  <tr>
    <td v-for="item in inputanForm" :key="item">
      {{ form.desc }}
    </td>
    <td v-for="item in inputanForm" :key="item">
      {{ form.amount }}
    </td>
    <td v-for="item in inputanForm" :key="item">
      {{ form.tc_type }}
    </td>
    <td v-for="item in inputanForm" :key="item">
      {{ form.date }}
    </td>
  </tr>
</template>
<script>
export default {
    props: {
        form: {
            type: Object,
            default: 'Untitled',
        },
    },
}
</script>
