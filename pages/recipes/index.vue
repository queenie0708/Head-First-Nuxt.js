<template>
  <section class="recipes">
    <Recipe
      v-for ="recipe in recipes"
      :key="recipe.id"
      :thumbnail="recipe.thumbnail"
      :title="recipe.title"
      :previewText="recipe.previewText"
      :id="recipe.id"
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
             title:"Panda",
             previewText:"Eat~",
             thumbnail:"https://static.boredpanda.com/blog/wp-content/uuuploads/food-art/food-art-18.jpg"
           },
           {
             thumbnail:"https://static.boredpanda.com/blog/wp-content/uuuploads/food-art/food-art-29.jpg",
             title:"Sleeping Rice Bear",
             id:"2",
             previewText:"Eat Good Sleep Good~"
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
