<template>
  <div>
    <Nuxt />
  </div>
</template>


<style lang="scss">
@import url("https://fonts.googleapis.com/css?family=Kulim+Park:400,400i,600,600i,700&display=swap");

// this is for when he highlight text
::selection {
  background: rgb(238, 238, 238);
  color: #1a2934;
}

* {
  &,
  &::before,
  &::after {
    margin: 0;
    padding: 0;
    -webkit-box-sizing: border-box;
    box-sizing: border-box;
  }
}

html,
body {
  height: 100vh; // needed for scrolling... I think. testing needed
  overflow-x: hidden;
}

html {
  font-size: 62.5%; //1rem = 10px; 10px/16px = 62.5%;

  @include responsive(tablet-landscape) {
    font-size: 56.25%; // 1rem = 9px; 9px/16px = 56.25%;
  }

  @include responsive(tablet-portrait) {
    font-size: 50%; // 1rem = 8px; 8px/16px = 50%;
  }

  @include responsive(big-desktop) {
    font-size: 80%; // 1 rem = 12px; 12px/16px = 75%
  }
}

body {
  font-family: "Kulim Park", Arial, Helvetica, sans-serif;
  position: relative; // TESTING: TEMPORARY
  // background-color: #1a2934;
  background-color: $steelblue;
  color: rgb(255, 255, 255);

  //TESTING:
  @include responsive(tablet-portrait) {
    // background-color: crimson;
  }

  & > * {
    width: 100%;
  }
}

.loader {
  position: relative;
  height: 100vh;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: center;
  -ms-flex-pack: center;
  justify-content: center;
  -webkit-box-align: center;
  -ms-flex-align: center;
  align-items: center;
  z-index: 5000; // To hide the nav button when load page is running//NOTE: REMEMBER. NEED TO SET A POSITION
  -webkit-transition: opacity 2s ease-in;
  -webkit-transition: opacity 2s ease-in;
  transition: opacity 2s ease-in;

  background-color: #1a2934;
  color: rgb(238, 238, 238);

  & i {
    font-size: 40rem;
  }
}

.maincontent {
  position: relative;
  z-index: 500;
  background-color: rgb(238, 238, 238);
  color: #1a2934;

  // TESTING:
  width: 100%;
  height: 100vh;
  -webkit-transition: opacity 0.2s ease-in;
  -webkit-transition: opacity 2s ease-in;
  transition: opacity 2s ease-in;
}

// this is the flex slider. move me and everything below me
.slider {
  width: 100%;
  height: 100%;

  &__title {
    height: 10vh;
    font-size: 3rem;
    text-align: center;

    padding: 2rem 0;
  }

  &__container {
    width: 100%;
    height: 86vh;
    display: -webkit-box;
    display: -ms-flexbox;
    display: flex;
    border: 2px solid rgb(238, 238, 238);

    .slide {
      position: relative;
      height: 100%;
      -webkit-box-flex: 1;
      -ms-flex: 1;
      flex: 1;
      border-right: 2px solid rgb(238, 238, 238);
      overflow: hidden;
      -webkit-transition: all 0.5s ease-in-out;
      transition: all 0.5s ease-in-out;
      // background-color: #1a2934;
      cursor: pointer;

      // &:nth-child(1) {
      //   background-image: url(../assets/img/pankaj-patel-SXihyA4oEJs-unsplash.jpg);
      //   background-size: cover;
      //   background-position: top center;
      // }

      // &:nth-child(2) {
      //   background-image: url(../assets/img/annie-spratt-KCQz_b2Hgi8-unsplash.jpg);
      //   background-position: center center;
      // }

      // &:nth-child(3) {
      //   background-image: url(../assets/img/annie-spratt--9vMBjrU-RA-unsplash.jpg);
      //   background-position: top center;
      // }
      // &:nth-child(4) {
      //   background-image: url(../assets/img/brett-jordan-IjKEHs3JtK4-unsplash.jpg);
      //   background-size: cover;
      //   background-position: center center;
      // }
      // &:nth-child(5) {
      //   background-image: url(../assets/img/julian-hochgesang--Wd8gStxy3s-unsplash.jpg);
      //   background-size: cover;
      //   background-position: top center;
      // }

      // &:hover, used to be this.
      // &.open {
      //   -webkit-box-flex: 5;
      //   -ms-flex-positive: 5;
      //   flex-grow: 5;

      //   & .content {
      //     visibility: visible;
      //     opacity: 1;
      //     -webkit-transition: 0.5s;
      //     transition: 0.5s;
      //     -webkit-transition-delay: 0.5s;
      //     transition-delay: 0.5s;
      //     -webkit-transform: translateY(0);
      //     transform: translateY(0);
      //   }
      // }

      // .content {
      //   position: absolute;
      //   bottom: 0;
      //   margin: 40px;
      //   padding: 30px;
      //   background-color: #000;
      //   color: #fff;
      //   visibility: hidden;
      //   opacity: 0;
      //   -webkit-transform: translateY(100px);
      //   transform: translateY(100px);
      //   -webkit-transition: 0s;
      //   transition: 0s;
      // }
    }
  }
}

.button--green {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #3b8070;
  color: #3b8070;
  text-decoration: none;
  padding: 10px 30px;
}

.button--green:hover {
  color: #fff;
  background-color: #3b8070;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}
</style>
