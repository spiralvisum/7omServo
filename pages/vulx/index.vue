<template>
  <div>
    <Servonav />
    <div class="black-section-wrapper first-section-wrapper">
      <b-container fluid class="position-absolute black-section">
        <b-row class="no-gutters top-row">
          <b-col cols="4" sm="3" lg="2">
            <b-row no-gutters>
              <b-col auto class="text-center">
                <font-awesome-icon :icon="['fab', 'facebook']" class="fb-blue social-media" />
              </b-col>
              <b-col auto class="text-center">
                <font-awesome-icon :icon="['fab', 'twitter']" class="vulx-green social-media" />
              </b-col>
              <b-col auto class="text-center">
                <font-awesome-icon :icon="['fab', 'instagram']" class="insta-orange social-media" />
              </b-col>
            </b-row>
            <b-row>
              <b-col class="text-center">
                <div class="contactnum">
                  <strong>
                    (760) 848-733
                  </strong>
                </div>
              </b-col>
            </b-row>
          </b-col>
        </b-row>
      </b-container>
      <b-container fluid class="black-section">
        <b-row>
          <b-col
            class="text-center"
            cols="4"
            sm="6"
            md="8"
            offset-md="2"
            offset-sm="3"
            offset="4"
          >
            <b-img src="~/assets/headerlogogreen.png" fluid alt="Fluid image" />
          </b-col>
        </b-row>
        <b-row no-gutters>
          <b-col
            class="text-center"
          >
            <h1>
              <span class="contactnum">
                Premium Substrate Amendment
              </span>
            </h1>
          </b-col>
        </b-row>
      </b-container>
      <b-container fluid class="mt-5 black-section">
        <b-carousel
          id="carousel-fade"
          v-model="slide"
          :interval="0"
          style="text-shadow: 0px 0px 2px #000"
          controls
          img-width="893"
          img-height="762"
        >
          <b-carousel-slide
            img-src="~/assets/diagram1.png"
            rel="preload"
          />
          <b-carousel-slide
            img-src="~/assets/diagram1.png"
          />
          <b-carousel-slide
            img-src="~/assets/diagram1.png"
          />
        </b-carousel>
      </b-container>
    </div>
    <div class="section-wrapper">
      <b-container fluid>
        <b-row>
          <b-col
            lg="6"
            data-aos="slide-right"
            data-aos-offset="200"
            data-aos-duration="500"
            data-aos-mirror="true"
            data-aos-once="true"
          >
            <div class="py-4 px-1 hero-text">
              <span class="vulx-green">
                VULX
              </span>
              IS MADE OF A BLEND OF NATURALLY-OCCURRING ALUMINUM HYDRO SILICATE MINERALS ENHANCED AND ACTIVATED OUR PROPRIETARY PROCESSING TECHNIQUES.
            </div>
          </b-col>
          <b-col
            lg="6"
            data-aos="slide-left"
            data-aos-offset="200"
            data-aos-duration="500"
            data-aos-mirror="true"
            data-aos-once="true"
            class="oas-init"
          >
            <div class="py-4 px-1 hero-text">
              <span class="fb-blue">
                THESE MINERALS
              </span>
              ARE FREQUENTLY USED TO EMEDIATE TOXIC HEAVY METALS AND ACT AS ION EXCHANGERS, BECAUSE OF THEIR INCREDIBLE CATION ADSORPTION AND EXCHANGE CAPABILITIES
            </div>
          </b-col>
        </b-row>
        <b-row>
          <b-col
            lg="6"
            data-aos="slide-right"
            data-aos-offset="200"
            data-aos-duration="500"
            data-aos-mirror="true"
            data-aos-once="true"
            class="oas-init"
          >
            <div class="py-4 px-1 hero-text">
              <span class="insta-orange">
                A SINGLE APPLICATION
              </span>
              WILL DELIVER RESULTS FOR YEARS TO COME.
            </div>
          </b-col>
          <b-col
            lg="6"
            data-aos="slide-left"
            data-aos-offset="200"
            data-aos-duration="500"
            data-aos-mirror="true"
            data-aos-once="true"
            class="oas-init"
          >
            <div class="py-4 px-1 hero-text hero-text-nobold">
              * NOT A SIGNIFICANT SOURCE OF NPK OR TRACE MINERALS
              <br>
              * NOT A SILICA ADDITIVE
              <br>
              <b-img src="~/assets/greenicon.png" class="my-2" />
            </div>
          </b-col>
        </b-row>
      </b-container>
      <b-container fluid>
        <b-row>
          <b-col>
            <p>more data</p>
          </b-col>
        </b-row>
      </b-container>
    </div>
  </div>
</template>

<style>
  .social-media{
    font-size: 8vw;
  }
  .vulx-green{
    color: rgb(69, 174, 83);
  }
  .fb-blue{
    color: rgb(22, 199, 255);
  }
  .hero-text-nobold {
    font-weight: 300 !important;
  }
  .insta-orange{
    color: rgb(243, 148, 73);
  }
  .contactnum {
    font-size: 4vw;
    color: white;
    padding-top:30px;
  }
  .hero-text{
    font-size: 5vw;
    font-weight: 700;
    text-align: center;
  }
  @media only screen and (min-width: 576px) {
      .social-media {
          font-size: 5vw;
      }
      .contactnum {
        font-size: 3.1vw;
      }
      .hero-text {
        font-size: 3.5vw;
      }
  }
  @media only screen and (min-width: 768px) {
      .social-media {
          font-size: 5vw;
      }
      .contactnum {
        font-size: 3.1vw;
      }
      .hero-text {
        font-size: 2.5vw;
      }
  }
  @media only screen and (min-width: 992px) {
      .social-media {
          font-size: 4vw;
      }
      .contactnum {
        font-size: 2.1vw;
      }
      .hero-text {
        font-size: 1.9vw;
      }
  }
  @media only screen and (min-width: 1200px) {
      .social-media {
          font-size: 3.1vw;
      }
      .contactnum {
        font-size: 2.1vw;
      }
  }
  img.img-fluid.w-100.d-block {
      max-width: 893px;
      max-height: 762px;
      margin: 0px auto;
  }
  .black-section, .black-section-wrapper{
    background-color: black;
  }
  .section-wrapper {
    padding:20px 0px;
    overflow: hidden;
  }
  .first-section-wrapper {
    padding-bottom:20px;
    overflow: hidden;
  }

</style>

<script>
import Vue from 'vue'
import { BootstrapVue, LayoutPlugin } from 'bootstrap-vue'
import AOS from 'aos'
import Servonav from '@/components/Servonav'

Vue.use(BootstrapVue, LayoutPlugin, AOS)

export default {
  components: {
    Servonav
  },
  data () {
    return {
      slide: 0,
      sliding: null
    }
  },
  mounted () {
    if (process.browser) {
      AOS.init()
    }
  },
  head () {
    return {
      title: 'Vulx Soil Amendment Made from Volcanic Mineral Mix',
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        [
          {
            hid: 'description',
            name: 'description',
            content: 'Vulx is a volcanic mineral-based soil amendment mixture designed to increase yield while decreasing required fertilizer and water use.'
          }
        ]
      ]
    }
  }
}

</script>
