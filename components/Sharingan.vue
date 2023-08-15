<script setup>
const props = defineProps({
  isLoading: Boolean,
})
</script>

<template>
  <div class="eyeleft">
    <div class="sharingano-div">
      <span class="sharingano" :class="isLoading ? 'animation0' : 'animation3'">
        <span class="inner-red"></span>
        <span class="inner-black">
          <span class="inner-full-black"></span>
        </span>
        <span class="tomoe t1"></span>
        <span class="tomoe t2"></span>
        <span class="tomoe t3"></span>
        <span class="roundt1"></span>
        <span class="roundt2"></span>
        <span class="roundt3"></span>
      </span>
    </div>
  </div>
</template>

<style scoped>
.sharingan {
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: 50%;
  border: 6px solid #231e1f;
  height: 200px;
  width: 200px;
  background-color: #a73a3a;
  overflow: hidden;
  -webkit-transition: 0.7s ease;
  -moz-transition: 0.7s ease;
  -o-transition: 0.7s ease;
  -webkit-box-shadow: inset 0 0 30px #231e1f;
}

.sharingan:before {
  content: "";
  border-radius: 50%;
  width: 30px;
  height: 30px;
  background-color: #231e1f;
}

@keyframes round {
  0% {
    transform: rotate(0deg);
  }

  25% {
    transform: rotate(-90deg);
  }

  50% {
    transform: rotate(-180deg);
  }

  100% {
    transform: rotate(-360deg);
  }
}

.sharingano-div {
  border: none;
  background: transparent;
  display: flex;
  border-radius: 50%;
}

.sharingano {
  position: relative;
  width: 200px;
  height: 200px;
  border-radius: 50%;
  border: 6px solid #131212;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #a73a3a;
  overflow: hidden;
  -webkit-transition: 0.7s ease;
  -moz-transition: 0.7s ease;
  -o-transition: 0.7s ease;
  -webkit-box-shadow: inset 0 0 30px #231e1f;
}

.animation3 {
  animation: 3s round infinite linear;
}

.animation0 {
  animation: 0.1s round infinite linear;
}

.inner-black {
  width: 70%;
  height: 70%;
  border-radius: 50%;
  border: 3px solid #131212;
  background-color: #a73a3a;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  z-index: 10;

}

.inner-full-black {
  border-radius: 50%;
  background-color: #131212;
  width: 45%;
  height: 45%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.inner-red {
  border-radius: 50%;
  width: 20%;
  height: 20%;
  z-index: 50;
  position: absolute;
  background-color: #a73a3a;
  overflow: hidden;

}

.tomoe {
  position: absolute;
  width: 15%;
  height: 50%;
  background-color: #131212;
  border-radius: 50%;
  z-index: 15;
}

.t1 {
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  -moz-transform: translateX(-50%);
  -ms-transform: translateX(-50%);
  -o-transform: translateX(-50%);
  -webkit-transform: translateX(-50%);
}

.roundt1 {
  width: 30%;
  height: 65%;
  border-radius: 50%;
  position: absolute;
  top: 0;
  left: 35%;
  background-color: #131212;
  z-index: 5;
  transform: rotateZ(-30deg);
  -moz-transform: rotateZ(-30deg);
  -moz-transform: rotateZ(-30deg);
  -ms-transform: rotateZ(-30deg);
  -o-transform: rotateZ(-30deg);
  -webkit-transform: rotateZ(-30deg);
  transform-origin: top;
  -moz-transform-origin: top;
  -ms-transform-origin: top;
  -o-transform-origin: top;
  -webkit-transform-origin: top;
}

.t2 {
  left: 20%;
  bottom: 10%;
  transform: rotateZ(55deg);
  -moz-transform: rotateZ(55deg);
  -ms-transform: rotateZ(55deg);
  -o-transform: rotateZ(55deg);
  -webkit-transform: rotateZ(55deg);
}

.roundt2 {
  width: 30%;
  height: 65%;
  border-radius: 50%;
  position: absolute;
  right: -5%;
  bottom: -44%;
  background-color: #131212;
  z-index: 5;
  transform: rotateZ(96deg);
  -moz-transform: rotateZ(96deg);
  -ms-transform: rotateZ(96deg);
  -o-transform: rotateZ(96deg);
  -webkit-transform: rotateZ(96deg);
  transform-origin: top;
  -moz-transform-origin: top;
  -ms-transform-origin: top;
  -o-transform-origin: top;
  -webkit-transform-origin: top;
}

.t3 {
  right: 20%;
  bottom: 10%;
  transform: rotateZ(-55deg);
  -moz-transform: rotateZ(-55deg);
  -ms-transform: rotateZ(-55deg);
  -o-transform: rotateZ(-55deg);
  -webkit-transform: rotateZ(-55deg);
}

.roundt3 {
  width: 30%;
  height: 65%;
  border-radius: 50%;
  position: absolute;
  left: -5%;
  bottom: -44%;
  background-color: #131212;
  transform: rotateZ(205deg);
  -moz-transform: rotateZ(205deg);
  -ms-transform: rotateZ(205deg);
  -o-transform: rotateZ(205deg);
  -webkit-transform: rotateZ(205deg);
  transform-origin: top;
  -moz-transform-origin: top;
  -ms-transform-origin: top;
  -o-transform-origin: top;
  -webkit-transform-origin: top;
  z-index: 5;

}

.t1::before {
  content: '';
  position: absolute;
  bottom: 0;
  left: -50%;
  width: 40%;
  height: 80%;
  background-color: #131212;
  transform-origin: bottom center;
  -ms-transform-origin: bottom center;
  -o-transform-origin: bottom center;
  -webkit-transform-origin: bottom center;
  -moz-transform-origin: bottom center;
  transform: rotateZ(13deg);
  -moz-transform: rotateZ(13deg);
  -ms-transform: rotateZ(13deg);
  -o-transform: rotateZ(13deg);
  -webkit-transform: rotateZ(13deg);
}

.t1::after {
  content: '';
  position: absolute;
  bottom: 0;
  right: -50%;
  width: 40%;
  height: 80%;
  background-color: #131212;
  transform-origin: bottom center;
  -ms-transform-origin: bottom center;
  -o-transform-origin: bottom center;
  -webkit-transform-origin: bottom center;
  -moz-transform-origin: bottom center;
  transform: rotateZ(-13deg);
  -moz-transform: rotateZ(-13deg);
  -ms-transform: rotateZ(-13deg);
  -o-transform: rotateZ(-13deg);
  -webkit-transform: rotateZ(-13deg);
}

.t2::before {
  content: '';
  position: absolute;
  top: 0;
  left: -50%;
  width: 41%;
  height: 80%;
  background-color: #131212;
  transform-origin: top center;
  -moz-transform-origin: top center;
  -ms-transform-origin: top center;
  -o-transform-origin: top center;
  -webkit-transform: top center;
  transform: rotateZ(-13deg);
  -moz-transform: rotateZ(-13deg);
  -ms-transform: rotateZ(-13deg);
  -o-transform: rotateZ(-13deg);
  -webkit-transform: rotateZ(-13deg);
}

.t2::after {
  content: '';
  position: absolute;
  top: 0;
  right: -50%;
  width: 40%;
  height: 80%;
  background-color: #131212;
  transform-origin: top center;
  -moz-transform-origin: top center;
  -ms-transform-origin: top center;
  -o-transform-origin: top center;
  -webkit-transform: top center;
  transform: rotateZ(13deg);
  -moz-transform: rotateZ(13deg);
  -ms-transform: rotateZ(13deg);
  -o-transform: rotateZ(13deg);
  -webkit-transform: rotateZ(13deg);
}

.t3::before {
  content: '';
  position: absolute;
  top: 0;
  left: -50%;
  width: 41%;
  height: 80%;
  background-color: #131212;
  transform-origin: top center;
  -moz-transform-origin: top center;
  -ms-transform-origin: top center;
  -o-transform-origin: top center;
  -webkit-transform: top center;
  transform: rotateZ(-13deg);
  -moz-transform: rotateZ(-13deg);
  -ms-transform: rotateZ(-13deg);
  -o-transform: rotateZ(-13deg);
  -webkit-transform: rotateZ(-13deg);
}

.t3::after {
  content: '';
  position: absolute;
  top: 0;
  right: -50%;
  width: 40%;
  height: 80%;
  background-color: #131212;
  transform-origin: top center;
  -moz-transform-origin: top center;
  -ms-transform-origin: top center;
  -o-transform-origin: top center;
  -webkit-transform: top center;
  transform: rotateZ(13deg);
  -moz-transform: rotateZ(13deg);
  -ms-transform: rotateZ(13deg);
  -o-transform: rotateZ(13deg);
  -webkit-transform: rotateZ(13deg);


}
</style>