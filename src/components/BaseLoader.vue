<template>
  <!-- source: https://codepen.io/yusufbkr/pen/LGEQGK -->
  <div class="soldier"></div>
</template>

<script>
export default {
  name: 'BaseLoader',
}
</script>

<style lang="scss" scoped>
$p: 8px;
$t: transparent;
$c1: #eefff8;
$c2: #27193d;
$c3: #c0cacd;
$c4: #888899;
$c5: #a0a4af;
$c6: #6b657e;

@mixin keyframes($name) {
  @-o-keyframes #{$name} {
    @content;
  }
  @-moz-keyframes #{$name} {
    @content;
  }
  @-webkit-keyframes #{$name} {
    @content;
  }
  @keyframes #{$name} {
    @content;
  }
}
@mixin animation($prop...) {
  -o-animation: $prop;
  -moz-animation: $prop;
  -ms-animation: $prop;
  -webkit-animation: $prop;
  animation: $prop;
}

body {
  @include animation(bg 10s linear infinite);
  overflow: hidden;
}

.soldier {
  position: absolute;
  top: 50%;
  right: 0;
  width: $p * 12;
  height: $p * 30;
  transform: translateY(-50%);
}

.soldier:nth-child(1) {
  @include animation(go 10s linear infinite);
}

.soldier:nth-child(2) {
  @include animation(go 10s 1s linear infinite);
}

.soldier:nth-child(3) {
  @include animation(go 10s 2s linear infinite);
}

.soldier:nth-child(4) {
  @include animation(go 10s 3s linear infinite);
}

@media (max-width: 480px) {
  .soldier {
    display: none;
  }
  .soldier:nth-child(1) {
    display: block;
  }
}

@mixin anim1() {
  box-shadow: 0 0 0px $t, $p * 4 0 0px $c1, $p * 5 0 0px $c1, $p * 6 0 0px $c1,
    $p * 7 0 0px $c1, $p * 8 0 0px $c1, $p * 3 $p 0px $c1, $p * 4 $p 0px $c1,
    $p * 5 $p 0px $c1, $p * 6 $p 0px $c1, $p * 7 $p 0px $c1, $p * 8 $p 0px $c1,
    $p * 9 $p 0px $c1, $p * 3 $p * 2 0px $c1, $p * 4 $p * 2 0px $c1,
    $p * 5 $p * 2 0px $c3, $p * 6 $p * 2 0px $c2, $p * 7 $p * 2 0px $c2,
    $p * 8 $p * 2 0px $c4, $p * 9 $p * 2 0px $c4, $p * 3 $p * 3 0px $c1,
    $p * 4 $p * 3 0px $c3, $p * 5 $p * 3 0px $c3, $p * 6 $p * 3 0px $c1,
    $p * 7 $p * 3 0px $c1, $p * 8 $p * 3 0px $c2, $p * 9 $p * 3 0px $c2,
    $p * 10 $p * 3 0px $c4, $p * 2 $p * 4 0px $c3, $p * 3 $p * 4 0px $c1,
    $p * 4 $p * 4 0px $c3, $p * 5 $p * 4 0px $c2, $p * 6 $p * 4 0px $c1,
    $p * 7 $p * 4 0px $c1, $p * 8 $p * 4 0px $c1, $p * 9 $p * 4 0px $c1,
    $p * 10 $p * 4 0px $c3, $p * 2 $p * 5 0px $c1, $p * 3 $p * 5 0px $c1,
    $p * 4 $p * 5 0px $c1, $p * 5 $p * 5 0px $c1, $p * 6 $p * 5 0px $c1,
    $p * 7 $p * 5 0px $c1, $p * 8 $p * 5 0px $c1, $p * 9 $p * 5 0px $c2,
    $p * 10 $p * 5 0px $c2, $p * 2 $p * 6 0px $c3, $p * 3 $p * 6 0px $c1,
    $p * 4 $p * 6 0px $c1, $p * 5 $p * 6 0px $c1, $p * 6 $p * 6 0px $c3,
    $p * 7 $p * 6 0px $c3, $p * 8 $p * 6 0px $c3, $p * 9 $p * 6 0px $c3,
    $p * 10 $p * 6 0px $c4, $p * 3 $p * 7 0px $c3, $p * 4 $p * 7 0px $c3,
    $p * 5 $p * 7 0px $c3, $p * 6 $p * 7 0px $c3, $p * 7 $p * 7 0px $c3,
    $p * 8 $p * 7 0px $c3, $p * 9 $p * 7 0px $c1, $p * 10 $p * 7 0px $c1,
    $p * 4 $p * 8 0px $c2, $p * 5 $p * 8 0px $c2, $p * 6 $p * 8 0px $c2,
    $p * 7 $p * 8 0px $c2, $p * 8 $p * 8 0px $c4, $p * 3 $p * 9 0px $c3,
    $p * 4 $p * 9 0px $c1, $p * 5 $p * 9 0px $c1, $p * 6 $p * 9 0px $c4,
    $p * 7 $p * 9 0px $c3, $p * 8 $p * 9 0px $c1, $p * 9 $p * 9 0px $c3,
    $p * 3 $p * 10 0px $c1, $p * 4 $p * 10 0px $c1, $p * 5 $p * 10 0px $c1,
    $p * 6 $p * 10 0px $c4, $p * 7 $p * 10 0px $c3, $p * 8 $p * 10 0px $c3,
    $p * 9 $p * 10 0px $c1, $p * 3 $p * 11 0px $c1, $p * 4 $p * 11 0px $c1,
    $p * 5 $p * 11 0px $c1, $p * 6 $p * 11 0px $c4, $p * 7 $p * 11 0px $c3,
    $p * 8 $p * 11 0px $c4, $p * 9 $p * 11 0px $c3, $p * 3 $p * 12 0px $c1,
    $p * 4 $p * 12 0px $c1, $p * 5 $p * 12 0px $c1, $p * 6 $p * 12 0px $c4,
    $p * 7 $p * 12 0px $c3, $p * 8 $p * 12 0px $c3, $p * 9 $p * 12 0px $c1,
    $p * 3 $p * 13 0px $c3, $p * 4 $p * 13 0px $c1, $p * 5 $p * 13 0px $c2,
    $p * 6 $p * 13 0px $c4, $p * 7 $p * 13 0px $c3, $p * 8 $p * 13 0px $c3,
    $p * 9 $p * 13 0px $c1, $p * 3 $p * 14 0px $c2, $p * 4 $p * 14 0px $c2,
    $p * 5 $p * 14 0px $c2, $p * 6 $p * 14 0px $c4, $p * 7 $p * 14 0px $c3,
    $p * 8 $p * 14 0px $c1, $p * 9 $p * 14 0px $c1, $p * 4 $p * 15 0px $c1,
    $p * 5 $p * 15 0px $c3, $p * 6 $p * 15 0px $c4, $p * 7 $p * 15 0px $c3,
    $p * 8 $p * 15 0px $c3, $p * 9 $p * 15 0px $c3, $p * 10 $p * 15 0px $c3,
    $p * 4 $p * 16 0px $c1, $p * 5 $p * 16 0px $c1, $p * 6 $p * 16 0px $c3,
    $p * 7 $p * 16 0px $c4, $p * 8 $p * 16 0px $c4, $p * 9 $p * 16 0px $c4,
    $p * 10 $p * 16 0px $c4, $p * 11 $p * 16 0px $c3, $p * 4 $p * 17 0px $c2,
    $p * 5 $p * 17 0px $c1, $p * 6 $p * 17 0px $c3, $p * 7 $p * 17 0px $c4,
    $p * 8 $p * 17 0px $c1, $p * 9 $p * 17 0px $c4, $p * 10 $p * 17 0px $c4,
    $p * 11 $p * 17 0px $c4, $p * 4 $p * 18 0px $c2, $p * 5 $p * 18 0px $c1,
    $p * 6 $p * 18 0px $c3, $p * 7 $p * 18 0px $c4, $p * 8 $p * 18 0px $c1,
    $p * 9 $p * 18 0px $c4, $p * 5 $p * 19 0px $c2, $p * 6 $p * 19 0px $c2,
    $p * 7 $p * 19 0px $c1, $p * 8 $p * 19 0px $c1, $p * 9 $p * 19 0px $c4,
    $p * 5 $p * 20 0px $c4, $p * 6 $p * 20 0px $c3, $p * 7 $p * 20 0px $c1,
    $p * 8 $p * 20 0px $c1, $p * 9 $p * 20 0px $c4, $p * 5 $p * 21 0px $c4,
    $p * 6 $p * 21 0px $c3, $p * 7 $p * 21 0px $c1, $p * 8 $p * 21 0px $c1,
    $p * 9 $p * 21 0px $c4, $p * 5 $p * 22 0px $c2, $p * 6 $p * 22 0px $c3,
    $p * 7 $p * 22 0px $c1, $p * 8 $p * 22 0px $c2, $p * 9 $p * 22 0px $c2,
    $p * 5 $p * 23 0px $c2, $p * 6 $p * 23 0px $c3, $p * 7 $p * 23 0px $c2,
    $p * 8 $p * 23 0px $c2, $p * 5 $p * 24 0px $c4, $p * 6 $p * 24 0px $c2,
    $p * 7 $p * 24 0px $c1, $p * 8 $p * 24 0px $c1, $p * 5 $p * 25 0px $c4,
    $p * 6 $p * 25 0px $c2, $p * 7 $p * 25 0px $c3, $p * 8 $p * 25 0px $c1,
    $p * 4 $p * 26 0px $c4, $p * 5 $p * 26 0px $c4, $p * 6 $p * 26 0px $c4,
    $p * 7 $p * 26 0px $c3, $p * 8 $p * 26 0px $c1, $p * 3 $p * 27 0px $c2,
    $p * 4 $p * 27 0px $c4, $p * 5 $p * 27 0px $c3, $p * 6 $p * 27 0px $c5,
    $p * 7 $p * 27 0px $c4, $p * 8 $p * 27 0px $c1, $p * 3 $p * 28 0px $c2,
    $p * 4 $p * 28 0px $c4, $p * 5 $p * 28 0px $c4, $p * 6 $p * 28 0px $c5,
    $p * 7 $p * 28 0px $c4, $p * 8 $p * 28 0px $c3, $p * 9 $p * 28 0px $c1,
    $p * 3 $p * 29 0px $c4, $p * 4 $p * 29 0px $c2, $p * 5 $p * 29 0px $c2,
    $p * 6 $p * 29 0px $c3, $p * 7 $p * 29 0px $c2, $p * 8 $p * 29 0px $c3,
    $p * 9 $p * 29 0px $c1, $p * 10 $p * 29 0px $c1, $p * 11 $p * 29 0px $c4,
    $p * 12 $p * 29 0px $c4;
}

@mixin anim2() {
  box-shadow: 0 0 0px $t, $p * 4 0 0px $c1, $p * 5 0 0px $c1, $p * 6 0 0px $c1,
    $p * 7 0 0px $c1, $p * 8 0 0px $c1, $p * 3 $p 0px $c1, $p * 4 $p 0px $c3,
    $p * 5 $p 0px $c1, $p * 6 $p 0px $c1, $p * 7 $p 0px $c1, $p * 8 $p 0px $c1,
    $p * 9 $p 0px $c1, $p * 3 $p * 2 0px $c1, $p * 4 $p * 2 0px $c1,
    $p * 5 $p * 2 0px $c1, $p * 6 $p * 2 0px $c2, $p * 7 $p * 2 0px $c2,
    $p * 8 $p * 2 0px $c2, $p * 9 $p * 2 0px $c4, $p * 3 $p * 3 0px $c1,
    $p * 4 $p * 3 0px $c3, $p * 5 $p * 3 0px $c3, $p * 6 $p * 3 0px $c1,
    $p * 7 $p * 3 0px $c1, $p * 8 $p * 3 0px $c2, $p * 9 $p * 3 0px $c2,
    $p * 10 $p * 3 0px $c4, $p * 2 $p * 4 0px $c3, $p * 3 $p * 4 0px $c1,
    $p * 4 $p * 4 0px $c3, $p * 5 $p * 4 0px $c4, $p * 6 $p * 4 0px $c1,
    $p * 7 $p * 4 0px $c1, $p * 8 $p * 4 0px $c1, $p * 9 $p * 4 0px $c1,
    $p * 10 $p * 4 0px $c3, $p * 2 $p * 5 0px $c1, $p * 3 $p * 5 0px $c1,
    $p * 4 $p * 5 0px $c1, $p * 5 $p * 5 0px $c1, $p * 6 $p * 5 0px $c1,
    $p * 7 $p * 5 0px $c1, $p * 8 $p * 5 0px $c1, $p * 9 $p * 5 0px $c4,
    $p * 10 $p * 5 0px $c2, $p * 2 $p * 6 0px $c3, $p * 3 $p * 6 0px $c3,
    $p * 4 $p * 6 0px $c3, $p * 5 $p * 6 0px $c3, $p * 6 $p * 6 0px $c3,
    $p * 7 $p * 6 0px $c3, $p * 8 $p * 6 0px $c3, $p * 9 $p * 6 0px $c3,
    $p * 10 $p * 6 0px $c4, $p * 3 $p * 7 0px $c3, $p * 4 $p * 7 0px $c3,
    $p * 5 $p * 7 0px $c6, $p * 6 $p * 7 0px $c3, $p * 7 $p * 7 0px $c3,
    $p * 8 $p * 7 0px $c3, $p * 9 $p * 7 0px $c1, $p * 10 $p * 7 0px $c1,
    $p * 4 $p * 8 0px $c6, $p * 5 $p * 8 0px $c2, $p * 6 $p * 8 0px $c2,
    $p * 7 $p * 8 0px $c2, $p * 8 $p * 8 0px $c2, $p * 3 $p * 9 0px $c1,
    $p * 4 $p * 9 0px $c1, $p * 5 $p * 9 0px $c2, $p * 6 $p * 9 0px $c1,
    $p * 7 $p * 9 0px $c1, $p * 8 $p * 9 0px $c1, $p * 3 $p * 10 0px $c1,
    $p * 4 $p * 10 0px $c1, $p * 5 $p * 10 0px $c1, $p * 6 $p * 10 0px $c2,
    $p * 7 $p * 10 0px $c3, $p * 8 $p * 10 0px $c1, $p * 9 $p * 10 0px $c1,
    $p * 3 $p * 11 0px $c3, $p * 4 $p * 11 0px $c1, $p * 5 $p * 11 0px $c1,
    $p * 6 $p * 11 0px $c4, $p * 7 $p * 11 0px $c3, $p * 8 $p * 11 0px $c1,
    $p * 9 $p * 11 0px $c1, $p * 3 $p * 12 0px $c3, $p * 4 $p * 12 0px $c1,
    $p * 5 $p * 12 0px $c1, $p * 6 $p * 12 0px $c4, $p * 7 $p * 12 0px $c3,
    $p * 8 $p * 12 0px $c3, $p * 9 $p * 12 0px $c1, $p * 3 $p * 13 0px $c3,
    $p * 4 $p * 13 0px $c3, $p * 5 $p * 13 0px $c1, $p * 6 $p * 13 0px $c4,
    $p * 7 $p * 13 0px $c4, $p * 8 $p * 13 0px $c3, $p * 9 $p * 13 0px $c1,
    $p * 4 $p * 14 0px $c4, $p * 5 $p * 14 0px $c2, $p * 6 $p * 14 0px $c1,
    $p * 7 $p * 14 0px $c1, $p * 8 $p * 14 0px $c4, $p * 9 $p * 14 0px $c4,
    $p * 4 $p * 15 0px $c2, $p * 5 $p * 15 0px $c2, $p * 6 $p * 15 0px $c3,
    $p * 7 $p * 15 0px $c1, $p * 8 $p * 15 0px $c1, $p * 9 $p * 15 0px $c1,
    $p * 10 $p * 15 0px $c1, $p * 5 $p * 16 0px $c2, $p * 6 $p * 16 0px $c2,
    $p * 7 $p * 16 0px $c2, $p * 8 $p * 16 0px $c3, $p * 9 $p * 16 0px $c3,
    $p * 10 $p * 16 0px $c1, $p * 4 $p * 17 0px $c3, $p * 5 $p * 17 0px $c1,
    $p * 6 $p * 17 0px $c1, $p * 7 $p * 17 0px $c2, $p * 8 $p * 17 0px $c2,
    $p * 9 $p * 17 0px $c1, $p * 4 $p * 18 0px $c1, $p * 5 $p * 18 0px $c1,
    $p * 6 $p * 18 0px $c1, $p * 7 $p * 18 0px $c3, $p * 8 $p * 18 0px $c4,
    $p * 9 $p * 18 0px $c4, $p * 10 $p * 18 0px $c1, $p * 4 $p * 19 0px $c1,
    $p * 5 $p * 19 0px $c1, $p * 6 $p * 19 0px $c1, $p * 7 $p * 19 0px $c3,
    $p * 8 $p * 19 0px $c4, $p * 9 $p * 19 0px $c4, $p * 10 $p * 19 0px $c1,
    $p * 4 $p * 20 0px $c3, $p * 5 $p * 20 0px $c1, $p * 6 $p * 20 0px $c3,
    $p * 7 $p * 20 0px $c3, $p * 8 $p * 20 0px $c2, $p * 9 $p * 20 0px $c4,
    $p * 10 $p * 20 0px $c4, $p * 11 $p * 20 0px $c1, $p * 4 $p * 21 0px $c3,
    $p * 5 $p * 21 0px $c1, $p * 6 $p * 21 0px $c3, $p * 9 $p * 21 0px $c2,
    $p * 10 $p * 21 0px $c4, $p * 11 $p * 21 0px $c2, $p * 12 $p * 21 0px $c2,
    $p * 5 $p * 22 0px $c4, $p * 6 $p * 22 0px $c2, $p * 10 $p * 22 0px $c2,
    $p * 11 $p * 22 0px $c2, $p * 12 $p * 22 0px $c2, $p * 4 $p * 23 0px $c4,
    $p * 5 $p * 23 0px $c2, $p * 6 $p * 23 0px $c2, $p * 10 $p * 23 0px $c4,
    $p * 11 $p * 23 0px $c4, $p * 12 $p * 23 0px $c3, $p * 4 $p * 24 0px $c1,
    $p * 5 $p * 24 0px $c3, $p * 6 $p * 24 0px $c3, $p * 9 $p * 24 0px $c4,
    $p * 10 $p * 24 0px $c4, $p * 11 $p * 24 0px $c3, $p * 4 $p * 25 0px $c1,
    $p * 5 $p * 25 0px $c3, $p * 8 $p * 25 0px $c4, $p * 9 $p * 25 0px $c4,
    $p * 10 $p * 25 0px $c3, $p * 4 $p * 26 0px $c1, $p * 5 $p * 26 0px $c3,
    $p * 8 $p * 26 0px $c4, $p * 9 $p * 26 0px $c3, $p * 10 $p * 26 0px $c4,
    $p * 4 $p * 27 0px $c1, $p * 5 $p * 27 0px $c3, $p * 8 $p * 27 0px $c4,
    $p * 9 $p * 27 0px $c4, $p * 10 $p * 27 0px $c3, $p * 4 $p * 28 0px $c1,
    $p * 5 $p * 28 0px $c1, $p * 6 $p * 28 0px $c1, $p * 9 $p * 28 0px $c4,
    $p * 10 $p * 28 0px $c4, $p * 11 $p * 28 0px $c3, $p * 4 $p * 29 0px $c3,
    $p * 5 $p * 29 0px $c3, $p * 6 $p * 29 0px $c3, $p * 7 $p * 29 0px $c1,
    $p * 8 $p * 29 0px $c4, $p * 9 $p * 29 0px $c4, $p * 10 $p * 29 0px $c2,
    $p * 11 $p * 29 0px $c2, $p * 12 $p * 29 0px $c4, $p * 13 $p * 29 0px $c4;
}

@mixin anim3() {
  box-shadow: 0 0 0px $t, $p * 3 0 0px $c1, $p * 4 0 0px $c1, $p * 5 0 0px $c1,
    $p * 6 0 0px $c1, $p * 7 0 0px $c1, $p * 2 $p 0px $c1, $p * 3 $p 0px $c3,
    $p * 4 $p 0px $c1, $p * 5 $p 0px $c1, $p * 6 $p 0px $c1, $p * 7 $p 0px $c1,
    $p * 8 $p 0px $c1, $p * 2 $p * 2 0px $c1, $p * 3 $p * 2 0px $c1,
    $p * 4 $p * 2 0px $c1, $p * 5 $p * 2 0px $c2, $p * 6 $p * 2 0px $c2,
    $p * 7 $p * 2 0px $c2, $p * 8 $p * 2 0px $c4, $p * 2 $p * 3 0px $c1,
    $p * 3 $p * 3 0px $c3, $p * 4 $p * 3 0px $c3, $p * 5 $p * 3 0px $c1,
    $p * 6 $p * 3 0px $c1, $p * 7 $p * 3 0px $c2, $p * 8 $p * 3 0px $c2,
    $p * 9 $p * 3 0px $c4, $p * 1 $p * 4 0px $c3, $p * 2 $p * 4 0px $c1,
    $p * 3 $p * 4 0px $c3, $p * 4 $p * 4 0px $c4, $p * 5 $p * 4 0px $c1,
    $p * 6 $p * 4 0px $c1, $p * 7 $p * 4 0px $c1, $p * 8 $p * 4 0px $c1,
    $p * 9 $p * 4 0px $c3, $p * 1 $p * 5 0px $c1, $p * 2 $p * 5 0px $c1,
    $p * 3 $p * 5 0px $c1, $p * 4 $p * 5 0px $c1, $p * 5 $p * 5 0px $c1,
    $p * 6 $p * 5 0px $c1, $p * 7 $p * 5 0px $c1, $p * 8 $p * 5 0px $c4,
    $p * 9 $p * 5 0px $c2, $p * 1 $p * 6 0px $c1, $p * 2 $p * 6 0px $c3,
    $p * 3 $p * 6 0px $c3, $p * 4 $p * 6 0px $c3, $p * 5 $p * 6 0px $c3,
    $p * 6 $p * 6 0px $c3, $p * 7 $p * 6 0px $c3, $p * 8 $p * 6 0px $c3,
    $p * 9 $p * 6 0px $c4, $p * 2 $p * 7 0px $c1, $p * 3 $p * 7 0px $c3,
    $p * 4 $p * 7 0px $c6, $p * 5 $p * 7 0px $c3, $p * 6 $p * 7 0px $c3,
    $p * 7 $p * 7 0px $c3, $p * 8 $p * 7 0px $c1, $p * 9 $p * 7 0px $c1,
    $p * 3 $p * 8 0px $c6, $p * 4 $p * 8 0px $c2, $p * 5 $p * 8 0px $c2,
    $p * 6 $p * 8 0px $c2, $p * 7 $p * 8 0px $c2, $p * 3 $p * 9 0px $c3,
    $p * 4 $p * 9 0px $c1, $p * 5 $p * 9 0px $c2, $p * 6 $p * 9 0px $c1,
    $p * 7 $p * 9 0px $c1, $p * 8 $p * 9 0px $c1, $p * 3 $p * 10 0px $c1,
    $p * 4 $p * 10 0px $c1, $p * 5 $p * 10 0px $c1, $p * 6 $p * 10 0px $c4,
    $p * 7 $p * 10 0px $c3, $p * 8 $p * 10 0px $c1, $p * 9 $p * 10 0px $c3,
    $p * 4 $p * 11 0px $c1, $p * 5 $p * 11 0px $c1, $p * 6 $p * 11 0px $c4,
    $p * 7 $p * 11 0px $c3, $p * 8 $p * 11 0px $c3, $p * 9 $p * 11 0px $c1,
    $p * 4 $p * 12 0px $c1, $p * 5 $p * 12 0px $c1, $p * 6 $p * 12 0px $c4,
    $p * 7 $p * 12 0px $c3, $p * 8 $p * 12 0px $c4, $p * 9 $p * 12 0px $c4,
    $p * 10 $p * 12 0px $c1, $p * 11 $p * 12 0px $c1, $p * 4 $p * 13 0px $c3,
    $p * 5 $p * 13 0px $c1, $p * 6 $p * 13 0px $c1, $p * 7 $p * 13 0px $c4,
    $p * 8 $p * 13 0px $c1, $p * 9 $p * 13 0px $c1, $p * 10 $p * 13 0px $c1,
    $p * 11 $p * 13 0px $c1, $p * 4 $p * 14 0px $c4, $p * 5 $p * 14 0px $c3,
    $p * 6 $p * 14 0px $c2, $p * 7 $p * 14 0px $c1, $p * 8 $p * 14 0px $c1,
    $p * 9 $p * 14 0px $c2, $p * 4 $p * 15 0px $c4, $p * 5 $p * 15 0px $c2,
    $p * 6 $p * 15 0px $c3, $p * 7 $p * 15 0px $c1, $p * 8 $p * 15 0px $c2,
    $p * 9 $p * 15 0px $c4, $p * 5 $p * 16 0px $c4, $p * 6 $p * 16 0px $c2,
    $p * 7 $p * 16 0px $c2, $p * 8 $p * 16 0px $c2, $p * 9 $p * 16 0px $c4,
    $p * 4 $p * 17 0px $c4, $p * 5 $p * 17 0px $c1, $p * 6 $p * 17 0px $c1,
    $p * 7 $p * 17 0px $c1, $p * 8 $p * 17 0px $c3, $p * 9 $p * 17 0px $c3,
    $p * 4 $p * 18 0px $c3, $p * 5 $p * 18 0px $c1, $p * 6 $p * 18 0px $c1,
    $p * 7 $p * 18 0px $c3, $p * 8 $p * 18 0px $c3, $p * 9 $p * 18 0px $c3,
    $p * 10 $p * 18 0px $c1, $p * 4 $p * 19 0px $c1, $p * 5 $p * 19 0px $c1,
    $p * 6 $p * 19 0px $c1, $p * 8 $p * 19 0px $c4, $p * 9 $p * 19 0px $c3,
    $p * 10 $p * 19 0px $c1, $p * 4 $p * 20 0px $c1, $p * 5 $p * 20 0px $c1,
    $p * 6 $p * 20 0px $c1, $p * 8 $p * 20 0px $c4, $p * 9 $p * 20 0px $c3,
    $p * 10 $p * 20 0px $c1, $p * 4 $p * 21 0px $c1, $p * 5 $p * 21 0px $c1,
    $p * 6 $p * 21 0px $c1, $p * 8 $p * 21 0px $c4, $p * 9 $p * 21 0px $c3,
    $p * 10 $p * 21 0px $c1, $p * 4 $p * 22 0px $c2, $p * 5 $p * 22 0px $c2,
    $p * 6 $p * 22 0px $c2, $p * 8 $p * 22 0px $c4, $p * 9 $p * 22 0px $c2,
    $p * 10 $p * 22 0px $c2, $p * 4 $p * 23 0px $c1, $p * 5 $p * 23 0px $c1,
    $p * 6 $p * 23 0px $c2, $p * 8 $p * 23 0px $c2, $p * 9 $p * 23 0px $c2,
    $p * 10 $p * 23 0px $c2, $p * 4 $p * 24 0px $c1, $p * 5 $p * 24 0px $c3,
    $p * 6 $p * 24 0px $c3, $p * 8 $p * 24 0px $c4, $p * 9 $p * 24 0px $c3,
    $p * 3 $p * 25 0px $c1, $p * 4 $p * 25 0px $c3, $p * 5 $p * 25 0px $c3,
    $p * 8 $p * 25 0px $c4, $p * 9 $p * 25 0px $c3, $p * 2 $p * 26 0px $c1,
    $p * 3 $p * 26 0px $c3, $p * 4 $p * 26 0px $c3, $p * 8 $p * 26 0px $c4,
    $p * 9 $p * 26 0px $c3, $p * 1 $p * 27 0px $c4, $p * 2 $p * 27 0px $c1,
    $p * 3 $p * 27 0px $c3, $p * 8 $p * 27 0px $c4, $p * 9 $p * 27 0px $c1,
    $p * 2 $p * 28 0px $c4, $p * 3 $p * 28 0px $c1, $p * 8 $p * 28 0px $c4,
    $p * 9 $p * 28 0px $c3, $p * 10 $p * 28 0px $c1, $p * 1 $p * 29 0px $c4,
    $p * 2 $p * 29 0px $c4, $p * 3 $p * 29 0px $c2, $p * 4 $p * 29 0px $c1,
    $p * 5 $p * 29 0px $c4, $p * 6 $p * 29 0px $c4, $p * 8 $p * 29 0px $c2,
    $p * 9 $p * 29 0px $c2, $p * 10 $p * 29 0px $c4, $p * 11 $p * 29 0px $c1,
    $p * 12 $p * 29 0px $c4;
}

.soldier:before {
  content: '';
  width: $p * 1.5;
  height: $p;
  position: absolute;
  top: 0;
  left: 0;
  @include animation(anim 1s ease infinite);
  @include anim3();
}

@include keyframes(anim) {
  0% {
    @include anim1();
  }
  33% {
    @include anim2();
  }
  66% {
    @include anim3();
  }
  100% {
    @include anim1();
  }
}

@include keyframes(go) {
  0% {
    right: 0;
  }
  100% {
    right: 928px;
  }
}

@include keyframes(bg) {
  0% {
    background: hsla(190, 60%, 60%, 0.5);
  }
  50% {
    background: hsla(0, 0%, 0%, 1);
  }
  100% {
    background: hsla(190, 60%, 60%, 0.5);
  }
}
</style>
