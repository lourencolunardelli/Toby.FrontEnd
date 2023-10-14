<!-- eslint-disable vue/no-mutating-props -->
<template>
  <card>
    <h5 slot="header" class="title">HOUSE BL</h5>
    <div class="row">
      <div class="col-md-2 pr-md-1">
        <base-input label="Number" placeholder="Number" v-model="model.number" disabled>
        </base-input>
      </div>
    </div>
    <div class="row">
      <div class="col-md-4 pr-md-1">
        <base-input label="Consignee"  placeholder="Consignee" v-model="model.consignee">
        </base-input>
      </div>
      <div class="col-md-4 px-md-1">
        <base-input label="Shipper" placeholder="Shipper" v-model="model.shipper">
        </base-input>
      </div>
      <div class="col-md-4 pl-md-1">
        <base-input label="Email address" type="email" placeholder="mike@email.com">
        </base-input>
      </div>
      <div class="col-md-6 pl-md-1">
        <base-input label="Last Name" v-model="model.loadingport" placeholder="Last Name">
        </base-input>
      </div>
    </div>
    <div class="row">
      <div class="col-md-12">
        <base-input label="Address" v-model="model.delivery" placeholder="Home Address">
        </base-input>
      </div>
    </div>
    <div class="row">
      <div class="col-md-4 pr-md-1">
        <base-input label="City" v-model="model.city" placeholder="City">
        </base-input>
      </div>
      <div class="col-md-4 px-md-1">
        <base-input label="Country" v-model="model.country" placeholder="Country">
        </base-input>
      </div>
      <div class="col-md-4 pl-md-1">
        <base-input label="Postal Code" placeholder="ZIP Code"> </base-input>
      </div>
    </div>
    <div class="row">
      <div class="col-md-8">
        <base-input>
          <label>About Me</label>
          <textarea rows="4" cols="80" class="form-control" placeholder="Here can be your description"
            v-model="model.about">
          </textarea>
        </base-input>
      </div>
    </div>
    <base-button slot="footer" type="primary" fill>Save</base-button>
  </card>
</template>
<script>
export default {
  created() {
    // Fazer algo com o objeto recuperado, por exemplo, atribuí-lo a uma variável de dados
    this.model = this.$route.params.item;
    console.log(this.model);
  },
  props: {
    model: {
      type: Object,
      default: () => {
        return {};
      }
    }
  }
};
</script>
<style></style>
