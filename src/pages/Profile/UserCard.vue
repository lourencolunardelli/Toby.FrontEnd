<template>
  <card type="user">
    <p class="card-text">
    </p>
    <div class="author">
      <div> <base-button slot="footer" type="success" fill>Enviar booking</base-button>
      </div>
      <div> <base-button slot="footer" type="warning" fill>Solicitação de reserva</base-button>
      </div>
      <div> <base-button slot="footer" type="primary" fill>Envio se draft (SI)</base-button>
      </div>
      <div> <base-button slot="footer" type="default" fill>Confirmação de embarque</base-button>
      </div>
      <div>
        <base-button slot="footer" type="primary" fill>Validate Master BL</base-button>
      </div>
      <!-- <div class="block block-one"></div>
      <div class="block block-two"></div>
      <div class="block block-three"></div>
      <div class="block block-four"></div> -->
      <!-- <a href="#">
        <img class="avatar" src="img/anime6.png" alt="...">
        <h5 class="title">{{user.fullName}}</h5>
      </a>
      <p class="description">
        {{user.title}}
      </p> -->
    </div>
    <p></p>
    <!-- <p class="card-description">
      {{user.description}}
    </p> -->
    <!-- <div slot="footer" class="button-container">
      <base-button icon round class="btn-facebook">
        <i class="fab fa-facebook"></i>
      </base-button>
      <base-button icon round class="btn-twitter">
        <i class="fab fa-twitter"></i>
      </base-button>
      <base-button icon round class="btn-google">
        <i class="fab fa-google-plus"></i>
      </base-button>
    </div> -->
  </card>
</template>
<script>
export default {
  props: {
    user: {
      type: Object,
      default: () => {
        return {};
      }
    }
  }
}
</script>
<style></style>
