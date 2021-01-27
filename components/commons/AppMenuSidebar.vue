<template>
  <v-list nav>
    <v-list-item
      to="/"
      router
      link
    >
      <v-list-item-action>
        <v-icon>mdi-home</v-icon>
      </v-list-item-action>
      <v-list-item-content>
        <v-list-item-title v-text="'Inicio'" />
      </v-list-item-content>
    </v-list-item>
      <v-list-group
        :value="true"
        prepend-icon="mdi-account-circle"
      >
        <template v-slot:activator>
          <v-list-item-title>Metas</v-list-item-title>
        </template>
        <v-list-item
          v-for="(item, index) in goals"
          :key="index"
          :to="`/goals/${item.id}`"
          dense
          link
        >
          <v-list-item-icon>
            <v-icon dense v-text="item.icon"></v-icon>
          </v-list-item-icon>
          <v-list-item-title v-text="item.title"></v-list-item-title>
        </v-list-item>
     </v-list-group>
  </v-list>
</template>

<script>
export default {
  data () {
    return {
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire'
        }
      ],
      admins: [
        ['Management', 'mdi-account-multiple-outline'],
        ['Settings', 'mdi-cog-outline']
      ],
      cruds: [
        ['Create', 'mdi-plus-outline'],
        ['Read', 'mdi-file-outline'],
        ['Update', 'mdi-update'],
        ['Delete', 'mdi-delete']
      ],
      goals: [
        {
          id: 1,
          title: 'Viaje a Australia',
          label: 'Importante',
          image: 'https://turismoi.cl/uploads/cl/photo/photo_file/2323/161-1.jpg',
          icon: 'mdi-star'
        },
        {
          id: 2,
          title: 'Comprar Casa',
          image: 'https://casasnyf.cl/wp-content/uploads/2018/11/gregario_01.jpg',
          icon: 'mdi-star'
        },
        {
          id: 3,
          title: 'Aprender Programación',
          image: 'https://ind-centerforexcelle.netdna-ssl.com/img/articles/26ee5-learnprogramming.jpg',
          icon: 'mdi-star'
        },
        {
          id: 4,
          title: 'Aprender Inglés',
          image: 'https://dam.ngenespanol.com/wp-content/uploads/2019/03/aprender-ingles-add-.jpg',
          icon: 'mdi-star'
        }
      ]
    }
  }
}
</script>

<style>

</style>
