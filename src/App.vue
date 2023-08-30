<template>
  <div>
    <ul>
      <li>{{$t('Home')}}</li>
      <li>{{$t('Service')}}</li>
      <li>{{$t('Contacts')}}</li>
      <li>{{$t('Project')}}</li>
    </ul>
  </div>
  <br>
  <span @click="switchLang">
    Переключить язык
  </span>
</template>

<script setup>
import { useI18n } from 'vue-i18n'

const { t, locale } = useI18n({ useScope: 'global' })
const switchLang = () => {
locale.value === 'en' ? locale.value = 'ru' : locale.value = 'en'
localStorage.setItem('lang', locale.value)
}
</script>
