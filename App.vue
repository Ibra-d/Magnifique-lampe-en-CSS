<template>
  <main>
    <div class="container">
      <div class="on_off">
        <button class="allumer">on</button>
      </div>
      <div class="baton"></div>
      <div class="ampoule_container">
        <div class="ampoule"></div>
        <div class="lumiere"></div>
      </div>
    </div>
  </main>
</template>
//
<script>
import { onMounted } from "vue";
// ...
export default {
  setup() {
    // ...
    onMounted(function () {
      const allumer = document.querySelector(".allumer"),
        hide = document.querySelector(".ampoule");
      allumer.addEventListener("click", function () {
        hide.classList.toggle("hide");
        allumer.textContent === "on"
          ? (allumer.textContent = "off")
          : (allumer.textContent = "on");
      });
    });
    // ...
    // Function on here
    // ...
    return {};
  },
};
</script>
//
<style lang="scss">
@import url(https://fonts.googleapis.com/css?family=Ubuntu:300,300italic,regular,italic,500,500italic,700,700italic);
::-webkit-scrollbar {
  display: none;
}
body {
  background-color: rgb(35, 35, 35);
  margin: 0;
  font-family: Ubuntu;
}
main {
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
  .container {
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 30em;
    width: 20rem;
    .baton {
      height: 13rem;
      width: 0.7rem;
      background-color: rgb(255, 255, 255);
    }
    .ampoule_container {
      display: flex;
      justify-content: center;
      align-items: center;
      position: relative;
      height: 4rem;
      width: 10rem;
      border-radius: 7rem 7rem 0 0;
      background-color: white;
      .ampoule {
        position: absolute;
        bottom: -1rem;
        border-radius: 0 0 1rem 1rem;
        height: 1rem;
        width: 2rem;
        opacity: 0;
        transform: translateY(-1rem);
        background-color: #fffd6b;
        transition: 0.3s;
      }
      .hide {
        transition: 0.3s;
        box-shadow: #fffd6b7c 0px 40px 2000px 100px;
        transform: translateY(0);
        opacity: 1;
      }
    }
    .on_off {
      position: absolute;
      right: 0;
      top: 0;
      button {
        margin: 0.4rem;
        height: 6rem;
        width: 6rem;
        border: none;
        border-radius: 50%;
        cursor: pointer;
        font-size: 1.4rem;
        text-transform: uppercase;
        box-shadow: rgba(100, 100, 111, 0.99) 0px 7px 29px 0px;
      }
    }
  }
}
</style>
