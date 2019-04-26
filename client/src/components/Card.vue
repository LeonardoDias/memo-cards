<template>
  <div class="card-container" ontouchstart="">
    <div class="flipper">
        <div class="card-front">
            <p> Front </p>
        </div>
        <div class="card-back">
            <p> Back </p>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Card'
}
</script>

<style scoped>
  .card-container {
    width: 100%;
    height: 100%;
    border: 1px solid #000;
    margin: 0;
    padding: 0;
  }

    .card-container:hover .flipper {
      transform: rotateY(180deg);
    }

  .flipper {
    transition: 1s;
    transform-style: preserve-3d;
    position: relative;
    width: 100%;
    height: 100%;
  }

  .card-front, .card-back {
    width: 100%;
    height: 100%;
    background-color: beige;
    backface-visibility: hidden;
    position: absolute;
    top: 0;
    left: 0;
  }

  .card-front {
    z-index: 2;
    transform: rotateY(0deg);
  }

  .card-back {
    transform: rotateY(180deg);
  }
</style>


