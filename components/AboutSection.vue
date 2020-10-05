<template>
  <div class="about">
    <div class="about--wrapper">
      <p class="about--header">About Me</p>
      <hr class="about--header-hr">
      <div class="about--container">


        <div class="about--left-col-wrapper">
          <div class="about--image-wrapper">
            <div class="about--image-block">
              <img class="about--image-im" src="profile.png" alt="">
            </div>
          </div>

        </div>
        <div class="about--right-col-wrapper">
            <div class="about--right-col-block">
              <div class="about--right-col-block-body"> 

                <p class="about--right-col-block-body-text" >
                  I am a <span class="highlight">Machine Learning Engineer</span> who also delves into the worlds of Data Engineering and Web Development. 
                  Currently, I am a Data Engineer at <span class="highlight redbull">Red Bull</span>, where I focus on creating scalable end-to-end machine learning models for <span class="highlight">Recommender Systems</span>.
                </p> 
                <p class="about--right-col-block-body-text" >
                  I graduated from the <span class="highlight">University of California, Los Angeles</span> with a BS in <span class="highlight">Astrophysics</span>. During that time, I completed four years 
                  of research as part of a research fellowship and was also a co author in a paper (details below).
                </p> 

              </div>
            </div>
        </div>


      </div>
    </div>
  </div>
</template>

<script>
  export default {
  }
  
</script>

<style lang="scss" scoped>

  $text-color: rgba(255, 255, 255, 0.616);
  $text-color-body: rgba(255, 255, 255, 0.835);
  $text-color-hover: rgba(255, 255, 255, 0.616);
  $hover-color: #5bbe5d21;
  $text-color-main: #64ffda;
  $text-title: rgb(223, 223, 223);
  $border-color-right: rgba(255, 255, 255, 0.329);
  $button-color: #64ffdb28;

  @keyframes fadeIn-about {
    0% { opacity: 0; transform: translateY(5%);}
    50% { opacity: 0; transform: translateY(5%);}
    100% { opacity: 1; transform: translateY(0%);}
  }

  .about--header, .about--header-hr {
    animation: fadeIn-about 1s ;
  }

  .about--container {
    animation: fadeIn-about 1.5s ;
  }

  .highlight {
    font-size: 115%;
    font-weight: 700;
    color: #efefef;
  }

  .redbull {
    color: rgba(251, 90, 104, 0.774);
  }

  .about--header-hr {
    margin: 0 auto;
    margin-bottom: 4%;
    width: 10%;
    border-color: $text-title;
  }

  .about {
    margin: 0 auto;
    padding: 8% 0;
    padding-bottom: 3%;
    text-align: center;
  }

  .about--wrapper {
    padding: 5% 15%;
    text-align: left;
    color: $text-title;
  }

  .about--header {
    padding: 3%;
    padding-bottom: 1%;
    text-align: center;
    font-size: 250%;
  }

  .about--container {
    display: flex;
    flex-direction: row;
    margin: 0 auto;
  }

  .about--left-col-wrapper {
    width: 25%;

    display: flex;
    justify-content: center;
    flex-direction: column;
  }

  .about--image-wrapper{

    display: flex;
    flex-direction: column;
    position: relative;

    .about--image-block-input {
      opacity: 0;
      background-color: $hover-color;
      position: absolute;
      padding: 2%;
      height: 35px;
    }

    .about--image-block {

      border-radius: 10px 0px 0px 10px;
      transition: all 0.5s;
      opacity: .8;

      &:hover {
        background-color: $hover-color;
        opacity: 1;
      }
    }
  }
  
  .about--right-col-wrapper {
    width: 75%;
    padding: 0 3%;
    display: inline-block !important;
    
    display: flex;
    justify-content: center;
    flex-direction: column;
  }

  .about--right-col-block {
    animation: fadeIn 1s;
    vertical-align: top;
  }

  .about--right-col-block-body {
    padding-bottom: 12%;
    font-size: 113%
  }

  .about--right-col-block-body-text {
    padding-bottom: 1%;
    letter-spacing: .7px;
  }

  .about--image-im {
    width: 100%;
    height: 100%;
    box-shadow: 12px 12px #ffefef47;
  }

  .about--image-block-text {
    padding: 15px;
    text-align: center;

    &:hover {
      color: $text-color-main;
    }
  }


  @media only screen and (max-width: 640px) {
    .about--wrapper {
      padding: 0;
    }
  }

</style>