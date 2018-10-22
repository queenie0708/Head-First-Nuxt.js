<template>
  <section class="single-recipe">
    <h1>{{ recipe.title}} </h1>
    <div>
      <img :src="recipe.thumbnail" :alt="recipe.title">
    </div>
    <p>{{ recipe.descriptionText }}</p>
  </section>
</template>

<script>
export default {
 asyncData(context) {
  return new Promise((resolve,reject) =>{
   setTimeout( ()=>{
     resolve({
       recipe:[
         {
           id:"1",
           title:"Panda",
           previewText:"Eat~",
           descriptionText:"This is really cute",
           thumbnail:"https://static.boredpanda.com/blog/wp-content/uuuploads/food-art/food-art-18.jpg"
         },
         {
           thumbnail:"https://static.boredpanda.com/blog/wp-content/uuuploads/food-art/food-art-29.jpg",
           title:"Sleeping Rice Bear",
           id:"2",
           previewText:"Eat Good Sleep Good~",
           descriptionText:"This is really cute and creative"
         }
       ].find(el => el.id === context.params.id)
     })
   },1500)
 })
 }
}
</script>

<style scoped>
.single-recipe{
  display:flex;
  flex-flow: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 30px;
}
.recipe-image{
  width: 100%;

}
</style>
