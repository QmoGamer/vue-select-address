<template>
	<select class="form-control" v-model="selectedIndex" @change="selected">
		<option v-for="(item, index) in options"
					 :value="index"
				   :key="index">{{item.name}}</option>
	</select>
</template>

<script>
export default {
  name: 'MySelect',
  props: [
		'options',
		'value'
  ],
  data() {
	  return {
		  selectedIndex: this.value
	  }
	},
	methods: {
		selected() {
      this.$emit('selected', this.selectedIndex)
    }
	},
	watch: {
		options: function () {
      this.selectedIndex = 0
    }
	}
}
</script>