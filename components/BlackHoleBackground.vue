<template>
  <div class="bh--wrapper">
    <div class="bh--content">


      <div class="bh--header">
        <div class="bh--header-name">Luis G. Chinchilla-Garcia</div>
        <div class="bh--header-text">
          <p class="bh--header-text-var">I am </p>
          <div class="bh--header-text-descr"></div>
        </div>
      </div>

      <div class="bh--moons">
        <div class="bh--moon" v-for="n in 8" :key="n"></div>
      </div>

      <div class="bh--shoot" v-for="n in 5" :key="n"></div>
      <div class="bh--stars">
      <div class="bh--star"  v-for="n in 50" :key="n"></div>
      </div>


    </div>
  </div>
</template>

<script>
  export default {
      
  }
</script>

<style lang="scss" scoped>

  .bh--wrapper {
    font-family: 'IBM Plex Serif', serif;
  }

  .bh--content {
    width:100%;
    background:#002142;
    height:850px;
    position:relative;
    overflow:hidden;
  }

  .bh--header {
    width:500px;
    height:200px;
    position:absolute;
    color:#FEFDE8;
    margin-left:20px;
    margin-top:500px;
    text-align: left;
    animation: fadeIn-header .5s;
  }

  .bh--header-name {
    font-size: 40px;
    animation: fadeIn-header 4s;
  }

  .bh--header-text-descr:before {
    content: '';
    animation: words linear infinite 9s;
  }

  h2 {
    font-size: 40px;
  }

  .bh--header-text {
    display: flex;
    padding: 5px 0;
    animation: fadeIn-header-text 1s;
  }

  .bh--header-text-var {
    text-align: left;
    font-size: 30px;
    white-space: pre;
  }

  .bh--header-text-descr {
    text-align: left;
    font-size: 30px;
  }

  .bh--moons {
    animation: fadeIn-bh 4s;
  }

  // bh--Shooting bh--stars
  @for $i from 1 through 8 {

    .bh--shoot:nth-child(#{$i}) {
      width:5px;
      height:5px;
      background:#FEFCE6;
      box-shadow: 0px 1px 30px 0px rgba(255, 255, 255, 1);
      z-index:400;
      position:absolute;
      border-radius:50% + random(5);
      margin-left:-1040px;
      animation: bh--shoot-#{$i} random(3)*3.5 + .8s linear infinite; 
      animation-delay:$i * 0.4s;
    }

    @keyframes bh--shoot-#{$i} {
      0% {
        margin-left:0px;
        margin-top:100px + random(150); 
        width:8px;
        height:8px;
      } 
      50% {
        margin-top:100px;
        width:8px;
        height:8px;
      } 
      100% {
        margin-left:100%;
        margin-top:300px + random(310);
        width:0px;
        height:0px;
      }
    }
    
  }


  $particles: 10; // has to match nodes in dom
  $particleSize: 140px;
  $lapDuration: 2s;
  $shadowColor: #ffffff;
  @keyframes scale {
  0% {
    transform: scale(1);
    opacity: 0;
    box-shadow: 0px 0px 50px rgba($shadowColor, 0.5);
  }
  10% {
    transform: scale(1);
    opacity: .3;
    box-shadow: 0px 0px 50px rgba($shadowColor, 0.5);
  }
  100% {
    transform: scale(.95)  translate(0px, 5px);
    opacity: .1;
    box-shadow: 0px 10px 20px rgba($shadowColor, 0);
  }
  }

  // bh--Moon and rings
  $rings: 8;
  @for $i from 1 through $rings {
    .bh--moon:nth-child(#{$i}) 
    {
      
      $d: $i * 100px;
      width:$d;
      height:$d;
      
      
      border-radius:50%;
      
      background:#FEFCE6;
      box-shadow: 0px 1px 30px 0px rgba(255, 255, 255, 1);
      
      
      opacity: 1/($i*5);
      
      position:absolute;
      z-index:10;
      
      margin-left:calc(50% - #{$d}/2);
      margin-top:calc(400px - #{$d}/2);
      
    }   
    .bh--moon:nth-child(1) {
      opacity: 1;
      background-color: black;
      
      $d: 150px;
      width:$d;
      z-index:50;
      height:$d;
      
      margin-left:calc(50% - #{$d}/2);
      margin-top:calc(400px - #{$d}/2);
    } 
  }

  $lapDuration: 2s;
  $activerings: 4;
  @for $i from 2 through $activerings {
    .bh--moon:nth-child(#{$i}) {
      animation-name: scale;
      animation-duration: $i * ($lapDuration / $activerings);
      animation-iteration-count: infinite;
      animation-timing-function: linear;
      animation-delay: $i * ($lapDuration / $activerings);
    }
  }

  // bh--stars
  .bh--stars  {
    width:100%;
    height:875px;
    overflow:hidden;
    margin:0 auto;
    margin-top:0px;
    position:relative;
  }

  $bh--stars:300;
  @for $i from 0 through $bh--stars {
    .bh--star:nth-child(#{$i})  {
      $d: random(2);
      width: $d + px;
      height: $d + px;
      z-index:1;
      background:white;
      border-radius:50%;
      position:absolute; 
      
      opacity: 1;
      
      margin-left:random(1500) + px;
      margin-top:random(875) + px;
        
      animation: twinkle-#{$i} 1s linear infinite;
      animation-delay:$i*0.01s;
    }
    
    @keyframes twinkle-#{$i} {
      from {
        opacity:1;
      }
      
      to {
        opacity:0.3; 
      }
    }
  }

  @keyframes fadeIn-header {
    0% { opacity: 0; transition: translateY(-5%); }
    50% { opacity: 0; transition: translateY(-5%); }
    100% { opacity: 1; transition: translateY(0%); }
  }

  @keyframes fadeIn-header-text {
    0% { opacity: 0; transition: translateY(-5%); }
    80% { opacity: 0; transition: translateY(-5%); }
    100% { opacity: 1; transition: translateY(0%); }
  }

  @keyframes fadeIn-bh {
    0% { opacity: 0; }
    100% { opacity: 1; }
  }

  @keyframes words {

    // ML Engineer
    0% {
      content: 'a Machine Learning Engineer';
      opacity: 0;
    }
    5% {
      content: 'a Machine Learning Engineer';
      opacity: 1;
    }
    15% {
      content: 'a Machine Learning Engineer';
      opacity: 1;
    }
    19% {
      content: 'a Machine Learning Engineer';
      opacity: 0;
    }

    // Astrophysics
    //   Fade in 
    20% {
      content: 'an Astrophysicist';
      opacity: 0;
    }
    25% {
      content: 'an Astrophysicist';
      opacity: 1;
    }
    35% {
      content: 'an Astrophysicist';
      opacity: 1;
    }
    39% {
      content: 'an Astrophysicist';
      opacity: 0;
    }

    //   Fade out
    40% {
      content: 'a Musician';
      opacity: 0;
    }
    45% {
      content: 'a Musician';
      opacity: 1;
    }
    55% {
      content: 'a Musician';
      opacity: 1;
    }
    59% {
      content: 'a Musician';
      opacity: 0;
    }

    // Mathematician
    //   Face in
    60% {
      content: 'a Mathematician';
      opacity: 0;
    }
    65% {
      content: 'a Mathematician';
      opacity: 1;
    }
    //   Face out
    75% {
      content: 'a Mathematician';
      opacity: 1;
    }
    79% {
      content: 'a Mathematician';
      opacity: 0;
    }

    // Programmer
    //  Fade in 
    80% {
      content: 'a Web Developer';
      opacity: 0;
    }
    85% {
      content: 'a Web Developer';
      opacity: 1;
    }
    //  Fade out 
    95% {
      content: 'a Web Developer';
      opacity: 1;
    }
    100% {
      content: 'a Web Developer';
      opacity: 0;
    }
  }

</style>
