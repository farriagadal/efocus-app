<template>
  <div class="courses-list">
    <div class="container">
      <div class="courses-list__results">
        <!-- <img src="@/assets/icons/results-icon.svg" alt=""> -->
        {{ courses.length }} Metas agregadas recientemente

        <v-btn
          color="primary"
          dark
        >
          nueva meta
          <v-icon>mdi-plus</v-icon>
        </v-btn>
      </div>
      <div class="courses-list__list">
        <div
          v-for="(course, index) in courses"
          :key="index"
        >
          <GoalCard
            :id="course.id"
            :label="course.label"
            :title="course.title"
            :modulesCount="course.modules_count"
            :imageUrl="course.image"
          />
        </div>
        <button>
          <v-icon>mdi-plus</v-icon>
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    courses: {
      type: Array
    }
  }
}
</script>

<style lang="scss" scoped>
.courses-list {
  // background: var(--color-secondary-3);
  padding-top: 30px;
  padding-bottom: 60px;

  &__results {
    display: flex;
    align-items: center;
    font-size: 16px;
    line-height: 25px;
    margin-bottom: 50px;
    font-weight: 500;
    font-size: larger;

    img {
      margin-right: 10px;
    }

    button {
      margin-left: auto;
    }
  }
  &__list {
    display: grid;
    grid-template-columns: repeat(3,minmax(0,1fr));
    grid-column-gap: 30px;
    grid-row-gap: 30px;
    .course-card {
      width: 100%;
    }
    @media (max-width: 768px) {
      grid-template-columns: repeat(1,minmax(0,1fr));
    }
  }
}
</style>
