<template>
<!--  TODO this would be split out so the generic data would be in its own area and then specific data would be added into the different area (ie Space, Dinosaur, Wildlife) -->
    <div class="museum-highlight" id="{{data.id}}">

      <div class="museum-highlight__header">
        <h3>{{data.name}}</h3>
        <div v-if="data.date">{{getHumanDate(data.date)}}</div>
      </div>

      <div>
        {{data.description}}


        <div class="museum-highlight__body-news" v-if="data.news">
          <h4>{{data.news.title}}</h4>
          <div v-if="data.news.date">{{getHumanDate(data.news.date)}}</div>
        </div>

        <a href="{{data.quiz}}" v-show="data.quiz" >Quiz</a>
      </div>



      ....
        <!-- Display the available information for the highlight -->
    </div>
</template>

<script>
import moment from 'moment';

export default {
    name: 'MuseumHighlight',
    components: {

    },
    mixins: [
    ],
    props: {
      data: {
        type: Object,
        required: false,
      }
    },
    data() {
        return {

        };
    },
    computed: {
        newsDate() {
            // Highlight's news item date
        },

    },
    methods: {
      getHumanDate(dateValue) {
        return moment(String(dateValue)).format('MM/DD/YYYY hh:mm')

      }


    },
    created() {

    },
};
</script>

<style lang="scss" scoped>
.museum-highlight {

}
</style>
