<template>
<!--  TODO this would be split out so the generic data would be in its own area and then specific data would be added into the different area (ie Space, Dinosaur, Wildlife) -->
    <div class="museum-highlight"
         :class="[data.partner ? 'partner' : '']"
         id="{{data.id}}">


      <div class="museum-highlight__header">
        <span class="museum-highlight__header-space-icon">
            <font-awesome-icon icon="fa-solid fa-star" />
          </span>
        <h3>{{data.name}}</h3>

        <div v-if="data.date">Posted: {{getHumanDate(data.date)}}</div>
      </div>

      <div>
        {{data.description}}
        <br/>
        <br/>
        <a :href="data.quiz" v-show="data.quiz" target="_blank">Take the quiz!</a>

        <div class="museum-highlight__body-news" v-if="data.news">
          <h4>{{data.news.title}}</h4>
          <div v-if="data.news.date">Posted: {{getHumanDate(data.news.date)}}</div>
        </div>

      </div>



        <!-- Display the available information for the highlight -->
    </div>
</template>

<script>
import moment from 'moment';
import {FontAwesomeIcon} from "@fortawesome/vue-fontawesome";

export default {
    name: 'MuseumHighlight',
    components: {
      FontAwesomeIcon
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
        return moment(String(dateValue)).format('DD/MMMM/YYYY hh:mm')

      }


    },
    created() {

    },
};
</script>

<style lang="scss" scoped>
.museum-highlight {
  border: 1px solid #696969FF;
  background-color: #d8ddff;
  border-radius: 10px;
  padding: 10px;
  margin: 10px;
  width: 300px;
  display: inline-grid;

  &.partner {
    background-color: #f3f3f3 !important;
  }

  &__header {
    position: relative;

    &-space-icon {
      color: #b4b43d;
      position: absolute;
      right: 0px;
    }
  }


}
</style>
