<template>
<!--  TODO this would be split out so the generic data would be in its own area and then specific data would be added into the different area (ie Space, Dinosaur, Wildlife) -->
<!--    Instead of adding in a partner paramiter if the are always going to not have an id we could use this instead-->
  <div class="museum-highlight"
         id="{{data.id}}">


      <div class="museum-highlight__header"
           :class="[data.partner ? 'partner' : '']">
        <span class="museum-highlight__header-icon">
          <slot name="museum-highlight__icon"/>
        </span>
        <h3>{{data.name}}</h3>

        <div v-if="data.date">Posted: {{getHumanDate(data.date)}}</div>
      </div>

      <div class="museum-highlight__body">
<!--    If there is no image provided don't show one as a genergic image will be out of context of the artical-->
        <img :src="data.image" v-if="data.image"/>

        {{data.description}}
        <br/>
        <br/>

<!--    This data could be passed in ike the icon or depending on the data this could be broken out into a separate component    -->
        <a :href="data.quiz" v-show="data.quiz" target="_blank">Take the quiz!</a>

        <!-- This news bit could be broken out depending on the size of these news items as I feel they make the cards a bit large.       -->
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

export default {
    name: 'MuseumHighlight',
    components: {

    },
    mixins: [
    ],
    props: {
      data: {
        type: Object,
        required: true,
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
        return moment(String(dateValue)).format('DD/MM/YYYY hh:mm')

      }


    },
    created() {

    },
};
</script>

<style lang="scss" scoped>
.museum-highlight {
  margin: 10px;
  width: 300px;
  display: inline-grid;

  &__header {
    background-color: #d8ddff;
    position: relative;
    padding: 10px;

    &.partner {
      background-color: #f3f3f3 !important;
    }

    &-icon {
      color: #b4b43d;
      position: absolute;
      top: -15px;
      right: -15px;
    }

    h3 {
      magin-top: 0;
    }
  }

  &__body{
    padding: 10px;
  }


}
</style>
