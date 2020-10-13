<template>
  <div class="skills">
    <div class="skills--wrapper">
      <p class="skills--header">Skills and Experience</p>
      <hr class="skills--header-hr" />

      <div class="skills--container">
        <div class="skills--left-col-wrapper">
          <div class="skills--radio-wrapper">
            <div
              class="skills--radio-btn"
              v-for="(button, index) in buttons"
              :key="index"
              :class="{ active: picked == button.value }"
            >
              <input
                class="skills--radio-btn-input"
                type="radio"
                :id="button.id"
                :value="button.value"
                v-model="picked"
              />
              <label class="skills--radio-btn-label" :for="button.id">
                <div class="skills--radio-btn-label-block">
                  <p class="skills--radio-btn-text">
                    {{ button.text }}
                  </p>
                </div>
              </label>
            </div>
          </div>
        </div>
        <div class="skills--right-col-wrapper">
          <div
            class="skills--right-col-block"
            v-for="(tab, index) in tabs"
            v-show="picked === tab.value"
            :key="index"
          >
            <p class="skills--right-col-block-title">{{ tab.title }}</p>
            <div class="skills--right-col-block-body">
              <ul>
                <li
                  v-for="(text, index) in tab.body"
                  :key="index"
                  class="skills--right-col-block-body-li"
                >
                  <p> {{ text }} </p>
                </li>
              </ul>
            </div>

            <p class="skills--right-col-block-tags-title">Technologies:</p>
            <div class="skills--right-col-block-tags-block">
              <p
                class="skills--right-col-block-tag"
                v-for="(tag, ind) in tab.tags"
                :key="ind + tag"
              >
                {{ tag }}
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="skills--downarrow">
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
      picked: "One",
      buttons: [
        { text: "Machine Learning Engineering", id: "one", value: "One" },
        { text: "Data Engineering", id: "two", value: "Two" },
        { text: "Data Analysis", id: "three", value: "Three" },
        { text: "Web Development", id: "four ", value: "Four" },
      ],
      tabs: [
        {
          title:
            "For Machine Learning Engineering, some of my responsibilities have included:",
          value: "One",
          body: [
            "Actively researching and prototyping machine learning models to personalize product recommendations",
            "Deploying machine learning models on cloud services as part of an end-to- end machine learning workflow",
            "Developing & maintaining end-to-end machine learning pipelines that are scalable and cost effective",
          ],
          tags: [
            "Tensorflow",
            "Tensorflow Probability",
            "Scikit-Learn",
            "Numpy",
            "Pandas",
          ],
        },
        {
          title:
            "For Data Engineering, some of my responsibilities have included:",
          value: "Two",
          body: [
            "Deploying machine learning models on cloud services as part of an end-to- end machine learning workflow",
            "Collaborating with back-end engineers to integrate APIs and microser- vices with the platforms",
            "Creating efficient and scalable ETL pipelines for machine learning models",
          ],
          tags: [
            "SQL",
            "BigQuery",
            "Apache Beam",
            "Python",
            "Pandas",
            "Tensorflow",
            "Tensorflow-Extended",
            "GCP",
            "Docker",
          ],
        },
        {
          title:
            "For Data Analysis, some of my responsibilities have included:",
          value: "Three",
          body: [
            "Creating repeatable exploratory data analysis in Jupyter notebooks, with visualizations to aid the story-telling process of data",
            "Integrating model analysis using rigorous mathematical methods",
            "Analyzing machine learning performance",
          ],
          tags: [
            "SQL",
            "BigQuery",
            "Apache Beam",
            "Python",
            "Pandas",
            "Tensorflow",
            "LaTex",
          ],
        },
        {
          title:
            "For Web Development, some of my responsibilities have included:",
          value: "Four",
          body: [
            "Implementing major features that increased scalability while reducing latency",
            "Researching and integrating machine learning models to personalize UI",
          ],
          tags: [
            "Javascript",
            "Typescript",
            "HTML/Haml",
            "CSS/SCSS",
            "Vue",
            "Node.js",
          ],
        },
      ],
    };
  },

  methods: {
    valueTab(val) {
      return { color: this.picked === val ? "green" : "none" };
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
  font-family: 'Quattrocento', serif;
  color: white;
}

ul, ol {
  margin: 0 auto;
  padding-left: 10%;
  list-style: circle;
}

// Outer Wrappers
.skills {
  margin: 80px auto;
  padding: 50px 0;
  text-align: center;
}

.skills--wrapper {
  padding: 10% 25%;
  padding-bottom: 70px;
  text-align: left;
}

.skills--header {
  color: $text-title;
  padding: 3%;
  padding-bottom: 1%;
  text-align: center;
  font-size: 250%;
}

.skills--header-hr {
  margin: 0 auto;
  width: 10%;
  border-color: $text-title;
}

.skills--container {
  display: flex;
  flex-direction: row;
  margin: 0 auto;
  padding-top: 30px;
}

// RIGHT COLUMN
.skills--right-col-wrapper {
  width: 75%;
  padding: 0 3%;
  color: $text-color;
  display: inline-block !important;
  height: 450px;

  display: flex;
  justify-content: center;
  flex-direction: column;

  overflow: auto;
}

.skills--right-col-block-title {
  color: $text-color-body;
  padding: 2% 0;
}

.skills--right-col-block-body {
  padding-bottom: 12%;
}

.skills--right-col-block p {
  font-size: 16px;
}

.skills--right-col-block-body-li {
  padding: 1% 0;
}

.skills--right-col-block-tags-title {
  color: $text-color-body;
}

.skills--right-col-block-tags-block {
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  flex-wrap: wrap;
}

.skills--right-col-block-tag {
  margin: 2% 0;
  margin-right: 2%;
  padding: 1%;
  border: 1px solid rgb(75, 226, 75);
  border-radius: 5px;
  width: max-content;
  background-color: $button-color;
  color: $text-color-body;
}

// LEFT COLUMN
.skills--left-col-wrapper {
  width: 25%;
  padding: 0 3%;
  padding-bottom: 200px;
  color: $text-color;

  display: flex;
  justify-content: center;
  flex-direction: column;
}

.skills--radio-wrapper {
  display: flex;
  flex-direction: column;
  position: relative;

  .skills--radio-btn-input {
    opacity: 0;
    background-color: $hover-color;
    position: absolute;
    padding: 2%;
    height: 35px;
  }

  .skills--radio-btn {
    border-right: 2px solid $border-color-right;
    border-radius: 10px 0px 0px 10px;
    transition: all 0.5s;

    &:hover {
      background-color: $hover-color;
    }
  }
}

.active {
  background-color: $hover-color;
  color: $text-color-main;
  border-right: 2px solid $text-color-main !important;
}

.skills--radio-btn-text {
  padding: 15px;
  text-align: center;

  &:hover {
    color: $text-color-main;
  }
}




// Animations
@keyframes fadeIn-skills-header {
  0% {
    opacity: 0;
    transform: translateY(5%);
  }
  50% {
    opacity: 0;
    transform: translateY(5%);
  }
  100% {
    opacity: 1;
    transform: translateY(0%);
  }
}
@keyframes fadeIn-skills-container {
  0% {
    opacity: 0;
    transform: translateY(5%);
  }
  50% {
    opacity: 0;
    transform: translateY(5%);
  }
  100% {
    opacity: 1;
    transform: translateY(0%);
  }
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
.skills--header,
.skills--header-hr {
  animation: fadeIn-skills-header 1s;
}

.skills--container {
  animation: fadeIn-skills-container 1.5s;
}

.skills--right-col-block {
  animation: fadeIn 1s;
  vertical-align: top;
}



@media only screen and (max-width: 1450px) {
  .skills--wrapper {
    padding: 10% 10%;
  }
}

@media only screen and (max-width: 1050px) {
  .skills--wrapper {
    padding: 10% 0%;
  }
}

@media only screen and (max-width: 812px) {

  .skills {
    padding: 50px 0;
  }

  .skills--wrapper {
    padding: 10% 0%;
  }

  .skills--container {
    display: flex;
    flex-direction: column;
    margin: 0 auto;
  }

  .skills--left-col-wrapper {
    width: 100%;
    padding: 0 3%;
    padding-bottom: 15px;
  }

  .skills--radio-wrapper {
    display: flex;
    flex-direction: row;
    position: relative;
    border: 2px solid rgba(255, 255, 255, 0.329);
  }

  .skills--radio-btn {
    flex-basis: 25%;
    flex-grow: 0;
    line-height: 100% !important;
    overflow:visible;
    border-radius: 0 !important;

    &:nth-child(4) {
      border-right: none !important;
    }
  }

  .active {
    border-right: 2px solid rgba(255, 255, 255, 0.329) !important;
    border-bottom: 2px solid #64ffda !important;
  }

  .skills--right-col-wrapper {
    margin: 0 auto;
    padding-top: 10px;
    width: 100% !important;
  }

}

@media only screen and (max-width: 600px) {

  .skills--wrapper {
    padding: 10% 0%;
  }

  .skills--header {
    font-size: 30px;
  }

  .skills--container {
    display: flex;
    flex-direction: column;
    margin: 0 auto;
  }

  .skills--left-col-wrapper {
    width: 100%;
    padding: 0 3%;
    padding-bottom: 15px;
  }

  .skills--radio-wrapper {
    display: flex;
    flex-direction: row;
    position: relative;
    border: 2px solid rgba(255, 255, 255, 0.329);
  }

  .skills--radio-btn {
    flex-basis: 25%;
    flex-grow: 0;
    line-height: 40% !important;
    border-radius: 0 !important;
  }
  
  .skills--radio-btn-text {
    visibility: hidden !important;
    padding: 0;
  }

  .active {
    border-right: none !important;
    border-bottom: 2px solid #64ffda !important;
  }

  .skills--right-col-block p {
    font-size: 16px;
  }

}

</style>