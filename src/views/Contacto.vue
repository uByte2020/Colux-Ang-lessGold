<template>
  <div id="Contactos">
    <NavbarPrinc />
    <div class="container-fluid">
      <div class="row">
        <TitleBar title="CONTACTOS" pageClass="contacto-page"></TitleBar>
        <div class="col-12" id="Formulario">
          <div class="row">
            <div class="col-lg-6 col-xl-6 col-sm-12 col-md-6">
              <form action="/#" method="get">
                <div class="row">
                  <div class="col-lg-6 col-xl-6 col-md-6 col-sm-12">
                    <div class="form-group">
                      <label for="Nome">Nome</label>
                      <input
                        type="text"
                        class="form-control"
                        name="Nome"
                        v-model="nome"
                        required
                      />
                    </div>
                  </div>
                  <div class="col-lg-6 col-xl-6 col-md-6 col-sm-12">
                    <div class="form-group">
                      <label for="email">E-mail</label>
                      <input
                        type="email"
                        name="email"
                        class="form-control"
                        v-model="email"
                        required
                      />
                    </div>
                  </div>
                  <div class="col-12">
                    <div class="form-group">
                      <label for="Telefone">Telefone</label>
                      <input
                        type="tel"
                        name="Telefone"
                        class="form-control"
                        v-model="telefone"
                        required
                      />
                    </div>
                  </div>
                  <div class="col-12">
                    <div class="form-group">
                      <label for="Mensagem">Mensagem</label>
                      <textarea
                        name="Mensagem"
                        class="form-control"
                        v-model="mensagem"
                      />
                    </div>
                  </div>
                  <div class="col-lg-12 col-xl-6 col-sm-12 col-md-12">
                    <button
                      type="button"
                      class="btn btn-default btn-lg btn-block"
                      @click="sendformulario"
                    >
                      ENVIAR MENSAGEM
                    </button>
                  </div>
                </div>
              </form>
            </div>
            <div class="col-lg-6 col-xl-6 col-sm-12 col-md-6">
              <div class="row">
                <div class="col-12 AngLess">
                  <h2 class="AngLessTitulo">ANG LESS GOLD</h2>
                </div>
                <div
                  class="col-12 Texto"
                >
                  <p class="texto-ang-less">Estrada da Mendanha</p>
                  <p class="texto-ang-less">Nº 25 Bloco 4 - 4 C</p>
                  <p class="texto-ang-less">Parque norte</p>
                  <p class="texto-ang-less">2580-588 Carregado</p>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="col-12">
          <h3 class="Localizacao">Localização</h3>
          <div class="row">
            <div class="col-11 mapa">
              <googleMap />
            </div>
          </div>
        </div>
        <Footer />
      </div>
    </div>
  </div>
</template>

<script>
import Footer from "../components/Footer.vue";
import NavbarPrinc from "../components/NavbarPrinc.vue";
import googleMap from "../components/Contacto/Map.vue";
import TitleBar from "../components/TitleBar";
export default {
  name: "Contacto",
  components: {
    Footer,
    NavbarPrinc,
    googleMap,
    TitleBar,
  },
  data() {
    return {
      nome: "",
      email: "",
      mensagem: "",
      telefone: "",
      formulario: [],
    };
  },
  methods: {
    sendformulario() {
      if (
        this.nome.length == 0 ||
        this.email.length == 0 ||
        this.telefone.length == 0
      ) {
        alert("Preencha os espaços vazios");
      } else {
        this.formulario.push(
          this.nome,
          this.email,
          this.telefone,
          this.mensagem
        );
        this.nome = "";
        this.email = "";
        this.telefone = "";
        this.mensagem = "";
      }
    },
  },
};
</script>

<style scoped>
@font-face {
  font-family: "Gotham";
  src: local("Fonts"), url(../assets/Fonts/GothamBold.otf) format("truetype");
}
.texto-ang-less {
  width: 300px;
  margin: auto;
}
.ContactoTitulo {
  background-color: rgb(139, 180, 95, 0.6);
  -moz-background-color: rgb(139, 180, 95, 0.6);
  -ms-background-color: rgb(139, 180, 95, 0.6);
  -webkit-background-color: rgb(139, 180, 95, 0.6);
  color: #fff;
  -moz-color: #fff;
  -ms-color: #fff;
  -webkit-color: #fff;
  padding: 2%;
  font-family: "Gotham";
  -moz-font-family: "Gotham";
  -ms-font-family: "Gotham";
  -webkit-font-family: "Gotham";
  text-align: left;
  -moz-text-align: left;
  -ms-text-align: left;
  -webkit-text-align: left;
  position: relative;
  -moz-position: relative;
  -ms-position: relative;
  -webkit-position: relative;
  /* z-index: 1; */
}
label {
  font-size: 20px;
  -moz-font-size: 20px;
  -ms-font-size: 20px;
  -webkit-font-size: 20px;
  text-align: left !important;
  -moz-text-align: left !important;
  -ms-text-align: left !important;
  -webkit-text-align: left !important;
  font-family: "Gotham";
  -moz-font-family: "Gotham";
  -ms-font-family: "Gotham";
  -webkit-font-family: "Gotham";
  color: #707070;
  -moz-color: #707070;
  -ms-color: #707070;
  -webkit-color: #707070;
}
#Formulario {
  padding: 2% 5%;
  -moz-padding: 2% 5%;
  -ms-padding: 2% 5%;
  -webkit-padding: 2% 5%;
  position: relative;
  -moz-position: relative;
  -ms-position: relative;
  -webkit-position: relative;
}
#Formulario::before {
  content: "";
  -moz-content: "";
  -ms-content: "";
  -webkit-content: "";
  position: absolute;
  -moz-position: absolute;
  -ms-position: absolute;
  -webkit-position: absolute;
  width: 100%;
  -moz-width: 100%;
  -ms-width: 100%;
  -webkit-width: 100%;
  height: 100%;
  -moz-height: 100%;
  -ms-height: 100%;
  -webkit-height: 100%;
  top: 0px;
  -moz-top: 0px;
  -ms-top: 0px;
  -webkit-top: 0px;
  left: 0px;
  -moz-left: 0px;
  -ms-left: 0px;
  -webkit-left: 0px;
  background: url("../assets/imgs/img4.jpg") no-repeat center center;
  -moz-background: url("../assets/imgs/img4.jpg") no-repeat center center;
  -ms-background: url("../assets/imgs/img4.jpg") no-repeat center center;
  -webkit-background: url("../assets/imgs/img4.jpg") no-repeat center center;
  background-size: 70% 120%;
  -moz-background-size: 70% 120%;
  -ms-background-size: 70% 120%;
  -webkit-background-size: 70% 150%;
  filter: opacity(0.1);
  -moz-filter: opacity(0.1);
  -ms-filter: opacity(0.1);
  -webkit-filter: opacity(0.1);
}
.form-control {
  width: 100%;
  -moz-width: 100%;
  -ms-width: 100%;
  -webkit-width: 100%;
}
.form-group {
  text-align: left !important;
  -moz-text-align: left !important;
  -ms-text-align: left !important;
  -webkit-text-align: left !important;
}
.btn {
  color: #fff;
  -moz-color: #fff;
  -ms-color: #fff;
  -webkit-color: #fff;
  background-color: #8cb560;
  -moz-background-color: #8cb560;
  -ms-background-color: #8cb560;
  -webkit-background-color: #8cb560;
  width: 100%;
  -moz-width: 100%;
  -ms-width: 100%;
  -webkit-width: 100%;
  margin-bottom: 4%;
  -moz-margin-bottom: 4%;
  -ms-margin-bottom: 4%;
  -webkit-margin-bottom: 4%;
  font-family: "Gotham";
  -moz-font-family: "Gotham";
  -ms-font-family: "Gotham";
  -webkit-font-family: "Gotham";
}
.btn:hover {
  color: rgb(214, 210, 210);
  -moz-color: rgb(214, 210, 210);
  -ms-color: rgb(214, 210, 210);
  -webkit-color: rgb(214, 210, 210);
}
.AngLess {
  text-align: center;
  -moz-text-align: center;
  -ms-text-align: center;
  -webkit-text-align: center;
}
.AngLessTitulo {
  color: #8cb560;
  -moz-color: #8cb560;
  -ms-color: #8cb560;
  -webkit-color: #8cb560;
  font-family: "Gotham";
  -moz-font-family: "Gotham";
  -ms-font-family: "Gotham";
  -webkit-font-family: "Gotham";
}
.Texto {
  font-family: "Gotham";
  -moz-font-family: "Gotham";
  -ms-font-family: "Gotham";
  -webkit-font-family: "Gotham";
  text-align: left;
  -moz-text-align: left;
  -ms-text-align: left;
  -webkit-text-align: left;
  color: #707070;
  -moz-color: #707070;
  -ms-color: #707070;
  -webkit-color: #707070;
  font-size: 24px;
  -moz-font-size: 24px;
  -ms-font-size: 24px;
  -webkit-font-size: 24px;
  margin-top: 4%;
  -moz-margin-top: 4%;
  -ms-margin-top: 4%;
  -webkit-margin-top: 4%;
  /* margin-left: 31%; */
  /* text-align: left; */
  /* width: 40px !important; */
}
.Localizacao {
  font-family: "Gotham";
  -moz-font-family: "Gotham";
  -ms-font-family: "Gotham";
  -webkit-font-family: "Gotham";
  color: #8cb560;
  -moz-color: #8cb560;
  -ms-color: #8cb560;
  -webkit-color: #8cb560;
  text-align: left;
  -moz-text-align: left;
  -ms-text-align: left;
  -webkit-text-align: left;
  padding: 1% 4%;
  -moz-padding: 1% 4%;
  -ms-padding: 1% 4%;
  -webkit-padding: 1% 4%;
  margin: auto;
}
.mapa {
  margin: auto !important;
}
@media only screen and (max-width: 300px) {
  .texto-ang-less {
    font-size: 20px;
  }
}
</style>