<template>
    <div class="topnavcontainer">
        <img src="../assets/premium_logo.png" width="15%" />
<div class="menu">
        <h2 > MENU <a-icon type="menu" /> </h2>
</div>
    </div>
</template>

<script>


export default ({
name:"Header",
data(){
    return {
        title:"Premium Web"
    }
}
})
</script>

<style scoped>
.topnavcontainer{  
    position: -webkit-sticky; /* Safari */
  position: sticky;
  top: 0;
  display:flex;
  align-items: center;
    width: 100%;
    padding: 10px 2% 10px 2%;
    box-shadow: 0 4px 5px rgba(131, 131, 131, 0.575);
    text-align: left;
    background: rgb(255, 255, 255);
    z-index: 5;

}
.menu{
    text-align: right;  width:80%;cursor:pointer; font-weight:bolder;
}
@media only screen and (max-width:600px){
    img{
        width:50%
    }
    .topnavcontainer{
        padding:0px;
    }
    .menu{
        width: 40%;
    }

    
}
</style>