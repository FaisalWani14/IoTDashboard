<template>
  <div class="q-pa-md row items-start q-gutter-md text-center">
    <q-card class="fancy-box">
      <q-card-section class="top">
        <slot name="card-header"></slot>
      </q-card-section>

      <q-card-section class="bottom">
        <slot name="card-content"></slot>
      </q-card-section>
    </q-card>
  </div>
</template>

<script>
export default {};
</script>

<style>
.fancy-box {
  width: 200px;
  margin-top: 40px;
  background-color: #f0f0f0;
  border-radius: 25px;

  margin-inline: 3%;
  box-shadow: 2px 2px 5px #999;
  text-align: center;
  -webkit-box-shadow: 7px -5px 10px 0px #4b0082, 11px -9px 10px 0px #0000ff,
    16px -14px 10px 0px #00ff00, 20px -17px 10px 0px #ffff00,
    24px -19px 10px 0px #ff7f00, 27px -23px 10px 0px #ff0000,
    5px 5px 15px 5px rgba(0, 0, 0, 0);
  box-shadow: 7px -5px 10px 0px #4b0082, 11px -9px 10px 0px #0000ff,
    16px -14px 10px 0px #00ff00, 20px -17px 10px 0px #ffff00,
    24px -19px 10px 0px #ff7f00, 27px -23px 10px 0px #ff0000,
    5px 5px 15px 5px rgba(0, 0, 0, 0);
}
.fancy-box p {
  font-size: 28px;
  line-height: 1.5;
}
.top {
  background-color: #4b0082;
  border-radius: 10px;
  border: 5px solid #4b0082;
  padding: 1px;
  top: -1px;
}
.bottom {
  background-color: #f0f0f0;
  padding: 40px;
}
</style>
