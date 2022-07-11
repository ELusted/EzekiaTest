<template>
<!--  TODO this would be split out so the generic data would be in its own area and then specific data would be added into the different area (ie Space, Dinosaur, Wildlife) -->
    <div class="museum-highlight">
      {{data.name}} - {{data.id}}
      {{data.date}}
      {{data.description}}
      {{data.news}}
        <!-- Display the available information for the highlight -->
    </div>
</template>

<script>

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

    },
    created() {

    },
};
</script>

<style lang="scss" scoped>
.museum-highlight {

}
</style>
