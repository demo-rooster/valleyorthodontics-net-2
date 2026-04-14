<template lang="pug" src="./index.pug" ></template>

<script>
import FormFlexible from '~/components/form/form-flexible'

export default {
  components: {
    FormFlexible
  },
  props: {
    props: {
      type: Object,
      default: () => ({})
    }
  },
  computed: {
    selectedForm () {
      const forms = Array.isArray(this.$store.state.forms) ? this.$store.state.forms : []
      const selectedFormId = Array.isArray(this.props.form) ? this.props.form[0] : this.props.form

      if (selectedFormId === undefined || selectedFormId === null) {
        return null
      }

      return forms.find(form => form.id.toString() === selectedFormId.toString()) || null
    }
  }
}
</script>

<style lang="sass" src="./index.sass"></style>
