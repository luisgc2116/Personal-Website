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
    <div class="about--downarrow">
      <DownArrow v-scroll-to="{ el: scrollTo }" />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    scrollTo: {
      type: String,
      required: true,
    },
  },
};
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

  p {
    color: rgba(255, 255, 255, 0.842);
  }

  .about--downarrow {
    padding-top: 80px;
  }

  .about {
    max-width: 1340px;
    margin: 150px auto;
    padding: 30px 0;
    text-align: center;
  }

  .about--wrapper {
    padding: 0;
    text-align: left;
    color: $text-title;
  }

  .about--header {
    padding: 3%;
    padding-bottom: 0;
    text-align: center;
    font-size: 35px;
    font-family: 'Quattrocento', serif;
  }

  .about--header-hr {
    margin: 0 auto;
    width: 60px;
    border-color: $text-title;
  }

  .about--container {
    display: flex;
    flex-direction: column;
    margin: 0 auto;
    padding-top: 50px;
  }

  .about--left-col-wrapper {
    width: 30%;
    display: flex;
    justify-content: center;
    flex-direction: column;
    margin: 0 auto;
    padding-bottom: 40px;
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
      opacity: 1;

      &:hover {
        background-color: $hover-color;
        opacity: .8;
      }
    }
  }

  .about--image-im {
    width: 100%;
    height: 100%;
    box-shadow: 5px 5px rgb(255 239 239 / 21%), 10px 10px rgb(255 239 239 / 16%), 15px 15px rgb(255 239 239 / 22%);
  }
  
  .about--right-col-wrapper {
    width: 100%;
    padding: 0 3%;
    margin: 0 auto;
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
    padding-bottom: 15px;
  }

  .about--right-col-block-body-text {
    padding-bottom: 20px;
    letter-spacing: .4px;
    font-size: 18px;
    font-family: 'Quattrocento', serif;
  }

  .highlight {
    font-size: 115%;
    font-weight: 700;
    color: #efefefe5;
    // box-shadow: 0px 2px rgb(255 239 239 / 33%), 0px 4px rgb(255 239 239 / 16%);
  }

  .redbull {
    color: rgba(250, 226, 228, 0.774);
  }

  .about--image-block-text {
    padding: 15px;
    text-align: center;

    &:hover {
      color: $text-color-main;
    }
  }

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

  @media only screen and (min-width: 1221px) and (max-width: 1450px)  {
    .about {
      max-width: 1340px;
      margin: 100px 50px;
      text-align: center;
    }
  }

  @media only screen and (min-width: 1040px) and (max-width: 1221px)  {
    .about {
      max-width: 1340px;
      margin: 100px 50px;
      text-align: center;
    }

    .about--right-col-block-body-text {
      padding-bottom: 20px;
      letter-spacing: .4px;
      font-size: 16px;
    }

    .about--left-col-wrapper {
      width: 370px;
    }
  }

  @media only screen and (min-width: 930px) and (max-width: 1040px)  {

    .about {
      margin: 100px 50px;
    }

    .about--left-col-wrapper {
      width: 330px;
    }

    .about--right-col-wrapper {
      width: 90%;
    }

    .about--right-col-block-body-text {
      padding-bottom: 20px;
      letter-spacing: .4px;
      font-size: 16px;
    }

    .about--downarrow {
      padding-top: 50px;
    }
  }

  @media only screen and (min-width: 500px) and (max-width: 930px)  {

    .about {
      margin: 100px 50px;
    }

    .about--container {
      display: flex;
      flex-direction: column;
      margin: 0 auto;
      padding-top: 50px;
    }

    .about--left-col-wrapper {
      width: 300px;
      margin: 0 auto;
      padding-bottom: 40px;
    }

    .about--right-col-wrapper {
      width: 100%;
    }

    .about--right-col-block-body-text {
      padding-bottom: 20px;
      letter-spacing: .4px;
      font-size: 16px;
    }

    .about--downarrow {
      padding-top: 50px;
    }
  }

  @media only screen and (max-width: 500px)  {

    .about {
      margin: 50px 20px;
      padding: 50px 0;
    }

    .about--container {
      display: flex;
      flex-direction: column;
      margin: 0 auto;
      padding-top: 50px;
    }

    .about--left-col-wrapper {
      max-width: 300px;
      width: 90%;
      margin: 0 auto;
      padding-bottom: 40px;
    }

    .about--right-col-wrapper {
      width: 100%;
    }

    .about--right-col-block-body-text {
      padding-bottom: 20px;
      letter-spacing: .4px;
      font-size: 90%;
    }

    .about--downarrow {
      padding-top: 10px;
    }
  }

</style>