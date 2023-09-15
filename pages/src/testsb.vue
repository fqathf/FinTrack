<template>
  <ul>
    <li v-for="country in countries" :key="country.id">{{ country.name }}</li>
  </ul>
</template>
<script setup>
import { createClient } from '@supabase/supabase-js'
const supabase = createClient('https://jcbmyonvjzzpwvijfeoi.supabase.co', 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6ImpjYm15b252anp6cHd2aWpmZW9pIiwicm9sZSI6ImFub24iLCJpYXQiOjE2OTM2Mzg5OTcsImV4cCI6MjAwOTIxNDk5N30.kyA6Pq-sk3rWICHXWglD9QIT7Eb2iV9MUgjDBfyVvF0')
const countries = ref([])

async function getCountries() {
  const { data } = await supabase.from('countries').select()
  countries.value = data
}

onMounted(() => {
  getCountries()
})
</script>

