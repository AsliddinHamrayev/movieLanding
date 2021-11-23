<template>
  <main>
    <div class="movie-box">
      <div class="movie-content">
        <div class="left-bar">
          <button class="left-bar__btn">
            <img src="../assets/Animate2.png" alt="" class="leftbar__img" />
          </button>
          <button class="left-bar__btn">
            <img src="../assets/Home.png" alt="" class="leftbar__img" />
          </button>
          <button class="left-bar__btn">
            <img src="../assets/movies.png" alt="" class="leftbar__img" />
          </button>
          <button class="left-bar__btn">
            <img src="../assets/shows.png" alt="" class="leftbar__img" />
          </button>
          <button class="left-bar__btn">
            <img src="../assets/rated.png" alt="" class="leftbar__img" />
          </button>
        </div>

        <div class="movie-text">
          <input
            type="text"
            class="search__input"
            name=""
            id="search"
            placeholder="Write down here"
          />

          <button class="movie__btn">
            <img
              src="../assets/search-interface-symbol.png"
              class="movie-btn__img"
              alt=""
            />
          </button>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
export default {};
</script>

<style>
main {
  background-image: url(../assets/card-img.png);
  height: 500px;
  width: 100%;
  z-index: 4;
  background-position: center;
    background-repeat: no-repeat;
}

.movie-box {
  height: 100%;
}

.movie-content {
  background-color: rgba(0, 0, 0, 0.487);
  color: #fff;
  display: flex;
  gap: 150px;
  height: 100%;
}

.bg__img {
  position: fixed;
  z-index: -1;
  width: 100%;
}

.left-bar {
  display: flex;
  flex-direction: column;
  max-width: 50px;
  background-color: rgba(0, 0, 0, 0.296);
  justify-content: space-around;
}

.left-bar__btn {
  background-color: transparent;
  border: none;
  cursor: pointer;
}

.leftbar__img {
  max-width: 32px;
  height: auto;
}

.movie-text {
  width: 70%;
}

.movie__tag {
  margin-top: 160px;
  background-color: rgba(0, 0, 0, 0.296);
  color: rgb(0, 208, 255);
}

.movie-text {
  text-align: center;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 15px;
}

.movie__btn {
  background-color: rgba(232, 232, 232, 0.296);
  border: none;
  padding: 3px;
  border-radius: 5px;
  cursor: pointer;
}

.search__input {
  width: 50%;
  padding: 10px;
  background-color: rgba(232, 232, 232, 0.296);
  border: none;
  outline: none;
  color: #fff;
  border-radius: 5px;
}

.search__input::placeholder {
  color: #fff;
  opacity: 1;
}
</style>
