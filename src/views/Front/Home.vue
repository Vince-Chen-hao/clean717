<template>
  <section class="HomeSection">
    <!-- 彈出式蓋板 -->
    <!-- <PopupNews></PopupNews> -->
    <!-- 點擊滑動置頂 -->
    <div id="SliderTop">
      <img class="SliderTop-img" src="../../assets/images/up3.png" alt="cart" />
    </div>

    <!-- SHOWCASE SLIDER -->
    <section id="showcase" style="margin-top:90px">
      <div id="carouselExampleIndicators" class="carousel slide" data-ride="carousel">
        <ol class="carousel-indicators">
          <li data-target="#carouselExampleIndicators" data-slide-to="0" class="active"></li>
          <li data-target="#carouselExampleIndicators" data-slide-to="1"></li>
          <li data-target="#carouselExampleIndicators" data-slide-to="2"></li>
        </ol>
        <div class="carousel-inner">
          <div class="carousel-item active  w-100">
            <img src="../../assets/images/cover01.png" class="d-block w-100" alt="..." />
          </div>
          <div class="carousel-item">
            <img src="../../assets/images/cover02.jpg" class="d-block w-100" alt="..." />
          </div>
          <div class="carousel-item">
            <img src="../../assets/images/cover03.jpg" class="d-block w-100" alt="..." />
          </div>
        </div>
        <a
          class="carousel-control-prev"
          href="#carouselExampleIndicators"
          role="button"
          data-slide="prev"
        >
          <span class="carousel-control-prev-icon" aria-hidden="true"></span>
          <span class="sr-only">Previous</span>
        </a>
        <a
          class="carousel-control-next"
          href="#carouselExampleIndicators"
          role="button"
          data-slide="next"
        >
          <span class="carousel-control-next-icon" aria-hidden="true"></span>
          <span class="sr-only">Next</span>
        </a>
      </div>
    </section>

    <section id="CategoryList">
      <div class="container mt-5">
        <ul class="row mr-4 category-list justify-content-around">
          <li
            class="col-md-3 col-6"
            v-for="(category, key) in categories"
            :key="key"
            @click.prevent="linkProductlist"
          >
            <i :class="category.icon" class="py-auto"></i>
            <ul style="list-style-type:none ">
              <li>{{ category.name }}</li>
              <li>{{ category.title }}</li>
            </ul>
          </li>
        </ul>
      </div>
    </section>

    <!-- Mission HEAD -->
    <section id="mission-head-section" style="background:#1f2d35">
      <div class="container">
        <div class="row">
          <div class="col text-center py-5 text-light">
            <h1 class="display-4">宗旨</h1>
            <p class="lead">
              我們希望一台上萬元的吸塵器能夠透過服務讓它持續維持高品質的吸塵效果，
              並致力於將吸塵器做到百分百清潔，讓您每次清潔完後都有一種收到新機器的感動
            </p>
            <!--添加.lead讓段落突出，常與display合用-->
            <a href="#" class="btn btn-outline-info mt-4">更多</a>
          </div>
        </div>
      </div>
    </section>

    <section id="ProductsType">
      <div class="container my-5">
        <h3>清潔圖片</h3>
        <hr />
        <div class="row">
          <div class="col-sm-4 my-1">
            <div class="l-bg-cover rounded type01 img-thumbnail">
              <router-link class="black-cover" to="/product_list">
                <span class="h4">專業</span>
              </router-link>
            </div>
          </div>
          <div class="col-sm-4 my-1">
            <div class="l-bg-cover rounded type02 img-thumbnail">
              <router-link class="black-cover" style="text-decoration: none" to="/product_list">
                <span class="h4">極淨</span>
              </router-link>
            </div>
          </div>
          <div class="col-sm-4 my-1">
            <div class="l-bg-cover rounded type03 img-thumbnail">
              <router-link class="black-cover" style="text-decoration: none" to="/product_list">
                <span class="h4">磨砂</span>
              </router-link>
            </div>
          </div>
        </div>
        <div class="row mb-4">
          <div class="col-md-6 my-1">
            <div class="l-bg-cover rounded type04 img-thumbnail">
              <router-link class="black-cover" to="/product_list">
                <span class=" h4">北歐家居</span>
              </router-link>
            </div>
          </div>
          <div class="col-md-6 my-1">
            <div class="l-bg-cover rounded type05 img-thumbnail">
              <router-link class="black-cover" style="text-decoration: none" to="/product_list">
                <span class="h4">典雅皇室</span>
              </router-link>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="VideoIntro">
      <div class="bg-light">
        <div class="container">
          <div class="row align-items-center justify-content-center py-3">
            <div class="col-lg-7 p-3">
              <div class="embed-responsive embed-responsive-16by9">
                <iframe
                  width="560"
                  height="315"
                  src="https://www.youtube.com/embed/he9Vb75mAhw?autoplay=1"
                  frameborder="0"
                  allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
                  allowfullscreen
                ></iframe>
              </div>
            </div>
            <div class="col-lg-5 p-3">
              <h5 class="text-center">服務項目</h5>
              <hr />
              <ul>
                <li></li>
                <li></li>
                <li></li>
                <li></li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </section>
    <Shoppingcart />
  </section>
</template>

<script>
import $ from "jquery";
import PopupNews from "../../components/Front/PopupNews.vue";
import Shoppingcart from "../../components/Front/Shoppingcart.vue";

export default {
  components: {
    PopupNews,
    Shoppingcart
  },

  data() {
    return {
      categories: [
        { name: "SHIPPING", title: "交寄方式", icon: "fas fa-shipping-fast fa-2x" },
        { name: "NEWS", title: "最新消息", icon: "fas fa-book-open fa-2x" },
        { name: "CONTACT", title: "立即聯繫", icon: "fas fa-mobile-alt fa-2x" },
        { name: "ABOUT", title: "關於我們", icon: "fas fa-users fa-2x" }
      ]
    };
  },
  methods: {
    linkProductlist() {
      const vm = this;
      vm.$router.push({ path: "/product_list" });
    },
    subscriptComplete() {
      this.$store.dispatch("updateMessage", {
        message: "訂閱成功，謝謝你的支持",
        status: "success"
      });
    }
  },
  created() {
    $(() => {
      $("#SliderTop").click(() => {
        $("html,body").animate({ scrollTop: 0 }, "slow");
        return false;
      });
    });
  }
};
</script>

<style lang="scss" scoped>
.SliderTop-img {
  position: fixed;
  bottom: 30px;
  right: 40px;
  width: 40px;
  background: rgb(241, 237, 206);
  border-radius: 70%;
  border-width: 2px;
  border-style: dotted;
  border-color: rgb(214, 210, 187);
  padding: 5px;
  z-index: 1000;
}

.l-bg-cover {
  background-position: center center;
  background-size: cover;
}

.carousel-item {
  height: 500px;

  @media (max-width: 768px) {
    height: 300px;
  }
  @media (max-width: 575.98px) {
    height: 200px;
  }
}

.carousel01 {
  background-image: url("../../assets/images/cover01.png");
}
.carousel02 {
  background-image: url("../../assets/images/cover02.jpg");
}
.carousel03 {
  background-image: url("../../assets/images/cover03.jpg");
}

.inside-banner {
  width: 100%;
  position: relative;
  padding-bottom: 40%;
  background-size: cover;
  background-position: center center;
  p {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    color: #fff;
    opacity: 0.8;
    font-size: 40px;
    text-shadow: 0px 2px 10px rgba(0, 0, 0, 0.3);

    @media (max-width: 575.98px) {
      margin-top: 20px;
      font-size: 28px;
    }
  }
}

.category-list {
  ul {
    padding-left: 20px;
  }

  > li {
    //只改變下一層的子元素li，不再往內層作用
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 15px 0;
    transition: all 0.5s;
    cursor: pointer;
    color: rgb(150, 145, 145);
    white-space: nowrap;
    @media (max-width: 575.98px) {
      font-size: 10px;
      padding: 10px 0px;
    }

    &:hover,
    &:active {
      background-color: rgb(218, 215, 188);
      color: rgb(173, 136, 80);
    }
  }
  > li:not(:last-child) {
    //作用在最後一個子元素
    border-right: rgb(228, 224, 224) solid 1px;
    @media (max-width: 768px) {
      border: none;
    }
  }
}

.type01 {
  background-image: url("../../assets/images/Home_img.jpg");
}
.type02 {
  background-image: url("../../assets/images/Home_img2.jpg");
}
.type03 {
  background-image: url("../../assets/images/image13.jpg");
}
.type04 {
  background-image: url("../../assets/images/image15.jpg");
}
.type05 {
  background-image: url("../../assets/images/image14.jpg");
}

.black-cover {
  display: flex;
  justify-content: center;
  align-items: center;
  border: 1.5px solid rgba(255, 255, 255, 0.5);
  text-decoration: none;
  height: 280px;
  position: relative;

  span {
    display: none;
  }

  &:hover span {
    z-index: 2;
    display: block;
    color: white;
  }

  &::before {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 1;
    opacity: 0;
    background-color: rgba(0, 0, 0, 0.5);
    transition: all 1s;
  }

  &:hover::before {
    opacity: 1;
  }

  @media (max-width: 575.98px) {
    span {
      display: block;
      color: rgb(255, 255, 255);
      z-index: 2;
    }

    &::before {
      content: "";
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: 1;
      opacity: 0.7;
      background-color: rgba(156, 152, 152, 0.5);
    }
  }
}

.NewsIist {
  //淡出動畫效果
  @keyframes flicker {
    0% {
      opacity: 1;
    }
    50% {
      opacity: 0.3;
    }
    100% {
      opacity: 1.2;
    }
  }
  .flicker {
    animation: flicker 1.5s linear infinite;
    color: #f7d202;
  }
  p {
    line-height: 10px;
  }
}

.font-intro {
  text-indent: 2em;
}

.brand-text {
  padding: 20px;
  background-color: rgb(187, 173, 133);
}

@media (min-width: 767px) {
  .brand-block {
    position: relative;
    height: 450px;
    .brand-img {
      margin-top: 55px;
      height: 350px;
      position: absolute;
      right: 0;
      z-index: 1;
    }
    .brand-text {
      height: 400px;
      position: absolute;
      left: 0;
      padding: 20px 130px 20px 40px;
    }
  }
}

.channel-form {
  padding: 2rem;
  background: url("../../assets/images/contact01.png");
  background-size: cover;
  text-align: center;
  @media (max-width: 767px) {
    padding: 3rem 1rem;
  }
  h4 {
    color: white;
    text-shadow: 1px 1px 1px rgb(3, 50, 56);
  }
  p {
    font-size: 15px;
  }
}

.form-control {
  padding: 0.3rem;
  border-radius: 5px;
}
</style>
