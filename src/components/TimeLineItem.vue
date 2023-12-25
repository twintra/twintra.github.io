<template>
  <v-row class="timeline-container">
    <v-col>
      <div v-if="!onRight" class="item-alt">
        <div  class="icon-alt">
          <slot name="icon"></slot>
        </div>
        <div class="details">
          <h3>
            <slot name="heading"></slot>
            {{ onRight }}
          </h3>
          <slot></slot>
        </div>
      </div>
    </v-col>
    <v-col>
      <div v-if="onRight" class="item">
        <div class="icon">
          <slot name="icon"></slot>
        </div>
        <div class="details">
          <h3>
            <slot name="heading"></slot>
            {{ onRight }}
          </h3>
          <slot></slot>
        </div>
      </div>
    </v-col>

  </v-row>
  
</template>
<script lang="ts">
export default {
  props: {
    onRight: {
      type: Boolean,
      required: false,
      default: true
    },
    color: {
      type: String,
      required: false,
    }
  }
}
</script>
<style scoped>
.v-col{
  padding: 0;
}
.details {
  flex: 1;
  margin-left: 1rem;
}
h3 {
  font-size: 1.2rem;
  font-weight: 500;
  margin-bottom: 0.4rem;
  color: var(--color-heading);
}

/* for right side */
.timeline-container:first-of-type .item:before{
  display: none;
}
.timeline-container:last-of-type .item:after{
  display: none;
}
.item {
  margin-top: 0;
  padding: 0.4rem 0 1rem calc(var(--section-gap) / 2);
  display: flex;
  position: relative;
}
.item:before {
  content: ' ';
  border-left: 1px solid var(--color-border);
  position: absolute;
  left: 0;
  bottom: calc(50% + 25px);
  height: calc(50% - 25px);
}
.item:after {
  content: ' ';
  border-left: 1px solid var(--color-border);
  position: absolute;
  left: 0;
  top: calc(50% + 25px);
  height: calc(50% - 25px);
}
.icon {
  display: flex;
  place-items: center;
  place-content: center;
  top: calc(50% - 25px);
  left: -25px;
  position: absolute;
  border: 1px solid var(--color-border);
  background: var(--color-background);
  border-radius: 8px;
  width: 50px;
  height: 50px;

  color: var(--color-text);
}

/* for left side */
.timeline-container:first-of-type .item-alt:before{
  display: none;
}
.timeline-container:last-of-type .item-alt:after{
  display: none;
}
.item-alt {
  margin-top: 0;
  padding: 0.4rem calc(var(--section-gap) / 2) 1rem 0;
  display: flex;
  position: relative;
}
.item-alt:before {
  content: ' ';
  border-right: 1px solid;
  border-color: var(--color-border);
  position: absolute;
  right: -1px;
  bottom: calc(50% + 25px);
  height: calc(50% - 25px);
}
.item-alt:after {
  content: ' ';
  border-right: 1px solid var(--color-border);
  position: absolute;
  right: -1px;
  top: calc(50% + 25px);
  height: calc(50% - 25px);
}
.icon-alt {
  display: flex;
  place-items: center;
  place-content: center;
  top: calc(50% - 25px);
  right: -25px;
  position: absolute;
  border: 1px solid var(--color-border);
  background: var(--color-background);
  border-radius: 8px;
  width: 50px;
  height: 50px;

  color: var(--color-text);
}


</style>
