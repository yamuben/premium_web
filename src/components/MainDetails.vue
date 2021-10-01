<template>
<div>
      <Modal  v-model="modalOpen" />
  <div class="container">
    <div class="sectionone">

<p> <span style="color:#fe5e27; font-size:100px; font-weight:100;"> &euro;X</span><span style="color:#fe5e27; font-size:45px; font-weight:100; vertical-align: 40px">100</span><span style="color:#fe5e27; font-size:45px; font-weight:100;margin-left:-65px">KM </span> </p>
<p style="font-size:20px; color:#7c7c7c"> I costi chilometric relativi alle auto provate dal 2016 ad oggi. <a href="/home" style="color:#fe5e27">Pi&uacute; infromazion </a></p>  
   <p style="color:#7c7c7c;font-size:20px;padding:5px;font-weight:bolder;"> 
<a-icon type="select" style="color:white;font-size:20px;background:#7c7c7c;padding:5px;font-weight:bolder;border-radius:50%; transform:rotate(-90deg)"/> 
  &nbsp; Prezzi aggirionati  al 08/06/2021
   </p>
    
    </div>
    <div class="sectiontwo">
      <h3>COSTI CALACOLATI SU QUESTE PERCENTUALI DU UTILIZZO</h3>
      <div class="smallcardcontainer">
        <div class="smallcard">
          <p
            style="
              font-size: 50px;
              font-weight: bolder;
              margin-top: 2px;
              color: #ffc320
            "
          >
            33
            <span style="font-size: 30px; font-weight: bolder; color: #e5e5e5"
              >%
            </span>
            <br />
            <span style="font-size: 20px; color: black">CITTA</span>
          </p>
        </div>
        
        <div class="smallcard">
          <p
            style="
              font-size: 50px;
              font-weight: bolder;
              margin-top: 2px;
              color: blue;
            "
          >
            33
            <span style="font-size: 30px; font-weight: bolder; color: #e5e5e5"
              >%
            </span>
            <br />
            <span style="font-size: 20px; color: black">STATALE</span>
          </p>
        </div>
        <div class="smallcard">
          <p
            style="
              font-size: 50px;
              font-weight: bolder;
              margin-top: 2px;
              color: green;
            "
          >
            33
            <span style="font-size: 30px; font-weight: bolder; color: #e5e5e5"
              >%
            </span>
            <br />
            <span style="font-size: 20px; color: black">AUTOSTRADA</span>
          </p>
        </div>
      </div>

      <div class="linecard">
        <div class="smallcardline" style="background:#ffc320"></div>
        <div class="smallcardline" style="background:blue"></div>
        <div class="smallcardline" style="background:green"></div>
      </div>

      <button type="button" class="showmodal" @click="openModal">Cambia percentuali</button>
    </div>


  </div>
</div>
</template>

<script>
import Modal from "./Modal.vue";

export default {
  name: "MainDetails",
  components: {
    Modal,
  },
  data() {
    return {
      title: "Premium Web",
      modalOpen: false,
    };
  },

  methods: {
    openModal() {
      this.modalOpen = !this.modalOpen;
    },
  },
};
</script>

<style scoped>
.showmodal {
  width: 70%;
  margin-top: 10px;
  height: 40px;
  background: #fff;
  color: #fe5e27;
  cursor: pointer;
  border-radius: 10px;
  font-weight: bolder;
  font-size: 20px;
  border: 1px solid rgb(223, 223, 223);
}
.showmodal:hover {
  background: rgb(251, 251, 251);
}
.sectionone {
  width: 35%;
  height: 100%;
  padding: 20px;
  text-align:left;
  /* background: #cc9d9d; */
}
.sectiontwo {
  width: 60%;
  height: 100%;
  background: #e5e5e5;
  padding: 20px;
}
.container {
  display: flex;
  width: 100%;
  height: 350px;
  padding: 0px 2% 0px 2%;
  background: #eeeeee;
}
.linecard {
  display: flex;
  height: 5px;
  width: 80%;
  margin: 30px 0px 0px 10%;
}

.smallcardcontainer {
  display: flex;
  height: 150px;
  width: 80%;
  margin: 30px 0px 0px 10%;
}
.smallcard {
  width: 30%;
  height: 100%;
  margin: 0px 1%;
  /* padding: 10px; */
  background: #fff;
  border-radius: 10px;
}
.smallcardline {
  width: 35%;
  height: 100%;
  background: rgb(153, 16, 16);
}
h2 {
  font-size: 40px;
  font-weight: bolder;
}
h3 {
  color: rgb(27, 27, 27);
  font-size: 20px;
  font-weight: bolder;
  /* height:0px; */
}
a{

    text-decoration: none;
    font-weight:bolder;
}
</style>