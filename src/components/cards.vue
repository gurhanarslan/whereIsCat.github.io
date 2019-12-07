<template>
    <div class="container mt-5">
        <div class="row">
            <div class="col-12 col-md-1 "></div>
         <transition enter-class="" appear enter-active-class="animated flip" leave-class="" leave-active-class="animated flip">       
            <section @click="card='card-1'" class="col-12 card-hover mx-2 col-md-2 box card-1"></section>
        </transition>
                 <transition enter-class="" appear enter-active-class="animated flip" leave-class="" leave-active-class="animated flip">       

            <section @click="card='card-2'" class="col-12 card-hover mx-2 col-md-2 box card-2"></section>
              </transition>
         <transition enter-class="" appear enter-active-class="animated flip" leave-class="" leave-active-class="animated flip">       

            <section @click="card='card-3'" class="col-12 card-hover mx-2 col-md-2 box card-3"></section>
              </transition>
                    <transition enter-class="" appear enter-active-class="animated flip" leave-class="" leave-active-class="animated flip">       

            <section @click="card='card-4'" class="col-12 card-hover mx-2 col-md-2 box card-4"></section>
              </transition>
         <transition enter-class="" appear enter-active-class="animated flip" leave-class="" leave-active-class="animated flip">       

            <section @click="card='card-5'" class="col-12 card-hover mx-2 col-md-2 box card-5"></section>
              </transition>
     
        </div>
        <div class="row mt-5  text-center">
            <div class="col-5">

            </div>
         
              <transition enter-class="" appear  enter-active-class="animated flip" leave-class="" leave-active-class="animated flip">
          <div  @click="result" :class="className()" class="col-2 mt-5 box vue"> </div>
       </transition>
            
            </div>
             <div class="col-5">

            </div>
        </div>
    
</template>
<script>
export default {
    data(){
      return{
        card:"default",
        rndCard:"",
        cards:["card-1","card-2","card-3","card-4","card-5"],
        returnComponents:""
      }
    },
    methods:{
        result(){
            if(this.card=="default"){
                alert("Lütfen Önce Kart Seçiniz!")
            }
            else{
          let rnd = Math.floor(Math.random()*this.cards.length)
            let deger;
            this.rndCard = this.cards[rnd];   
            console.log(this.rndCard)  
            if(this.rndCard==this.card){
                              this.returnComponents="appWinner"    
                    console.log(this.returnComponents) 
                          this.$emit("stat-section",this.returnComponents)   
            }
             else{
                    this.returnComponents="appLooser"
                    
                    console.log(this.returnComponents)  
                          this.$emit("stat-section",this.returnComponents)  
             }
            }
      
        },
        className(){
            
        
                 if(this.rndCard==this.card){
                           
               return  this.card
            }
            else{
             return this.rndCard
            }
            
          
        }
    }
    
  
}
</script>
<style>
.card-hover:hover{
    box-shadow: 2px 3px 3px 4px rgb(63, 59, 59);
}
.vue{
    background: url(/src/assets/vue-js-egitim-background.jpg) no-repeat ;
    background-size: cover; 
    width: 100%;
    height: 100%;
    }
    .card-5{
    background: url(/src/assets/card-5.jpg) no-repeat ;
    background-size: cover; 
    width: 100%;
    }
     .card-5:checked{
         background-color: black;
     }
    .card-1{
    background: url(/src/assets/card-1.jpg) no-repeat ;
    background-size: cover; 
    width: 100%;
    }
    .card-2{
    background: url(/src/assets/card-2.jpg) no-repeat ;
    background-size: cover; 
    width: 100%;
    }
    .card-3{
    background: url(/src/assets/card-3.jpg) no-repeat ;
    background-size: cover; 
    width: 100%;
    }
    .card-4{
    background: url(/src/assets/card-4.jpg) no-repeat ;
    background-size: cover; 
    width: 100%;
    }

.box{
    width: 80%;
    height: 250px;
    
    box-shadow: 1px 1px 5px 1px black
}
</style>