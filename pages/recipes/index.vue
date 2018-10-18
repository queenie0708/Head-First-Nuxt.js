<template>
  <section class="recipes">
    <Recipe
      thumbnail="https://static.boredpanda.com/blog/wp-content/uuuploads/food-art/food-art-38.jpg"
      title="Hot Dog"
      id="1"
      previewText="Eat~"
    />
    <Recipe
      thumbnail="https://static.boredpanda.com/blog/wp-content/uuuploads/food-art/food-art-29.jpg"
      title="Sleeping Rice Bear"
      id="2"
      previewText="Eat Good Sleep Good~"
    />

  </section>
</template>

<script>
import Recipe from '@/components/Recipe'
export default{
  components:{
    Recipe
  },
  asyncData(){
   return new Promise((resolve,reject) =>{
     setTimeout( ()=>{
       resolve({
         recipes:[
           {
             id:"1",
             title:"Sleeping Rice Bear",
             previewText:"Eat Good Sleep Good~",
             thumbnail:"https://static.boredpanda.com/blog/wp-content/uuuploads/food-art/food-art-18.jpg"
           }
         ]
       })
     },1500)
   })
  }
}
</script>

<style scoped>
.recipes{
 display: flex;
 flex-flow: row wrap;
 justify-content: center;
 align-items: center;
}

</style>
