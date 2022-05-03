<template>
  <div>
    <label for="locale-select">{{ $t("locale") }}</label>
    <select v-model="locale" id="locale-select" @change="setLocale" required>
      <option :selected="locale === 'en'" value="en">English</option>
      <option :selected="locale === 'es'" value="es">Español</option>
      <option :selected="locale === 'pt'" value="pt">Portuguese</option>
    </select>
  </div>
</template>

<script>
export default {
  name: "LocaleSelect",
  data() {
    return {
      locale: "",
    };
  },
  computed: {
    navigatorLocale() {
      return navigator.language.slice(0, 2);
    },
  },
  mounted() {
    const storedLocale = localStorage.getItem("locale");

    if (storedLocale) {
      this.locale = storedLocale;
    } else {
      this.locale = this.navigatorLocale;
    }

    this.setLocale();
  },
  methods: {
    setLocale() {
      this.$root.$i18n.locale = this.locale;
      localStorage.setItem("locale", this.locale);
    },
  },
};
</script>

<i18n>
{
	"en": {
		"locale": "language"
	},
	"es": {
		"locale": "lenguaje"
	},
	"pt": {
		"locale": "Língua"
	}
}
</i18n>
