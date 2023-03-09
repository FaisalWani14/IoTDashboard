<template>
  <div class="logo">
    <p>Hover over the J to see it explode</p>
    <div class="logo-canvas">
      <svg
        version="1.1"
        xmlns="http://www.w3.org/2000/svg"
        xmlns:xlink="http://www.w3.org/1999/xlink"
        x="0px"
        y="0px"
        viewBox="-100 -80 470 514"
        enable-background="new -100 -80 470 514"
        xml:space="preserve"
        class="logo-svg"
      >
        <g class="logo-svg-green-1">
          <polygon points="235.4,58.2 269.2,0.8 186.7,0.8" />
        </g>
        <g class="logo-svg-green-2">
          <polygon points="186.7,0.8 235.4,58.2 188.8,82" />
        </g>
        <g class="logo-svg-green-3">
          <polygon points="269.2,0.8 235.4,58.2 269.2,79.8" />
        </g>
        <g class="logo-svg-cyan-1">
          <polygon points="232.3,145.3 235.4,58.2 188.8,82" />
        </g>
        <g class="logo-svg-cyan-2">
          <polygon points="232.3,145.3 269.2,79.8 235.4,58.2" />
        </g>
        <g class="logo-svg-cyan-3">
          <polygon points="188.8,82 232.3,145.3 185.5,131.1" />
        </g>
        <g class="logo-svg-cyan-4">
          <polygon points="269.2,79.8 232.3,145.3 267.8,126.6" />
        </g>
        <g class="logo-svg-blue-1">
          <polygon points="185.5,131.1 188.8,196.8 232.3,145.3" />
        </g>
        <g class="logo-svg-blue-2">
          <polygon points="232.3,145.3 237.3,206.6 188.8,196.8" />
        </g>
        <g class="logo-svg-blue-3">
          <polygon points="232.3,145.3 267.8,202.7 237.3,206.6" />
        </g>
        <g class="logo-svg-blue-4">
          <polygon points="232.3,145.3 267.8,126.6 267.8,202.7" />
        </g>
        <g class="logo-svg-purple-1">
          <polygon points="188.8,196.8 203.3,290.1 184.9,255.9" />
        </g>
        <g class="logo-svg-purple-2">
          <polygon points="203.3,290.1 237.3,206.6 188.8,196.8" />
        </g>
        <g class="logo-svg-purple-3">
          <polygon points="203.3,290.1 267.8,202.7 237.3,206.6" />
        </g>
        <g class="logo-svg-purple-4">
          <polygon points="203.3,290.1 261.3,279.3 267.8,202.7" />
        </g>
        <g class="logo-svg-pink-1">
          <polygon points="145.3,285.4 184.9,255.9 135.6,315.1" />
        </g>
        <g class="logo-svg-pink-2">
          <polygon points="135.6,315.1 203.3,290.1 184.9,255.9" />
        </g>
        <g class="logo-svg-pink-3">
          <polygon points="203.3,290.1 261.3,279.3 236,323.5" />
        </g>
        <g class="logo-svg-pink-4">
          <polygon points="135.6,315.1 236,323.5 203.3,290.1" />
        </g>
        <g class="logo-svg-pink-5">
          <polygon points="135.6,315.1 180.7,353.2 236,323.5" />
        </g>
        <g class="logo-svg-red-1">
          <polygon points="135.6,315.1 104.4,274 145.3,285.4" />
        </g>
        <g class="logo-svg-red-2">
          <polygon points="135.6,315.1 73.6,290.1 104.4,274" />
        </g>
        <g class="logo-svg-red-3">
          <polygon points="73.6,290.1 64.2,335.2 102.1,351.8" />
        </g>
        <g class="logo-svg-red-4">
          <polygon points="73.6,290.1 102.1,351.8 135.6,315.1" />
        </g>
        <g class="logo-svg-red-5">
          <polygon points="102.1,351.8 180.7,353.2 135.6,315.1" />
        </g>
        <g class="logo-svg-orange-1">
          <polygon points="46.1,273 77.8,250.5 104.4,274" />
        </g>
        <g class="logo-svg-orange-2">
          <polygon points="73.6,290.1 46.1,273 104.4,274" />
        </g>
        <g class="logo-svg-orange-3">
          <polygon points="46.1,273 64.2,335.2 73.6,290.1" />
        </g>
        <g class="logo-svg-orange-4">
          <polygon points="46.1,273 8.5,275.2 64.2,335.2" />
        </g>
        <g class="logo-svg-yellow-1">
          <polygon points="46.1,273 0.8,251.5 8.5,275.2" />
        </g>
        <g class="logo-svg-yellow-2">
          <polygon points="0.8,251.5 69.5,230 46.1,273" />
        </g>
        <g class="logo-svg-yellow-3">
          <polygon points="46.1,273 69.5,230 77.8,250.5" />
        </g>
      </svg>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss">
@import "bourbon";

body {
  text-align: center;
}

.logo {
  font-family: "Helvetica", Arial, sans-serif;
  font-size: 0.8em;
  display: inline-block;
  position: relative;
}

.logo-svg {
  width: em(228);
  height: em(250);
  position: relative;

  polygon {
    stroke: #ccc;
    stroke-width: 1;
  }

  g {
    transform: translateX(0);
    transition: transform 0.1s ease;
  }
}

.logo-svg {
  &-green-1 {
    fill: #3fae52;
  }
  &-green-2 {
    fill: #7cc686;
  }
  &-green-3 {
    fill: #2d8d43;
  }
  &-cyan-1 {
    fill: #00bad2;
  }
  &-cyan-2 {
    fill: #0097a7;
  }
  &-cyan-3 {
    fill: #4ac4d7;
  }
  &-cyan-4 {
    fill: #00bad2;
  }
  &-blue-1 {
    fill: #62b3e4;
  }
  &-blue-2 {
    fill: #1b77bd;
  }
  &-blue-3 {
    fill: #62b3e4;
  }
  &-blue-4 {
    fill: #3191cf;
  }
  &-purple-1 {
    fill: #7a3594;
  }
  &-purple-2 {
    fill: #944198;
  }
  &-purple-3 {
    fill: #b06eae;
  }
  &-purple-4 {
    fill: #944198;
  }
  &-pink-1 {
    fill: #e81f64;
  }
  &-pink-2 {
    fill: #c21e5c;
  }
  &-pink-3 {
    fill: #f06392;
  }
  &-pink-4 {
    fill: #e81f64;
  }
  &-pink-5 {
    fill: #c21e5c;
  }
  &-red-1 {
    fill: #ef4438;
  }
  &-red-2 {
    fill: #e57373;
  }
  &-red-3 {
    fill: #d32e2e;
  }
  &-red-4 {
    fill: #ef4438;
  }
  &-red-5 {
    fill: #d32e2e;
  }
  &-orange-1 {
    fill: #f47c20;
  }
  &-orange-2 {
    fill: #f8951f;
  }
  &-orange-3 {
    fill: #f47c20;
  }
  &-orange-4 {
    fill: #fcb452;
  }
  &-yellow-1 {
    fill: #fedc63;
  }
  &-yellow-2 {
    fill: #fecd27;
  }
  &-yellow-3 {
    fill: #faa71c;
  }
}

@mixin lst($transform-rotate, $transform-x, $transform-y) {
  transform: rotate($transform-rotate)
    translate3d(em($transform-x), em($transform-y), 0);
}

.logo:hover {
  .logo-svg {
    &-green-1 {
      @include lst(-15deg, 30, 0);
    }
    &-green-2 {
      @include lst(-10deg, -10, -30);
    }
    &-green-3 {
      @include lst(14deg, 20, -110);
    }
    &-cyan-1 {
      @include lst(-7deg, -85, -50);
    }
    &-cyan-2 {
      @include lst(22deg, 70, -180);
    }
    &-cyan-3 {
      @include lst(12deg, -20, -80);
    }
    &-cyan-4 {
      @include lst(-25deg, 0, 80);
    }
    &-blue-1 {
      @include lst(7deg, -35, -60);
    }
    &-blue-2 {
      @include lst(13deg, 100, -150);
    }
    &-blue-3 {
      @include lst(2deg, 50, -50);
    }
    &-blue-4 {
      @include lst(-10deg, 50, 60);
    }
    &-purple-1 {
      @include lst(5deg, -80, -150);
    }
    &-purple-2 {
      @include lst(8deg, -20, -120);
    }
    &-purple-3 {
      @include lst(-30deg, -80, 120);
    }
    &-purple-4 {
      @include lst(20deg, 150, -80);
    }
    &-pink-1 {
      @include lst(10deg, 40, -120);
    }
    &-pink-2 {
      @include lst(-30deg, -120, 0);
    }
    &-pink-3 {
      @include lst(11deg, 90, 0);
    }
    &-pink-4 {
      @include lst(-60deg, -350, -10);
    }
    &-pink-5 {
      @include lst(-22deg, -120, 90);
    }
    &-red-1 {
      @include lst(5deg, 50, -30);
    }
    &-red-2 {
      @include lst(-20deg, -95, 15);
    }
    &-red-3 {
      @include lst(17deg, 80, 0);
    }
    &-red-4 {
      @include lst(9deg, 50, 20);
    }
    &-red-5 {
      @include lst(-12deg, -70, 50);
    }
    &-orange-1 {
      @include lst(8deg, 70, -35);
    }
    &-orange-2 {
      @include lst(-23deg, -100, 0);
    }
    &-orange-3 {
      @include lst(15deg, 10, 18);
    }
    &-orange-4 {
      @include lst(10deg, 40, 28);
    }
    &-yellow-1 {
      @include lst(20deg, 50, 0);
    }
    &-yellow-2 {
      @include lst(-14deg, -80, -17);
    }
    &-yellow-3 {
      @include lst(-5deg, -15, -20);
    }
  }
}
</style>
