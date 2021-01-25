<template>
  <div class="courses-list">
    <div class="container">
      <div class="courses-list__results">
        <!-- <img src="@/assets/icons/results-icon.svg" alt=""> -->
        {{ courses.length }} Colecciones disponibles para tu selección
      </div>
      <div class="courses-list__list">
        <div
          v-for="(course, index) in courses"
          :key="index"
        >
          <CourseCard
            :id="course.id"
            :label="course.state.name"
            :title="course.title"
            :modulesCount="course.modules_count"
            :imageUrl="course.image"
          />
        </div>
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
  background: var(--color-secondary-3);
  padding-top: 120px;
  padding-bottom: 58px;

  @media (max-width: 768px) {
    padding-left: 18px;
    padding-right: 17px;
    padding-top: 80px;
  }
  &__results {
    display: flex;
    font-family: "Arimo";
    font-style: normal;
    font-weight: normal;
    font-size: 16px;
    line-height: 24px;
    margin-bottom: 30px;

    img {
      margin-right: 10px;
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
