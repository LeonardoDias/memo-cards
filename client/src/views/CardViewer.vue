<template>
  <div class="card-viewer">
    <div class="card-component">
      <Card/>
    </div>
  </div>
</template>

<script>
import Card from '@/components/Card.vue'

export default {
  name: 'CardViewer',
  components: {
    Card
  },
  props: {
    cardHeight: Number,
    cardWidth: Number
  },
  data: () => {
    return {
      cardHeightValue: 0,
      cardWidthValue: 0
    }
  },
  mounted() {
    this.cardHeightValue = this.cardHeight;
    this.cardWidthValue = this.cardWidth;
    
    const cardComponent = document.getElementsByClassName("card-component")[0];
    cardComponent.style.width = `${this.cardWidthValue}px`;
    cardComponent.style.height = `${this.cardHeightValue}px`;
  },
  watch: {
    cardWidthValue: (newWidth, oldWitdh) => {
      const cardComponent = document.getElementsByClassName("card-component")[0];
      cardComponent.style.width = `${newWidth}px`;
    },

    cardHeightValue: (newHeight, oldHeight) => {
      const cardComponent = document.getElementsByClassName("card-component")[0];
      cardComponent.style.height = `${newHeight}px`;
    },
  }
}
</script>

<style>
  .card-viewer {
    display: flex;
    flex-wrap: wrap;
    flex-direction: row;
    align-content: center;
    justify-content: center;
  }

  
</style>
