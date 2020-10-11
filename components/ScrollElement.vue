<template>
  <div>
    <div class="scroll--wrapper">
      <ul>
        <li class="scroll--elem" v-for="(header,index) in headers" :key="index">
          <vs-tooltip>
            <template #tooltip>{{ header.name }}</template>
            <vs-radio
              class="scroll--elem-li"
              v-model="scrollVal"
              vs-name="scroll"
              vs-value="about"
              v-scroll-to="{ el: header.id }"
            ></vs-radio>
          </vs-tooltip>
        </li>

        <div class="scroll--vertical-line"></div>

        <li class="scroll--elem">
          <a href="https://www.github.com/luisgc2116/">
            <Icons icon="github" />
          </a>
        </li>
        <li class="scroll--elem">
          <a href="https://www.linkedin.com/in/luisgchinchilla-garcia/">
            <Icons icon="linkedin" />
          </a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    headers: {
      type: Array,
      required: true,
    },
  },

  data() {
    return {
      scrollVal: "",
    };
  },
};
</script>

<style lang="scss" scoped>
#linkedin {
  fill: aquamarine;
}

.scroll--wrapper {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  position: fixed;
  right: 1%;
  top: 50%;
  z-index: 1000;
}

.scroll--elem {
  padding: 6px;
}

.scroll--vertical-line {
  height: 65px;
  border-left: 1px solid #9e9a9ab8;
  margin: 13px 0;
  margin-left: 40%;
}

ul {
  list-style-type: none;
}


  @media only screen and (max-width: 640px) {
    .scroll--wrapper {
      display: none;
    }
  }
</style>