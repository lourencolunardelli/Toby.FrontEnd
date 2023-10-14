<template>
  <div class="row">
    <div class="col-12">
      <card :title="table1.title">
        <div class="table-responsive">
          <base-table
            :data="table1.data"
            :columns="table1.columns"
            thead-classes="text-primary"
            @verDetalhes="verDetalhes"
          >
          </base-table>
        </div>
      </card>
    </div>
  </div>
</template>
<script>
import { BaseTable } from "@/components";
const tableColumns = ["Number", "Shipper", "Consignee", "loadingport", "delivery"];
const tableData = [
  {
    id: 1,
    number: "HEAD23C00185",
    shipper: "Dakota Rice",
    consignee: "Isabelle Frederica",
    loadingport: "Niger",
    delivery: "Oud-Turnhout",
  },
  {
    id: 2,
    number: "HEAD23C00122",
    shipper: "Minerva Hooper",
    consignee: "Sandhya Hamida",
    loadingport: "Curaçao",
    delivery: "Sinaai-Waas",
  },
  {
    id: 3,
    number: "HEAD23C00146",
    shipper: "Sage Rodriguez",
    consignee: "Ifa Acke",
    loadingport: "Netherlands",
    delivery: "Baileux",
  },
  {
    id: 4,
    number: "HEAD23C00174",
    shipper: "Philip Chaney",
    consignee: "Lileas Sakke",
    loadingport: "Korea, South",
    delivery: "Overland Park",
  },
  {
    id: 5,
    number: "HEAD23C00386",
    shipper: "Doris Greene",
    consignee: "Gnaeus Borivoj",
    loadingport: "Malawi",
    delivery: "Feldkirchen in Kärnten",
  },
  {
    id: 6,
    number: "HEAD23C00907",
    shipper: "Mason Porter",
    consignee: "Isa Cory",
    loadingport: "Chile",
    delivery: "Gloucester",
  },
  {
    id: 7,
    number: "HEAD23C00560",
    shipper: "Jon Porter",
    consignee: "Nikodemos Emilis",
    loadingport: "Portugal",
    delivery: "Gloucester",
  },
];
import router from '../../router/routes'; // Certifique-se de que o caminho está correto

export default {
  components: {
    BaseTable,
  },
  data() {
    return {
      table1: {
        title: "Bills of Lading",
        columns: [...tableColumns],
        data: [...tableData],
      },
    };
  },
  methods: {
    verDetalhes(item) {
      // Navega para a rota 'BillOfLadingDetails' com o ID do item como parâmetro
      this.$router.push({ name: "house details", params: { item } });
    },
  },
};
</script>
<style></style>
