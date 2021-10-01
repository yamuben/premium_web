
<template>
  <div class="modal"   v-show="value">
    <div class="container">
    <span class="close" @click.prevent="close">&times;</span>

      <h1> Dove usi  l'auto?  </h1>
      <p style="font-size:20px;color:black; padding:0px 30px 0px 30px">Utilizzai <span style="font-weight:bolder; color:#fe5e27">cursori </span> per modificare le percentuali relative al tipo di percoroso che fai abitualmante, una volta impostati i valori cilcca su <span style="font-weight:bolder; color:#fe5e27"> Ricalcola </span></p>
    <div style="height:350px;width:100%;background:#eeeeee;border-radius:20px;padding:5%;"> 
 
     <a-icon type="fire" style="color:red;font-size:40px; margin-right:34%;transform:rotate(180deg)"/>
 <div class="linecard">
        <div class="smallcardline" style="background:#ffc320"></div>
        <div class="smallcardline" style="background:red"></div>
        <div class="smallcardline" style="background:green"></div>
      </div>
     <a-icon type="fire" style="color:red;font-size:40px; margin-left:31%"/>
  <a-card style="width:100%;background:#eeeeee;margin-top:30px">
    <a-card-grid style="width:30%;text-align:center; margin-left:2%;background:white">

          <a-statistic
            title="CITTA"
            :value="33.28"
            :precision="2"
            suffix="%"
            :value-style="{ color: '#ffc320' }"
            style="text-align:center"
          >
            <template #prefix>
              <a-icon type="arrow-up" />
            </template>
          </a-statistic>
     
    </a-card-grid>
    <a-card-grid style="width:30%;text-align:center; margin-left:2.5%;background:white" :hoverable="false">
     
          <a-statistic
            title="STATTALE"
            :value="33.28"
            :precision="2"
            suffix="%"
            :value-style="{ color: 'red' }"
            style="text-align:center"
          >
            <template #prefix>
              <a-icon type="arrow-down" />
            </template>
          </a-statistic>
    </a-card-grid>
    <a-card-grid style="width:30%;text-align:center; margin-left:2.5%;background:white">
      
          <a-statistic
            title="AUTOSTRADA"
            :value="70.28"
            :precision="2"
            suffix="%"
            :value-style="{ color: 'green' }"
            style="text-align:center"
          >
            <template #prefix>
              <a-icon type="arrow-up" />
            </template>
          </a-statistic>
    </a-card-grid>
  </a-card>


    <a-button style="width:100%;margin-top:30px" @click="close">Ricalcola</a-button>
    </div>
    </div>
  </div>
</template>

    <script>
export default {
  name: "Modal",
  props: {
    value: {
      required: true,
    },
  },
  methods: {
    close() {
      this.$emit("input", !this.value);
    },
  },
};
</script>


    <style lang="css" scoped>
.modal {
  background: rgba(0, 0, 0, 0.801);
  height: 100%;
  width: 100%;
  position: fixed;
  padding-top: 100px;
  z-index: 2;
  top:0;
  left:0;
}
.linecard {
  display: flex;
  height: 10px;
  width: 95%;
  margin: 0px 0px 0px 2%;
}
.smallcardline {
  width: 35%;
  height: 100%;
  background: rgb(153, 16, 16);
}
.container {
  background: rgb(255, 255, 255);
  width: 70%;
  margin: auto;
  padding:20px;
}
/* The Close Button */
.close {
  color: #ffffff;
  background:#fe5e27;
  width: 60px;
  height: 60px;
  border-radius: 50%;
  align-items: center;
text-align: center;
padding: 2px;
  float: right;
  font-size: 40px;
  font-weight: bold;
}

.close:hover,
.close:focus {
  color: #eeeeee;
  text-decoration: none;
  cursor: pointer;
}
</style>