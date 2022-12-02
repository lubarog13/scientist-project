<template>
  <v-lazy
      v-model="isActive"
      :options="{
          threshold: .5
        }"
      min-height="200"
      transition="fade-transition"
  >
  <div class="page "
  >
    <div class="page_container" v-animate-onscroll="'animated flipInX'" data-animate-onscroll-offset="100">
    <h2 :id="'title-'+pageNumber">{{titles[pageNumber]}}</h2>
    <div class="content" v-html="text[pageNumber]"></div>
    </div>
  </div>
  </v-lazy>
</template>

<script>
import textMixin from "../mixins/textMixin";
export default {
  name: "InfoPage",
  mixins: [textMixin],
  props: {
    pageNumber: {
      type: Number,
      required: true
    }
  },
  data() {
    return {
      isActive: false
    }
  }
}
</script>

<style scoped>
.page {
  width: 100%;
  padding: 40px;
  animation: 1.5s fadeIn ease;
}
.page_container {
  width: 100%;
  max-width: 1300px;
  margin: auto;
}
h2 {
  font-size: 36px;
  padding-left: 30px;
  margin-bottom: 30px;
  border-left: 4px solid #05336e;
}
.content {
  width: 100%;
  display: flex;
  align-items: center;
}
::v-deep ul {
  margin-left: 20px;
}
::v-deep .content-left {
  width: 60%;
  margin-right: 40px;
}

::v-deep .content-right {
  width: calc(40% - 30px);
}

::v-deep ul,
::v-deep p {
  font-size: 20px;
  line-height: 24px;
}
::v-deep a {
  word-break: break-all;
  text-decoration: none;
  color: #0c64d5;
}

::v-deep img {
  object-fit: cover;
  width: 100%;
  box-shadow: 4px 4px 10px;

}

@keyframes fadeIn {
  from {
    offset: 0;
  }
  to {
    offset: 1;
  }
}

@media (max-width:750px) {
  .content {
    flex-direction: column;
  }
  ::v-deep .content-left {
    width: 100%;
    margin-right: 0;
    margin-bottom: 20px;
  }
  ::v-deep .content-right {
    width:100%;
  }
  ::v-deep ul,
  ::v-deep p {
    font-size: 16px;
    line-height: 20px;
  }
}
</style>