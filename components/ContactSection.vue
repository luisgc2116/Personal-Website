<template>
  <div class="contact">
    <div class="contact--wrapper">
      <p class="contact--header">Contact Me</p>
      <hr class="contact--header-hr">
      <div class="contact--container">

        <div class="contact--col-wrapper">
            <div class="contact--col-block">
              <div class="contact--col-block-body"> 

                <p class="contact--col-block-body-text" >
                  I'm always open for discussions, so feel free to contact me! 
                </p> 

                <div class="contact--col-block-body-buttons">
                  <a class="contact--col-block-body-button" href="mailto:luisgc2116@gmail.com">Email</a> 
                  <a class="contact--col-block-body-button" href="Luis_GC_Resume.pdf" download="">Resume</a> 
                </div>

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
  $border-color: rgba(255, 255, 255, 0.329);
  $button-color: #64ffdb28;

  @keyframes fadeIn-contact {
    0% { opacity: 0; transform: translateY(5%);}
    50% { opacity: 0; transform: translateY(5%);}
    100% { opacity: 1; transform: translateY(0%);}
  }

  .contact--header, .contact--header-hr {
    animation: fadeIn-contact 1s;
  }

  .contact--container {
    animation: fadeIn-contact 1.5s;
    text-align: center;
  }

  .highlight {
    font-size: 115%;
    font-weight: 700;
    color: #efefef;
  }

  .contact--header-hr {
    margin: 0 auto;
    margin-bottom: 4%;
    width: 10%;
    border-color: $text-title;
  }

  .contact {
    margin: 0 auto;
    padding: 8% 0;
    padding-bottom: 3%;
    text-align: center;
  }

  .contact--wrapper {
    padding: 5% 15%;
    padding-bottom: 16%;
    text-align: left;
    color: $text-title;
  }

  .contact--header {
    padding: 3%;
    padding-bottom: 1%;
    text-align: center;
    font-size: 250%;
  }

  .contact--container {
    display: flex;
    flex-direction: row;
    margin: 0 auto;
  }

  .contact--image-wrapper{

    display: flex;
    flex-direction: column;
    position: relative;

    .contact--image-block-input {
      opacity: 0;
      background-color: $hover-color;
      position: absolute;
      padding: 2%;
      height: 35px;
    }

    .contact--image-block {

      border-radius: 10px 0px 0px 10px;
      transition: all 0.5s;
      opacity: .8;

      &:hover {
        background-color: $hover-color;
        opacity: 1;
      }
    }
  }
  
  .contact--col-wrapper {
    padding: 0 3%;
    display: inline-block !important;
    
    display: flex;
    justify-content: center;
    flex-direction: column;
    width: 70%;
    margin: 0 auto;
  }

  .contact--col-block {
    animation: fadeIn 1s;
    vertical-align: top;
  }

  .contact--col-block-body {
    padding-bottom: 12%;
    font-size: 113%
  }

  .contact--col-block-body-text {
    padding-bottom: 6%;
    letter-spacing: .7px;
  }

  .contact--col-block-body-button {
    display: flex;
    flex-direction: row;
    white-space: pre;
  }

  .contact--col-block-body-button {
    display: inline-block;
    border-radius: 4px;
    border: 1px solid #c4fff1;
    color: #c4fff1;
    text-decoration: none;
    padding: 10px 30px;
    background-color: #242524;
  }

  .contact--image-im {
    width: 100%;
    height: 100%;
    box-shadow: 12px 12px #ffefef47;
  }

  .contact--image-block-text {
    padding: 15px;
    text-align: center;

    &:hover {
      color: $text-color-main;
    }
  }


  @media only screen and (max-width: 640px) {
    .contact--wrapper {
      padding: 0;
    }
  }

</style>