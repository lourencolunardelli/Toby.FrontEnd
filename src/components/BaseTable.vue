<template>
  <table class="table tablesorter" :class="tableClass">
    <thead :class="theadClasses">
      <tr>
        <slot name="columns">
          <th v-for="column in columns" :key="column">{{ column }}</th>
        </slot>
      </tr>
    </thead>
    <tbody :class="tbodyClasses">
      <tr v-for="(item, index) in data" :key="index">
        <slot :row="item">
          <td v-for="(column, index) in columns" :key="index" v-if="hasValue(item, column)">
            {{ itemValue(item, column) }}
          </td>

          <td>
            <button @click="verDetalhes(item)"> <!-- Adicione um evento de clique para chamar o método verDetalhes -->
              <i class="fas fa-eye"></i> <!-- Ícone de olho (você pode usar qualquer ícone de olho que preferir) -->
            </button>
          </td>
        </slot>
      </tr>
    </tbody>
  </table>
</template>
<script>
export default {
  name: 'base-table',
  props: {
    columns: {
      type: Array,
      default: () => [],
      description: "Table columns"
    },
    data: {
      type: Array,
      default: () => [],
      description: "Table data"
    },
    type: {
      type: String, // striped | hover
      default: "",
      description: "Whether table is striped or hover type"
    },
    theadClasses: {
      type: String,
      default: '',
      description: "<thead> css classes"
    },
    tbodyClasses: {
      type: String,
      default: '',
      description: "<tbody> css classes"
    }
  },
  computed: {
    tableClass() {
      return this.type && `table-${this.type}`;
    }
  },
  methods: {
    hasValue(item, column) {
      return item[column.toLowerCase()] !== "undefined";
    },
    itemValue(item, column) {
      return item[column.toLowerCase()];
    },
    verDetalhes(item) {
      this.$emit('verDetalhes', item); // Emitindo um evento personalizado com o item como argumento
    }
  }
};
</script>
<style></style>
