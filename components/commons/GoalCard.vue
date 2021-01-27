<template>
  <div class="course-card" :style="{ backgroundImage: 'url(' + imageUrl + ')' }" >
    <div class="course-card__label">{{ label }}</div>
    <div class="course-card__text">
      <div class="course-card__text__title">{{ title }}</div>
      <div class="course-card__text__description">
        Última actualización 06-04-2012
      </div>
    </div>
    <nuxt-link :to="`/cursos/${getUrlSlug}`" class="course-card__link" />
  </div>
</template>

<script>
export default {
  props: {
    id: {
      type: Number,
      default: 1
    },
    label: {
      type: String
    },
    title: {
      type: String,
      default: ''
    },
    modulesCount: null,
    imageUrl: {
      type: String
    }
  },

  computed: {
    getUrlSlug () {
      return this.title.replace(/\s/g, '_').toLowerCase()
    }
  }
}
</script>

<style lang="scss" scoped>
$width-card: 370px;
$heigth-card: 420px;
$heigth-card-mobile: 360px;

.course-card {
  // background: url('~@/assets/images/course-img.jpg');
  background-size: cover;
  background-position: center;
  width: $width-card;
  height: $heigth-card;
  position: relative;
  border-radius: 10px;
  transition: all 0.3s ease-in-out;
  cursor: pointer;

  @media (max-width: 768px) {
    width: 100%;
    height: $heigth-card-mobile;
  }

  &::before {
    content: '';
    left: 0px;
    top: 0px;
    position: absolute;
    width: 100%;
    height: 100%;
    background: linear-gradient(360deg, #000000 0%, rgba(0, 0, 0, 0) 100%);
    border-radius: 10px;
  }

  &:hover {
    transform: translateY(-20px);
  }

  &__label {
    background: var(--color-primary);
    padding: 0px 22px;
    border-radius: 30px;
    width: min-content;
    display: flex;
    color: var(--color-secondary-3);
    font-style: normal;
    font-weight: bold;
    font-size: 14px;
    line-height: 24px;
    text-transform: uppercase;
    top: 14px;
    left: 10px;
    position: absolute;
  }

  &__text {
    position: absolute;
    bottom: 33px;
    left: 30px;
    width: 80%;

    &__title {
      font-size: 30px;
      line-height: 36px;
      color: #FFFFFF;
      margin-bottom: 15px;
    }

    &__description {
      font-size: 16px;
      line-height: 24px;
      display: flex;
      align-items: center;
      color: #D5D5D5;
    }
  }

  &__link {
    bottom: 0;
    height: 100%;
    left: 0;
    position: absolute;
    right: 0;
    top: 0;
    width: 100%;
  }
}
</style>
