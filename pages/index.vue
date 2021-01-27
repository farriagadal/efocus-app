<template>
  <div class="home-page">
    <GoalsList :courses="courses" />
  </div>
</template>

<script>
export default {
  data () {
    return {
      courses: [
        {
          id: 1,
          title: 'Viaje a Australia',
          label: 'Importante',
          image: 'https://turismoi.cl/uploads/cl/photo/photo_file/2323/161-1.jpg'
        },
        {
          id: 2,
          title: 'Comprar Casa',
          image: 'https://casasnyf.cl/wp-content/uploads/2018/11/gregario_01.jpg'
        },
        {
          id: 3,
          title: 'Aprender Programación',
          image: 'https://ind-centerforexcelle.netdna-ssl.com/img/articles/26ee5-learnprogramming.jpg'
        },
        {
          id: 4,
          title: 'Aprender Inglés',
          image: 'https://dam.ngenespanol.com/wp-content/uploads/2019/03/aprender-ingles-add-.jpg'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>

</style>
