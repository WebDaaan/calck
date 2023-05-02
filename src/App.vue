<template>
  <div id="app">
    <div class="container">
      <main class="container__calck">
        <div class="calck__header">
          <div class="calck__header__example">
            <p class="example__text">{{ firstNumb }} {{ znak }} {{ secondNumb }}</p>
          </div>
          <div class="calck__header__answer">
            <p class="answer__text">{{ answer }}</p>
          </div>
        </div>
        <h1 class="calck__content__massege">{{ massege }}</h1>
        <div class="calck__content">
          <button @click="numbPushOne" class="calck__content__item calck__content__item-numb">1</button>
          <button @click="numbPushTwo" class="calck__content__item calck__content__item-numb">2</button>
          <button @click="numbPushThree" class="calck__content__item calck__content__item-numb">3</button>
          <button @click="plusPush" class="calck__content__item calck__content__item-znak">+</button>
          <button @click="numbPushZero" class="calck__content__item calck__content__item-numb">0</button>
          <button @click="minusPush" class="calck__content__item calck__content__item-znak">-</button>
          <button @click="answerPush" class="calck__content__item calck__content__item-znak ravno">=</button>
        </div>
      </main>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      answer: null,
      firstNumb: '',
      znak: null,
      secondNumb: '',
      massege: ''
    }
  },
  methods: {
    numbPushZero() {
      if (znak === null) {
        this.firstNumb = this.firstNumb + '0'
      } else {
        this.secondNumb += '0'
      }
    },
    numbPushOne() {
      if (znak === null) {
        this.firstNumb += '1'
      } else {
        this.secondNumb += '1'
      }
    },
    numbPushTwo() {
      if (znak === null) {
        this.firstNumb += '2'
      } else {
        this.secondNumb += '2'
      }
    },
    numbPushThree() {
      if (znak === null) {
        this.firstNumb += '3'
      } else {
        this.secondNumb += '3'
      }
    },
    plusPush() {
      this.znak = '+'
    },
    minusPush() {
      this.znak = '-'
    },
    answerPush() {
      // if (this.secondNumb === null) {
      //   massege = 'Пример написан не до конца'
      // } else {
      this.answer = Number(this.firstNumb) + Number(this.secondNumb)
      // }
    }
  }
}

</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Jost:wght@500&family=Lato:wght@300;400&family=Noto+Sans+SC:wght@300&display=swap');

#app {
  box-sizing: content-box;
  height: 800px;
  font-family: 'Lato', sans-serif;
}

.container {
  width: 100%;
  height: 100%;
  background: linear-gradient(0deg, rgb(202, 199, 199), rgb(255, 255, 255));
  display: flex;
  justify-content: center;
  align-items: center;

}

.container__calck {
  width: 400px;
  height: 360px;
  background-color: rgb(0, 0, 0);
  display: flex;
  flex-direction: column;

  border-radius: 20px;
  box-shadow: 0px 0px 8px 10px rgba(34, 60, 80, 0.2);
  opacity: 90%;
}

.calck__header {
  width: 100%;
  margin-bottom: 5px;
  display: flex;

  &__answer {
    width: 29%;
    height: 60px;
    margin: 20px 20px 0 0;

    background-color: white;
    border: 2px black solid;
    border-radius: 0 20px 20px 0;

    display: flex;
    justify-content: start;
    align-items: center;
  }

  &__example {
    width: 61%;
    height: 60px;
    margin: 20px 0 0 20px;

    background-color: white;
    border: 2px black solid;
    border-radius: 20px 0 0 20px;

    display: flex;
    justify-content: start;
    align-items: center;
  }

  .answer__text {
    margin: 20px;
    font-size: 40px;
    color: rgb(0, 0, 0);

  }

  .example__text {
    margin: 20px;
    font-size: 40px;
    color: rgb(0, 0, 0);

  }
}

.calck__content {
  width: 90%;
  margin: 20px;
  margin-top: 0;

  display: grid;
  grid-template-columns: repeat(3, 110px);
  grid-template-rows: repeat(3, 60px);
  gap: 15px;

  &__item {
    border: none;
    border-radius: 20px;
    font-size: 24px;
    font-weight: 400;

    opacity: 90%;

    &-numb {
      background-color: rgb(96, 96, 96);

      &:hover {
        background: linear-gradient(90deg, rgb(114, 114, 114), rgb(122, 113, 113));
      }

      &:active {
        background: linear-gradient(90deg, rgb(66, 66, 66), rgb(83, 78, 78));
      }
    }

    &-znak {
      background-color: rgb(209, 139, 8);

      &:hover {
        background-color: rgb(237, 156, 5);

        &:active {
          background-color: rgb(171, 113, 5);

        }
      }

      &:active {
        background-color: rgb(168, 119, 28);
      }
    }
  }
}

.znak {
  background-color: rgb(209, 139, 8);
}

.znak:active {
  background-color: rgb(168, 119, 28);

}

.ravno {
  width: 360px;
}
</style>
