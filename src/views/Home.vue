<template>
  <div class="hello">
    <Header />
    <MainDetails />
<BodyLayout/>
    <a-layout-footer
     class="footer"
    >
      <div  style="display: flex; text-align: center">
          <div class="divQuat" style="width:85%;display: flex; text-align: center;">
        <h1 style="color: white; font-weight: bolder;">QUATTRORUOTE</h1>
        <h2 style="color: white">
          &nbsp; Sitemap |&nbsp; Contatti |&nbsp; Redazionne
        </h2>
          </div>
         <h1 style="color: white"> <a-icon type="facebook" />  <a-icon type="linkedin" /> <a-icon type="slack-square" /> <a-icon type="instagram" /></h1>
      </div>
      <hr />
    </a-layout-footer>
  </div>
</template>

<script>
import Header from "../components/Header.vue";
import Modal from "../components/Modal.vue";
import MainDetails from "../components/MainDetails.vue";
import BodyLayout from "../components/BodyLayout.vue";
export default {
  name: "HelloWorld",
  components: {
    Header,
    MainDetails,
    Modal,BodyLayout,
  },
  data() {
    return {
      msg: "Welcome to Benjamin Vue.js App",
      modalOpen: true,
    };
  },
  methods: {
    openModal() {
      this.modalOpen = !this.modalOpen;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.hello {
  height: 100%;
  width: 100%;
  display: block;
  padding: 0;
  background: rgb(17, 17, 240);
}
.footer{
      text-align: left;
        background: #424446;
        color: white;
        /* bottom: 0; */
        width: 100%;
}

@media only screen and (max-width: 768px) {
    .footer{
        height: auto;
        position: inherit;
    }
    h1{
        font-size:15px;
        text-align:center;
    }
    h2{
        font-size: 12px;
        text-align:center;
    }
}

@media only screen and (max-width:600px){
div{
    flex-wrap: wrap;
    text-align: center;
width: 100%;
}
    
}

</style>
