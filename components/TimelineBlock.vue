<template>
  <div class="timeline">  

    <div class="timeline--outer-wrapper">
    
      <div class="timeline--header">
        <p class="timeline--header-title">
          Experience Timeline
        </p>
        <hr class="timeline--header-hr">
      </div>

      <div class="timeline--wrapper">
        <div class="timeline--sections">
          <div class="timeline--experience">
            
            <div class="timeline--experience-section"></div>


              <!-- TIMELINE BLOCKS -->
              <div class="timeline--experience-blocks">

                <div class="timeline--experience-block" v-for="(block, index) in blockData" :key="index"> 
                  <div :class="blockPosition(index)">
                    <p class="timeline--experience-title"> {{ block.title }} </p>
                    <p class="timeline--experience-subtitle"> {{ block.subtitle }} </p>
                    <p class="timeline--experience-date"> {{ block.date }} </p>
                    <p class="timeline--experience-body"> {{ block.body }} </p>
                  </div>
                </div>

              </div>


          </div>
        </div>
      </div>

    </div>

    <div class="timeline--downarrow">
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
    data() {
      return {
        blockData: [
          {
            title: 'Study of Filments Near the Galactic Center', 
            subtitle: 'Astrophysics Research: UCLA',
            date: "(2014-2018)",
            body: 'Conducted image processing and statistical analysis on data take by space telescopes WISE and SPITZER on gas filaments AFGL-5376 and Double Helix Nebula in the Galactic Center.'
          },
          {
            title: 'Radio Transient Classification', 
            subtitle: 'Astrophysics Research: UC Berkeley', 
            date: "(Summer 2016)",
            body: 'Used clustering techniques to classify fast radio transients. This work was done under the mentorship of Dr. Casey Law and Dr. Carl Heiles.'
          },
          {
            title: 'Search for Technosignature in TRAPPIST-1', 
            subtitle: 'Astrophysics Research: UCLA', 
            date: "2016-2017",
            body: 'Collected over three terabytes of observational data from the 100m Green Bank telescope to identify possible technosignatures near TRAPPIST-1.'
          },
          {
            title: 'Lead Machine Learning Engineer', 
            subtitle: 'Logos', 
            date: "(2017-now)",
            body: 'Leading the data science team toward researching, developing & experimenting machine learning models to solve problems in Natural Language Processing, personalized UI/UX, and business-oriented analysis.'
          },
          {
            title: 'Data Engineer', 
            subtitle: 'Red Bull', 
            date: "(2019-now)",
            body: 'Research, prototype, and deploy machine learning models on cloud services to personalize product recommendations as part of an end-to-end machine learning workflow.'
          },
        ],
      }
    },
    methods: {
      blockPosition(index) {
        if (index % 2 === 0)
          return 'timeline--experience-content-left'
        
        return 'timeline--experience-content-right' 
      }
    },  
  }
</script>

<style lang="scss" scoped>

  $block-color: #86968f21;
  $block-color-hover: #86968f4d;
  $title-color: #9bffe4f5;
  $subtitle-color: #e4f1ff;
  $body-color: #e4f1ff;
  $divider-color: #64ffdb94;

  @keyframes fadeIn-header {
    0% { opacity: 0; transform: translateY(5%);}
    50% { opacity: 0; transform: translateY(5%);}
    100% { opacity: 1; transform: translateY(0%);}
  }
  @keyframes fadeIn-wrapper {
    0% { opacity: 0; transform: translateY(5%);}
    50% { opacity: 0; transform: translateY(5%);}
    100% { opacity: 1; transform: translateY(0%);}
  }

  p {
    font-family: 'Quattrocento', serif;
  }

  .timeline--header {
    animation: fadeIn-header 1s;
  }

  .timeline--wrapper {
    animation: fadeIn-wrapper 1.5s;
  }

  .timeline--downarrow {
    padding: 80px;
  }



  // Outer wrappers
  .timeline {
    text-align: center;
    margin: 10% auto;
    letter-spacing: 1px;
    width: 1000px;
  }

  .timeline--header-title {
    font-size: 250%;
    padding: .6% 0;
    width: fit-content;
    margin: 10% auto;
    margin-bottom: 0%;
    color: rgb(223, 223, 223);
  }

  .timeline--header-hr {
    margin: 0 auto;
    margin-bottom: 4%;
    width: 100px;
    border-color: rgb(135 , 144, 145);
  }

  .timeline--wrapper {
    width: 100%;
    height: auto;
    color: #f2f2f2;
    position: relative;
    padding: 0;
  }

  .timeline--experience-block {
    display: flex;
    flex-direction: column;
    padding: 1%;
    // width: 883pxs;
  }

  .timeline--experience-section {

    &::before {
      content: '';
      position: absolute;
      top: 0;
      left: calc(50% - 1px);
      height: 100%;
      width: 2px;
      background: $divider-color;
      margin-top: 25px;
    }
  }

  .timeline--experience-blocks {

    padding-top: 25px;
    
    &::before{
      top: 24px;
      left: 100%;
      border-color: transparent;
      border-left-color: #1b1b1b;
    }
  }

  .timeline--experience-content-left {
    float: left;
    position: relative;
    background: $block-color;
    border-radius: 10px;
    margin-left: 0;
    padding: 1.5em;
    width: 45%;
    opacity: .85;
    transition: all .3s ease;
    margin-right: auto;

    &:hover {
      background: $block-color-hover;
    }

    &::before {
      content: '';
      position: absolute;
      top: 24px;
      right: 100%;
      left: 100%;
      height: 0;
      width: 0;
      border: 15px solid transparent;
      border-color: transparent;
      border-left-color: $block-color;
    }
  }

  .timeline--experience-content-right {
    float: right;
    position: relative;
    background: $block-color;
    border-radius: 10px;
    margin-left: 0;
    padding: 1.5em;
    width: 45%;
    opacity: .85;
    transition: all .3s ease;
    margin-left: auto;

    &:hover {
      background: $block-color-hover;
    }

    &::before {
      content: '';
      position: absolute;
      top: 24px;
      right: 100%;
      height: 0;
      width: 0;
      border: 15px solid transparent;
      border-color: transparent;
      border-right-color: $block-color;
    }
  }

  .timeline--experience-title {
    font-size: 145%;
    font-weight: 500;
    color: $title-color;
  }

  .timeline--experience-subtitle {
    font-size: 115%;
    padding-top: .4%;
    color: $subtitle-color;
  }

  .timeline--experience-date {
    font-size: 85%;
    padding-top: .4%;
    color: $subtitle-color;
  }

  .timeline--experience-body {
    font-size: 90%;
    letter-spacing: 1px;
    padding: 2.5% 0;
    text-align: left;
    color: $body-color;
  }

  @media only screen and (max-width: 1010px) {
    .timeline {
      text-align: center;
      margin: 10% auto;
      letter-spacing: 1px;
      width: 800px;
    }
  }

  @media only screen and (max-width: 810px) {
    .timeline {
      text-align: center;
      margin: 10% auto;
      letter-spacing: 1px;
      width: 70%;
    }

    .timeline--experience-block {
      padding: 15px;
    }

    .timeline--experience-content-left, .timeline--experience-content-right {
      float: left !important;
      position: relative;
      background: $block-color;
      border-radius: 10px;
      margin-left: 0;
      padding: 1.5em;
      width: 80%;
      opacity: .85;
      transition: all .3s ease;
      margin-left: 13%;
      margin-right: auto;
    }

    .timeline--experience-content-left::before {
      left: -30px;
      border: 15px solid transparent;
      border-color: transparent;
      border-right-color: $block-color;
    }

    .timeline--experience-section {

      &::before {
        content: '';
        position: absolute;
        top: 0;
        left: calc(10% - 1px);
        height: 100%;
        width: 2px;
        background: $divider-color;
      }
    }

  }

  @media only screen and (max-width: 560px) {
    .timeline {
      text-align: center;
      margin: 10% auto;
      letter-spacing: 1px;
      width: 70%;
      -webkit-transform: translateZ(0);
      transform: translateZ(0);
    }

    .timeline--header-title {
      font-size: 200%;
      padding: .6% 0;
      width: fit-content;
      margin: 10% auto;
      margin-bottom: 0%;
      color: rgb(223, 223, 223);
    }

    .timeline--experience-block {
      padding: 15px 0;
    }

    .timeline--experience-content-left, .timeline--experience-content-right {
      float: left !important;
      position: relative;
      background: $block-color;
      border-radius: 10px;
      margin-left: 0;
      padding: 1.5em;
      width: 100%;
      height: 200px;
      overflow: auto;
      opacity: .85;
      transition: all .3s ease;
      margin-left: 0;
      margin-right: auto;
    }

    .timeline--experience-content-left::before {
      left: -30px;
      border: 15px solid transparent;
      border-color: transparent;
      border-right-color: $block-color;
    }

    .timeline--experience-section {

      &::before {
        content: '';
        position: absolute;
        top: 0;
        left: calc(10% - 1px);
        height: 0%;
        width: 2px;
        background: $divider-color;
      }
    }

    .timeline--experience-title {
      font-size: 125%;
      font-weight: 500;
      color: $title-color;
    }

    .timeline--experience-subtitle {
      font-size: 105%;
      padding-top: .4%;
      color: $subtitle-color;
    }

    .timeline--experience-date {
      font-size: 65%;
      padding-top: .4%;
      color: $subtitle-color;
    }

    .timeline--experience-body {
      font-size: 70%;
      letter-spacing: 1px;
      padding: 2.5% 0;
      text-align: left;
      color: $body-color;
    }

  }

</style>