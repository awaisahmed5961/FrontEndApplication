<template>
  <div class="header">
    <div class="header__search-container">
      <form>
        <div class="header__search-container-field-group">
          <input
            placeholder="Search..."
            v-model="searchText"
            v-on:keyup="search($event.target.value)"
          />
          <select>
            <option disabled selected value="default">Filter</option>
            <option value="Paris">Paris</option>
            <option value="Rome">Rome</option>
            <option value="Madrid">Madrid</option>
          </select>

          <div v-if="openSuggestionBox" class="serach-container">
            <ul>
              <li v-for="item in searchResult" :key="item" @click="selectedItem(item)">{{item}}</li>
            </ul>
          </div>
        </div>
      </form>
    </div>
    <div class="header__userinformation-container">
      <div class="header__userinformation-container-notification-pannel">
        <img src="../../assets/icons/gloab.svg" alt="icon" />
      </div>
      <div class="header__userinformation-container-profile">
        <img src="../../assets/useravatar.jpeg" alt="userprofile" />
        <div>
          <h6>Barly Vallendito</h6>
          <p>Admin Manager</p>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import axios from "axios";
export default {
  name: "Header",
  data() {
    return {
      searchText: "",
      openSuggestionBox: false,
      searchResult: [],
    };
  },
  methods: {
    selectedItem(item) {
      this.openSuggestionBox = false;
      this.searchResult = [];
      this.searchText = item;
    },
    search(text) {
      let config = {
        headers: {
          "Content-Type": "application/json",
          Accept: "application/json",
        },
      };
      axios
        .post(
          "https://apitest.iqfulfillment.com/v1/test/search",
          { q: text },
          config
        )
        .then((res) => {
          console.log(res);
          this.openSuggestionBox = true;
          this.searchResult = res.data.results;
        })
        .catch((err) => {
          console.log(err);
        });
    },
  },
};
</script>

