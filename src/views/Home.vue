<template>
  <v-container grid-list-xl>
    <v-layout wrap row>
      <!-- <v-flex xs12> -->
        <feed-card
          v-for="(article, i) in articles"
          :key="i"
          :size="article.size"
          :value="article.value"
        />
      <!-- </v-flex> -->
    </v-layout>
  </v-container>
</template>

<script>
export default {
  data () {
    return {
      articles: [
        {
          size: 1,
          value: {
            prominent: false,
            category: 'Travel',
            title: 'The Art Of Travel',
            hero: 'blurcamera.jpg',
            author: 'John L',
            date: 'Nov 2016'
          }
        },
        {
          size: 2,
          value: {
            prominent: false,
            category: 'Travel',
            title: 'Moroccan Days',
            hero: 'moroccandays.jpg',
            author: 'john L',
            date: 'June 2016'
          }
        },
        {
          size: 2,
          value: {
            prominent: false,
            category: 'Leisure',
            title: 'Swedish Fishing',
            hero: 'autumnclouds.jpg',
            author: 'Rachel L',
            date: 'March 2017'
          }
        },
        {
          size: 1,
          value: {
            prominent: true,
            category: 'Travel',
            title: 'The Adventure Begins',
            hero: 'snowcup.jpg',
            author: 'Rachel L',
            date: 'Dec 2016'
          }
        },
        {
          size: 2,
          value: {
            prominent: false,
            category: 'Travel',
            title: 'Paris in Spring',
            hero: 'christmas.jpg',
            author: 'John L',
            date: 'Dec 2016'
          }
        },
        {
          size: 2,
          value: {
            prominent: false,
            category: 'Political',
            title: 'Youthful Independence',
            hero: 'july4.jpg',
            author: 'Rachel L',
            date: 'July 2016'
          }
        }
      ]
    }
  },
  components: {
    FeedCard: () => import('@/components/FeedCard')
  }
}
</script>
