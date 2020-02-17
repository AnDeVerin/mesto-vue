<template>
  <div class="root">
    <header class="header root__section">
      <img src="./assets/images/logo.svg" alt="mesto logo" class="logo" />
    </header>

    <div class="profile root__section">
      <div class="user-info">
        <div class="user-info__photo"></div>
        <div class="user-info__data">
          <h1 class="user-info__name">Jaques Causteau</h1>
          <p class="user-info__job">Sailor, Researcher</p>
        </div>
        <button @click="isPopupShown=true" class="button user-info__button">+</button>
      </div>
    </div>

    <div class="places-list root__section">
      <card
        v-for="card in cards"
        :key="card.id"
        :name="card.name"
        :url="card.link"
        @remove="deleteCard(card.id)"
      />
    </div>

    <popup v-if="isPopupShown" @hide-popup="isPopupShown=false" @add-card="addCard"/>
  </div>
</template>

<script>
import Card from "./components/Card.vue";
import Popup from "./components/Popup.vue";

export default {
  name: "App",

  components: {
    Card,
    Popup,
  },

  data() {
    return {
      cards: [
        {
          id: 1,
          name: "Архыз",
          link:
            "https://pictures.s3.yandex.net/frontend-developer/cards-compressed/arkhyz.jpg"
        },
        {
          id: 2,
          name: "Челябинская область",
          link:
            "https://pictures.s3.yandex.net/frontend-developer/cards-compressed/chelyabinsk-oblast.jpg"
        },
        {
          id: 3,
          name: "Иваново",
          link:
            "https://pictures.s3.yandex.net/frontend-developer/cards-compressed/ivanovo.jpg"
        },
        {
          id: 4,
          name: "Камчатка",
          link:
            "https://pictures.s3.yandex.net/frontend-developer/cards-compressed/kamchatka.jpg"
        },
        {
          id: 5,
          name: "Холмогорский район",
          link:
            "https://pictures.s3.yandex.net/frontend-developer/cards-compressed/kholmogorsky-rayon.jpg"
        },
        {
          id: 6,
          name: "Байкал",
          link:
            "https://pictures.s3.yandex.net/frontend-developer/cards-compressed/baikal.jpg"
        },
        {
          id: 7,
          name: "Нургуш",
          link:
            "https://pictures.s3.yandex.net/frontend-developer/cards-compressed/khrebet-nurgush.jpg"
        },
        {
          id: 8,
          name: "Тулиновка",
          link:
            "https://pictures.s3.yandex.net/frontend-developer/cards-compressed/tulinovka.jpg"
        },
        {
          id: 9,
          name: "Остров Желтухина",
          link:
            "https://pictures.s3.yandex.net/frontend-developer/cards-compressed/zheltukhin-island.jpg"
        },
        {
          id: 10,
          name: "Владивосток",
          link:
            "https://pictures.s3.yandex.net/frontend-developer/cards-compressed/vladivostok.jpg"
        }
      ],

      isPopupShown: false,
    };
  },

  methods: {
    deleteCard(id) {
      this.cards = this.cards.filter(card => card.id !== id);
    },

    addCard(data) {
      const { name, link } = data;
      const id = Date.now();
      this.cards.push({ name, link, id });
    }
  }
};
</script>

<style>
@import url(./assets/pages/index.css);
</style>
