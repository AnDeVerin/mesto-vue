<template>
  <div class="popup">
    <div class="popup__content">
      <img @click="hide" src="../assets/images/close.svg" alt class="popup__close" />
      <h3 class="popup__title">Новое место</h3>
      <form @submit.prevent="addCard" class="popup__form" name="new">
        <input
          v-model="name"
          type="text"
          name="name"
          class="popup__input popup__input_type_name"
          placeholder="Название"
        />
        <input
          v-model="link"
          type="text"
          name="link"
          class="popup__input popup__input_type_link-url"
          placeholder="Ссылка на картинку"
        />
        <button type="submit" class="button popup__button">+</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "Popup",

  data() {
    return {
      name: "",
      link: ""
    };
  },

  methods: {
    hide() {
      this.$emit("hide-popup");
    },

    addCard() {
      this.hide();
      const cardData = {
        name: this.name,
        link: this.link
      };

      this.$emit("add-card", cardData);
    }
  }
};
</script>
