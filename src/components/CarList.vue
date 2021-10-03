<template>
  <a-tabs type="card" @change="callback">
    <a-tab-pane key="1" tab="Costo">
      <a-list
        item-layout="vertical"
        style="width: 91%"
        size="large"
        :pagination="pagination"
        :data-source="listData"
      >
        <div slot="footer"><b>Premium Products</b></div>
        <a-list-item
          slot="renderItem"
          key="item.title"
          slot-scope="item, index"
        >
          <div class="productcontainer">
            <div style="width:">
              <img width="272" alt="logo" :src="item.picture" />
            </div>
            <div style="padding-left:15px; width:100%;text-align:left; line-height: 0.7;">
              <h1 style="font-weight:bolder">{{ item.title }}</h1>
              <h2 style="font-weight:bolder">{{ item.description }}</h2>
              <div style="display:flex;width:100%">
                  <div style="width:70%">
              <p>Tipo: <b>{{ item.tipo}}</b></p>
              <p>Potenza: <b>{{ item.potenza[0]}}</b>CV | <b>{{ item.potenza[1]}}kW</b> </p>
              <p>Cilindrata: <b>{{ item.cilindrata}}</b> m<sup>3</sup></p>
                  </div>
                  <div style="cursor:pointer; border:2px solid blue;padding:25px 20px 5px 20px; width:30%;text-align:center;">
<h1 style="">GPL </h1>
                  </div>
              </div>
    <a-progress :percent="item.progressOne"  />
    <a-progress :percent="item.progressTwo"  />
            </div>
          </div>
        </a-list-item>
      </a-list>
    </a-tab-pane>
    <a-tab-pane key="2" tab="Potenza"> Content of Tab Pane 2 </a-tab-pane>
    <a-tab-pane key="3" tab="Cilindrata"> Content of Tab Pane 3 </a-tab-pane>
    <a-tab-pane key="4" tab="Marca"> Content of Tab Pane 4 </a-tab-pane>
  </a-tabs>
</template>

<script>
import listData from "../assets/constants/listOfProducts.json";

export default {
  data() {
    return {
      listData,
      pagination: {
        onChange: (page) => {
          console.log(page);
        },
        pageSize: 3,
      },
      actions: [
        { type: "star-o", text: "156" },
        { type: "like-o", text: "156" },
        { type: "message", text: "2" },
      ],
    };
  },
};
</script>

<style scoped>
.productcontainer{
    display: flex;
    padding:5px;
}

.productcontainer:hover{
    box-shadow:4px 4px #eeeeee;
    cursor: pointer;
}

@media only screen and (max-width:768px){
    
    h2{
        font-size: 17px;
    }
}

@media only screen and (max-width: 600px) {
    .productcontainer{
        flex-wrap: wrap;
        width:100%;
        margin-left: 20px;
    }
    h1{
        margin-top: 15px;
    }
    h2{
        font-size: 15px;
    }
}
</style>