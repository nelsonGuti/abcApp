<template>
  <div>
    <div class="container">
      <div class="pyro">
        <div class="before"></div>
        <div class="after"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.container {
  display: grid;
  justify-content: center;
  align-content: center;
}
.pyro {
  margin-top: 5rem;
  width: 100%;
  height: 10vh;
}

.pyro > .before,
.pyro > .after {
  position: relative;
  width: 5px;
  height: 5px;
  border-radius: 50%;
  box-shadow: 0 0 #fff, 0 0 #fff, 0 0 #fff, 0 0 #fff, 0 0 #fff, 0 0 #fff,
    0 0 #fff, 0 0 #fff, 0 0 #fff, 0 0 #fff, 0 0 #fff, 0 0 #fff, 0 0 #fff,
    0 0 #fff, 0 0 #fff, 0 0 #fff, 0 0 #fff, 0 0 #fff, 0 0 #fff, 0 0 #fff,
    0 0 #fff, 0 0 #fff, 0 0 #fff, 0 0 #fff, 0 0 #fff, 0 0 #fff, 0 0 #fff,
    0 0 #fff, 0 0 #fff, 0 0 #fff, 0 0 #fff, 0 0 #fff, 0 0 #fff, 0 0 #fff,
    0 0 #fff, 0 0 #fff, 0 0 #fff, 0 0 #fff, 0 0 #fff, 0 0 #fff, 0 0 #fff,
    0 0 #fff, 0 0 #fff, 0 0 #fff, 0 0 #fff, 0 0 #fff, 0 0 #fff, 0 0 #fff,
    0 0 #fff, 0 0 #fff, 0 0 #fff;
  -moz-animation: 1s bang ease-out infinite backwards,
    1s gravity ease-in infinite backwards, 5s position linear infinite backwards;
  -webkit-animation: 1s bang ease-out infinite backwards,
    1s gravity ease-in infinite backwards, 5s position linear infinite backwards;
  -o-animation: 1s bang ease-out infinite backwards,
    1s gravity ease-in infinite backwards, 5s position linear infinite backwards;
  -ms-animation: 1s bang ease-out infinite backwards,
    1s gravity ease-in infinite backwards, 5s position linear infinite backwards;
  animation: 1s bang ease-out infinite backwards,
    1s gravity ease-in infinite backwards, 5s position linear infinite backwards;
}

.pyro > .after {
  -moz-animation-delay: 1.25s, 1.25s, 1.25s;
  -webkit-animation-delay: 1.25s, 1.25s, 1.25s;
  -o-animation-delay: 1.25s, 1.25s, 1.25s;
  -ms-animation-delay: 1.25s, 1.25s, 1.25s;
  animation-delay: 1.25s, 1.25s, 1.25s;
  -moz-animation-duration: 1.25s, 1.25s, 6.25s;
  -webkit-animation-duration: 1.25s, 1.25s, 6.25s;
  -o-animation-duration: 1.25s, 1.25s, 6.25s;
  -ms-animation-duration: 1.25s, 1.25s, 6.25s;
  animation-duration: 1.25s, 1.25s, 6.25s;
}

@-webkit-keyframes bang {
  to {
    box-shadow: -185px 47.3333333333px #0091ff, -81px -226.6666666667px #ff0051,
      142px -356.6666666667px #00ff44, -211px -356.6666666667px #003cff,
      -205px -22.6666666667px #0080ff, -238px -190.6666666667px #00ff80,
      242px -92.6666666667px #ff0099, -75px -155.6666666667px #4d00ff,
      166px -316.6666666667px yellow, 89px -136.6666666667px #3c00ff,
      -122px -115.6666666667px #0073ff, -88px -404.6666666667px #d0ff00,
      125px -33.6666666667px #ff00bb, -217px -229.6666666667px #f2ff00,
      145px -34.6666666667px #ff0044, 32px -332.6666666667px #0dff00,
      -170px -45.6666666667px #fff200, -165px -221.6666666667px #007bff,
      -62px -126.6666666667px #00ffa2, 14px -40.6666666667px #77ff00,
      -46px -320.6666666667px #ff001e, 95px -12.6666666667px #3300ff,
      158px -157.6666666667px #005eff, 37px -270.6666666667px #00ff44,
      165px -158.6666666667px #37ff00, -158px -98.6666666667px #bbff00,
      -195px -147.6666666667px #ff9500, 40px -278.6666666667px #84ff00,
      -17px -281.6666666667px #4800ff, -8px -96.6666666667px #4400ff,
      131px -180.6666666667px #73ff00, 72px -108.6666666667px #00ff6a,
      149px -0.6666666667px #c800ff, 243px -177.6666666667px #001eff,
      125px -161.6666666667px #ff2200, 27px -396.6666666667px #00fff7,
      -12px -64.6666666667px #8800ff, 45px -243.6666666667px #5500ff,
      -115px -51.6666666667px #fff200, -204px 2.3333333333px #3700ff,
      63px 82.3333333333px #ff4400, -226px -350.6666666667px #66ff00,
      108px 68.3333333333px #2b00ff, 57px -401.6666666667px #d9ff00,
      -122px 75.3333333333px #ff0051, 143px -53.6666666667px #ff9900,
      172px -28.6666666667px #ff00f7, -50px -178.6666666667px #00ff37,
      -111px 26.3333333333px #ff0022, -28px 44.3333333333px #f200ff,
      -136px -71.6666666667px #00fff2;
  }
}
@-moz-keyframes bang {
  to {
    box-shadow: -185px 47.3333333333px #0091ff, -81px -226.6666666667px #ff0051,
      142px -356.6666666667px #00ff44, -211px -356.6666666667px #003cff,
      -205px -22.6666666667px #0080ff, -238px -190.6666666667px #00ff80,
      242px -92.6666666667px #ff0099, -75px -155.6666666667px #4d00ff,
      166px -316.6666666667px yellow, 89px -136.6666666667px #3c00ff,
      -122px -115.6666666667px #0073ff, -88px -404.6666666667px #d0ff00,
      125px -33.6666666667px #ff00bb, -217px -229.6666666667px #f2ff00,
      145px -34.6666666667px #ff0044, 32px -332.6666666667px #0dff00,
      -170px -45.6666666667px #fff200, -165px -221.6666666667px #007bff,
      -62px -126.6666666667px #00ffa2, 14px -40.6666666667px #77ff00,
      -46px -320.6666666667px #ff001e, 95px -12.6666666667px #3300ff,
      158px -157.6666666667px #005eff, 37px -270.6666666667px #00ff44,
      165px -158.6666666667px #37ff00, -158px -98.6666666667px #bbff00,
      -195px -147.6666666667px #ff9500, 40px -278.6666666667px #84ff00,
      -17px -281.6666666667px #4800ff, -8px -96.6666666667px #4400ff,
      131px -180.6666666667px #73ff00, 72px -108.6666666667px #00ff6a,
      149px -0.6666666667px #c800ff, 243px -177.6666666667px #001eff,
      125px -161.6666666667px #ff2200, 27px -396.6666666667px #00fff7,
      -12px -64.6666666667px #8800ff, 45px -243.6666666667px #5500ff,
      -115px -51.6666666667px #fff200, -204px 2.3333333333px #3700ff,
      63px 82.3333333333px #ff4400, -226px -350.6666666667px #66ff00,
      108px 68.3333333333px #2b00ff, 57px -401.6666666667px #d9ff00,
      -122px 75.3333333333px #ff0051, 143px -53.6666666667px #ff9900,
      172px -28.6666666667px #ff00f7, -50px -178.6666666667px #00ff37,
      -111px 26.3333333333px #ff0022, -28px 44.3333333333px #f200ff,
      -136px -71.6666666667px #00fff2;
  }
}
@-o-keyframes bang {
  to {
    box-shadow: -185px 47.3333333333px #0091ff, -81px -226.6666666667px #ff0051,
      142px -356.6666666667px #00ff44, -211px -356.6666666667px #003cff,
      -205px -22.6666666667px #0080ff, -238px -190.6666666667px #00ff80,
      242px -92.6666666667px #ff0099, -75px -155.6666666667px #4d00ff,
      166px -316.6666666667px yellow, 89px -136.6666666667px #3c00ff,
      -122px -115.6666666667px #0073ff, -88px -404.6666666667px #d0ff00,
      125px -33.6666666667px #ff00bb, -217px -229.6666666667px #f2ff00,
      145px -34.6666666667px #ff0044, 32px -332.6666666667px #0dff00,
      -170px -45.6666666667px #fff200, -165px -221.6666666667px #007bff,
      -62px -126.6666666667px #00ffa2, 14px -40.6666666667px #77ff00,
      -46px -320.6666666667px #ff001e, 95px -12.6666666667px #3300ff,
      158px -157.6666666667px #005eff, 37px -270.6666666667px #00ff44,
      165px -158.6666666667px #37ff00, -158px -98.6666666667px #bbff00,
      -195px -147.6666666667px #ff9500, 40px -278.6666666667px #84ff00,
      -17px -281.6666666667px #4800ff, -8px -96.6666666667px #4400ff,
      131px -180.6666666667px #73ff00, 72px -108.6666666667px #00ff6a,
      149px -0.6666666667px #c800ff, 243px -177.6666666667px #001eff,
      125px -161.6666666667px #ff2200, 27px -396.6666666667px #00fff7,
      -12px -64.6666666667px #8800ff, 45px -243.6666666667px #5500ff,
      -115px -51.6666666667px #fff200, -204px 2.3333333333px #3700ff,
      63px 82.3333333333px #ff4400, -226px -350.6666666667px #66ff00,
      108px 68.3333333333px #2b00ff, 57px -401.6666666667px #d9ff00,
      -122px 75.3333333333px #ff0051, 143px -53.6666666667px #ff9900,
      172px -28.6666666667px #ff00f7, -50px -178.6666666667px #00ff37,
      -111px 26.3333333333px #ff0022, -28px 44.3333333333px #f200ff,
      -136px -71.6666666667px #00fff2;
  }
}
@-ms-keyframes bang {
  to {
    box-shadow: -185px 47.3333333333px #0091ff, -81px -226.6666666667px #ff0051,
      142px -356.6666666667px #00ff44, -211px -356.6666666667px #003cff,
      -205px -22.6666666667px #0080ff, -238px -190.6666666667px #00ff80,
      242px -92.6666666667px #ff0099, -75px -155.6666666667px #4d00ff,
      166px -316.6666666667px yellow, 89px -136.6666666667px #3c00ff,
      -122px -115.6666666667px #0073ff, -88px -404.6666666667px #d0ff00,
      125px -33.6666666667px #ff00bb, -217px -229.6666666667px #f2ff00,
      145px -34.6666666667px #ff0044, 32px -332.6666666667px #0dff00,
      -170px -45.6666666667px #fff200, -165px -221.6666666667px #007bff,
      -62px -126.6666666667px #00ffa2, 14px -40.6666666667px #77ff00,
      -46px -320.6666666667px #ff001e, 95px -12.6666666667px #3300ff,
      158px -157.6666666667px #005eff, 37px -270.6666666667px #00ff44,
      165px -158.6666666667px #37ff00, -158px -98.6666666667px #bbff00,
      -195px -147.6666666667px #ff9500, 40px -278.6666666667px #84ff00,
      -17px -281.6666666667px #4800ff, -8px -96.6666666667px #4400ff,
      131px -180.6666666667px #73ff00, 72px -108.6666666667px #00ff6a,
      149px -0.6666666667px #c800ff, 243px -177.6666666667px #001eff,
      125px -161.6666666667px #ff2200, 27px -396.6666666667px #00fff7,
      -12px -64.6666666667px #8800ff, 45px -243.6666666667px #5500ff,
      -115px -51.6666666667px #fff200, -204px 2.3333333333px #3700ff,
      63px 82.3333333333px #ff4400, -226px -350.6666666667px #66ff00,
      108px 68.3333333333px #2b00ff, 57px -401.6666666667px #d9ff00,
      -122px 75.3333333333px #ff0051, 143px -53.6666666667px #ff9900,
      172px -28.6666666667px #ff00f7, -50px -178.6666666667px #00ff37,
      -111px 26.3333333333px #ff0022, -28px 44.3333333333px #f200ff,
      -136px -71.6666666667px #00fff2;
  }
}
@keyframes bang {
  to {
    box-shadow: -185px 47.3333333333px #0091ff, -81px -226.6666666667px #ff0051,
      142px -356.6666666667px #00ff44, -211px -356.6666666667px #003cff,
      -205px -22.6666666667px #0080ff, -238px -190.6666666667px #00ff80,
      242px -92.6666666667px #ff0099, -75px -155.6666666667px #4d00ff,
      166px -316.6666666667px yellow, 89px -136.6666666667px #3c00ff,
      -122px -115.6666666667px #0073ff, -88px -404.6666666667px #d0ff00,
      125px -33.6666666667px #ff00bb, -217px -229.6666666667px #f2ff00,
      145px -34.6666666667px #ff0044, 32px -332.6666666667px #0dff00,
      -170px -45.6666666667px #fff200, -165px -221.6666666667px #007bff,
      -62px -126.6666666667px #00ffa2, 14px -40.6666666667px #77ff00,
      -46px -320.6666666667px #ff001e, 95px -12.6666666667px #3300ff,
      158px -157.6666666667px #005eff, 37px -270.6666666667px #00ff44,
      165px -158.6666666667px #37ff00, -158px -98.6666666667px #bbff00,
      -195px -147.6666666667px #ff9500, 40px -278.6666666667px #84ff00,
      -17px -281.6666666667px #4800ff, -8px -96.6666666667px #4400ff,
      131px -180.6666666667px #73ff00, 72px -108.6666666667px #00ff6a,
      149px -0.6666666667px #c800ff, 243px -177.6666666667px #001eff,
      125px -161.6666666667px #ff2200, 27px -396.6666666667px #00fff7,
      -12px -64.6666666667px #8800ff, 45px -243.6666666667px #5500ff,
      -115px -51.6666666667px #fff200, -204px 2.3333333333px #3700ff,
      63px 82.3333333333px #ff4400, -226px -350.6666666667px #66ff00,
      108px 68.3333333333px #2b00ff, 57px -401.6666666667px #d9ff00,
      -122px 75.3333333333px #ff0051, 143px -53.6666666667px #ff9900,
      172px -28.6666666667px #ff00f7, -50px -178.6666666667px #00ff37,
      -111px 26.3333333333px #ff0022, -28px 44.3333333333px #f200ff,
      -136px -71.6666666667px #00fff2;
  }
}
@-webkit-keyframes gravity {
  to {
    transform: translateY(200px);
    -moz-transform: translateY(200px);
    -webkit-transform: translateY(200px);
    -o-transform: translateY(200px);
    -ms-transform: translateY(200px);
    opacity: 0;
  }
}
@-moz-keyframes gravity {
  to {
    transform: translateY(200px);
    -moz-transform: translateY(200px);
    -webkit-transform: translateY(200px);
    -o-transform: translateY(200px);
    -ms-transform: translateY(200px);
    opacity: 0;
  }
}
@-o-keyframes gravity {
  to {
    transform: translateY(200px);
    -moz-transform: translateY(200px);
    -webkit-transform: translateY(200px);
    -o-transform: translateY(200px);
    -ms-transform: translateY(200px);
    opacity: 0;
  }
}
@-ms-keyframes gravity {
  to {
    transform: translateY(200px);
    -moz-transform: translateY(200px);
    -webkit-transform: translateY(200px);
    -o-transform: translateY(200px);
    -ms-transform: translateY(200px);
    opacity: 0;
  }
}
@keyframes gravity {
  to {
    transform: translateY(200px);
    -moz-transform: translateY(200px);
    -webkit-transform: translateY(200px);
    -o-transform: translateY(200px);
    -ms-transform: translateY(200px);
    opacity: 0;
  }
}
@-webkit-keyframes position {
  0%,
  19.9% {
    margin-top: 10%;
    margin-left: 40%;
  }
  20%,
  39.9% {
    margin-top: 40%;
    margin-left: 30%;
  }
  40%,
  59.9% {
    margin-top: 20%;
    margin-left: 70%;
  }
  60%,
  79.9% {
    margin-top: 30%;
    margin-left: 20%;
  }
  80%,
  99.9% {
    margin-top: 30%;
    margin-left: 80%;
  }
}
@-moz-keyframes position {
  0%,
  19.9% {
    margin-top: 10%;
    margin-left: 40%;
  }
  20%,
  39.9% {
    margin-top: 40%;
    margin-left: 30%;
  }
  40%,
  59.9% {
    margin-top: 20%;
    margin-left: 70%;
  }
  60%,
  79.9% {
    margin-top: 30%;
    margin-left: 20%;
  }
  80%,
  99.9% {
    margin-top: 30%;
    margin-left: 80%;
  }
}
@-o-keyframes position {
  0%,
  19.9% {
    margin-top: 10%;
    margin-left: 40%;
  }
  20%,
  39.9% {
    margin-top: 40%;
    margin-left: 30%;
  }
  40%,
  59.9% {
    margin-top: 20%;
    margin-left: 70%;
  }
  60%,
  79.9% {
    margin-top: 30%;
    margin-left: 20%;
  }
  80%,
  99.9% {
    margin-top: 30%;
    margin-left: 80%;
  }
}
@-ms-keyframes position {
  0%,
  19.9% {
    margin-top: 10%;
    margin-left: 40%;
  }
  20%,
  39.9% {
    margin-top: 40%;
    margin-left: 30%;
  }
  40%,
  59.9% {
    margin-top: 20%;
    margin-left: 70%;
  }
  60%,
  79.9% {
    margin-top: 30%;
    margin-left: 20%;
  }
  80%,
  99.9% {
    margin-top: 30%;
    margin-left: 80%;
  }
}
@keyframes position {
  0%,
  19.9% {
    margin-top: 10%;
    margin-left: 40%;
  }
  20%,
  39.9% {
    margin-top: 40%;
    margin-left: 30%;
  }
  40%,
  59.9% {
    margin-top: 20%;
    margin-left: 70%;
  }
  60%,
  79.9% {
    margin-top: 30%;
    margin-left: 20%;
  }
  80%,
  99.9% {
    margin-top: 30%;
    margin-left: 80%;
  }
}
</style>