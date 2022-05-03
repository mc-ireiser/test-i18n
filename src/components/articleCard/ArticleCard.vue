<template>
  <div>
    <article>
      <hgroup>
        <h1>{{ $t("title") }}</h1>
        <h2>{{ $t("subtitle") }}</h2>
      </hgroup>
      <p>
        <span>
          {{ $t("paragraph") }}
        </span>
        <i18n path="readMore_composeLink" tag="span">
          <template v-slot:readMoreLinkSlot>
            <a :href="aboutJavaScriptUrl" target="_blank">{{
              $t("readMore")
            }}</a>
          </template>
        </i18n>
      </p>
      <p>
        <a :href="sourceUrl" target="_blank">{{ $t("source") }}</a>
      </p>
    </article>
    <LocaleSelector />
  </div>
</template>

<script>
import LocaleSelector from "@/components/localeSelect/LocaleSelect.vue";
export default {
  name: "ArticleCard",
  components: {
    LocaleSelector,
  },
  computed: {
    locale() {
      return this.$root.$i18n.locale;
    },
    sourceBaseUrl() {
      return `https://developer.mozilla.org/${this.locale}/docs/Web`;
    },
    sourceUrl() {
      return `${this.sourceBaseUrl}/JavaScript`;
    },
    aboutJavaScriptUrl() {
      return `${this.sourceBaseUrl}/JavaScript/About_JavaScript`;
    },
  },
};
</script>

<i18n>
{
	"en": {
		"paragraph": "JavaScript (JS) is a lightweight, interpreted, or just-in-time compiled programming language with first-class functions. While it is most well-known as the scripting language for Web pages, many non-browser environments also use it, such as Node.js, Apache CouchDB and Adobe Acrobat. JavaScript is a prototype-based, multi-paradigm, single-threaded, dynamic language, supporting object-oriented, imperative, and declarative (e.g. functional programming) styles.",
		"readMore": "Read more",
		"readMore_composeLink": "{readMoreLinkSlot} about JavaScript.",
		"source": "Source",
		"subtitle": "Not to be confused with Java (programming language)",
		"title": "JavaScript"
	},
	"es": {
		"paragraph": "JavaScript (JS) es un lenguaje de programación ligero, interpretado, o compilado justo-a-tiempo (just-in-time) con funciones de primera clase. Si bien es más conocido como un lenguaje de scripting (secuencias de comandos) para páginas web, y es usado en muchos entornos fuera del navegador, tal como Node.js, Apache CouchDB y Adobe Acrobat JavaScript es un lenguaje de programación basada en prototipos, multiparadigma, de un solo hilo, dinámico, con soporte para programación orientada a objetos, imperativa y declarativa (por ejemplo programación funcional).",
		"readMore": "Lee más",
		"readMore_composeLink": "{readMoreLinkSlot} en acerca de JavaScript.",
		"source": "Fuente",
		"subtitle": "No debe confundirse con Java.",
		"title": "JavaScript"
	},
	"pt": {
		"paragraph": "JavaScript® (às vezes abreviado para JS) é uma linguagem leve, interpretada e baseada em objetos com funções de primeira classe, mais conhecida como a linguagem de script para páginas Web, mas usada também em vários outros ambientes sem browser, tais como node.js,  Apache CouchDB e Adobe Acrobat. O JavaScript é uma linguagem baseada em protótipos, multi-paradigma e dinâmica, suportando estilos de orientação a objetos, imperativos e declarativos (como por exemplo a programação funcional).",
		"readMore": "Saiba mais",
		"readMore_composeLink": "{readMoreLinkSlot} sobre o JavaScript.",
		"source": "origem",
		"subtitle": "Nota: Não confundir com Java (linguagem de programação)",
		"title": "JavaScript"
	}
}
</i18n>
