<script lang="ts" setup>
import PopularTags from './components/PopularTags.vue'
import { useUserStore } from '@/stores/useUserStore'
import type { ArticleListProps, ArticleToggleOptions } from '@/types'
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/css';
import 'swiper/css/navigation';
import 'swiper/css/pagination';
import { Navigation, Pagination, Autoplay } from 'swiper/modules';
const store = useUserStore()
const getOptionsForLabel: Record<string, { author?: string; tag?: string }> = {
  'Global Feed': {},
  'Your Feed': { author: store.userInfo?.username }
}
const activeLabel = ref(store.isLoggedIn ? 'Your Feed' : 'Global Feed')
const articleListProps = ref<ArticleListProps>(getOptionsForLabel[activeLabel.value])
const articleToggleOptions = ref<ArticleToggleOptions[]>([
  {
    label: 'Your Feed',
    show: store.isLoggedIn,
  },
  { label: 'Global Feed' },
])

const categories = ref([
  {
    title: "Tv Televisions",
    image: "/media/webps/jpg/media/wysiwyg/magebig/catalog/catalog-01.webp",
    items: ["Smart TV", "4K Ultra HD TVs", "LED TVs", "OLED TVs", "Accessories"]
  },
  {
    title: "Air Conditioners",
    image: "/media/webps/jpg/media/wysiwyg/magebig/catalog/catalog-02.webp",
    items: ["Type Hanging On Wall", "Type Erect", "Type Hanging On Celling", "Accessories"]
  },
  {
    title: "Washing Machine",
    image: "/media/webps/jpg/media/wysiwyg/magebig/catalog/catalog-03.webp",
    items: ["Type Horizontal", "Type Vertical", "Type Drying Clothes"]
  },
  {
    title: "Audios & Theaters",
    image: "/media/webps/jpg/media/wysiwyg/magebig/catalog/catalog-04.webp",
    items: ["Speakers", "Home Theater System", "Wireless Audio", "Headphone", "Accessories"]
  },
  {
    title: "Office Electronics",
    image: "/media/webps/jpg/media/wysiwyg/magebig/catalog/catalog-05.webp",
    items: ["Printers", "Store & Business", "Scanners", "Projectors", "Phones"]
  },
  {
    title: "Car Electronics",
    image: "/media/webps/jpg/media/wysiwyg/magebig/catalog/catalog-06.webp",
    items: ["Audio & Video", "Radar Detector", "Car Security Products", "Vehicle GPS Tracking", "Portable CB Radios"]
  }
]);

function handleTabClick() {
  if (['Your Feed', 'Global Feed'].includes(activeLabel.value)) {
    if (articleToggleOptions.value.length === 3) {
      articleToggleOptions.value.pop()
    }

    articleListProps.value = getOptionsForLabel[activeLabel.value]
  }
}
function handleTagClick(tag: string) {
  activeLabel.value = tag
  articleListProps.value = { tag }
  if (articleToggleOptions.value.length === 2) {
    articleToggleOptions.value.push({
      label: tag,
      icon: true,
    })
  } else {
    articleToggleOptions.value[2].label = tag
  }
}


</script>

<template>
  <main id="maincontent" class="page-main">
    <div id="contentarea" tabindex="-1"></div>
    <div class="main-slider-full">
      <div class="container main-slider-container">
        <div class="widgetplus widgetplus-block slider-0" id="widgetplus-block-2733911325">
          <div class="main-slider-v2">
            <div class="row">
              <div class="col-12 col-xl-8">
                <div class="slider">
                  <Swiper :modules="[Navigation, Pagination, Autoplay]" :loop="true" :autoplay="{ delay: 3000 }"
                    :pagination="{ clickable: true }" :navigation="true" class="mySwiper">
                    <!-- Slide 1 -->
                    <SwiperSlide>
                      <div class="item-slider object-fit" style="height: 330px;">
                        <div class="img-slide">
                          <picture>
                            <source type="image/webp" width="768" height="330"
                              srcset="https://martfury02.magebig.com/media/webps/jpg/media/wysiwyg/magebig/layout02/mf02-slider-01.webp"
                              media="(min-width: 768px)">
                            <source width="768" height="330"
                              srcset="https://martfury02.magebig.com/media/wysiwyg/magebig/layout02/mf02-slider-01.jpg"
                              media="(min-width: 768px)">
                            <img class="img-fluid" alt="TV Banner" width="470" height="330"
                              src="/media/webps/jpg/media/wysiwyg/magebig/layout02/mf02-slider-mobile-01.webp" />
                          </picture>
                        </div>
                        <div class="block-content-slide">
                          <div class="block-center">
                            <p class="text-small">Samsung</p>
                            <h2 class="text-large">Smart TV 43 Inch 43M55<br>4k Full HD Tizen OS</h2>
                            <div class="text-normal">
                              <div>Sale</div>
                              <p>30% Off</p>
                            </div>
                            <div class="btn-wrap">
                              <a class="btn-shopnow action primary" href="#"><span>Shop now</span></a>
                            </div>
                          </div>
                        </div>
                      </div>
                    </SwiperSlide>

                    <!-- Slide 2 -->
                    <SwiperSlide>
                      <div class="item-slider object-fit" style="height: 330px;">
                        <img class="img-fluid" alt="Summer Sale"
                          src="/media/webps/jpg/media/wysiwyg/magebig/layout02/mf02-slider-mobile-02.webp" />
                        <div class="block-content-slide">
                          <div class="block-center">
                            <p class="text-small">Mega Sale, Don't Miss Out!</p>
                            <h2 class="text-large">Happy Summer<br>combo super cool</h2>
                            <div class="text-normal">
                              <div>Up to</div>
                              <p>40% Off</p>
                            </div>
                            <div class="btn-wrap">
                              <a class="btn-shopnow action primary" href="#"><span>Shop now</span></a>
                            </div>
                          </div>
                        </div>
                      </div>
                    </SwiperSlide>

                    <!-- Slide 3 -->
                    <SwiperSlide>
                      <div class="item-slider object-fit" style="height: 330px;">
                        <img class="img-fluid" alt="Marshall Speaker"
                          src="/media/webps/jpg/media/wysiwyg/magebig/layout02/mf02-slider-mobile-03.webp" />
                        <div class="block-content-slide">
                          <div class="block-center">
                            <p class="text-small">Don't Miss Out!</p>
                            <h2 class="text-large">Experience great sound<br>with Marshall speaker</h2>
                            <div class="text-normal">
                              <div><span style="text-decoration: line-through;">$225.00</span></div>
                              <p>$200.00</p>
                            </div>
                            <div class="btn-wrap">
                              <a class="btn-shopnow action primary" href="#"><span>Shop now</span></a>
                            </div>
                          </div>
                        </div>
                      </div>
                    </SwiperSlide>
                  </Swiper>
                </div>
              </div>
              <div class="col-12 col-xl-4">
                <div class="row">
                  <div class="col-12 col-sm-6 col-xl-12">
                    <div class="item-bn-inner"><a href="#" class="block-top hover-effect01 object-fit"
                        style="height: 150px;"><span class="img-native-wrap" style="padding-bottom: 40.541%;"><img
                            class="img-fluid" alt="" width="370" height="150" loading="lazy"
                            src="/media/webps/jpg/media/wysiwyg/magebig/layout02/mf02-blocktop-01.webp"
                            data-webp="1"></span><span class="text"><span
                            style="font-size: 18pt;"><strong>Fluence</strong>
                            Minimal</span><br><span style="font-size: 18pt;">Speaker</span><br><br><span
                            style="color: #999999;">Price just</span> <br><span style="color: #ff0000;"><span
                              style="color: #339966;">$159.99</span></span></span></a>
                    </div>
                  </div>
                  <div class="col-12 col-sm-6 col-xl-12">
                    <div class="item-bn-inner" style="height: 150px;"><a href="#"
                        class="block-top hover-effect01 object-fit" style="height: 150px;"><span class="img-native-wrap"
                          style="padding-bottom: 40.541%;"><img class="img-fluid" alt="" width="370" height="150"
                            loading="lazy" src="/media/webps/jpg/media/wysiwyg/magebig/layout02/mf02-blocktop-02.webp"
                            data-webp="1"></span><span class="text"><span style="font-size: 18pt;">Gopro
                            camera</span><br><br><span>Sale <span style="color: #ff0000;">20% off</span></span>
                          <br><span style="color: #666;">Only 2 days: 21/10 &amp;
                            22/10</span></span></a></div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="container main-container">
      <div class="columns row">
        <div class="column main main-wrap col-12">
          <div class="widgetplus widgetplus-block slider-0" id="widgetplus-block-4183918087">
            <div class="main-heading">
              <h2 class="heading-title"><span>Top Categories Of The Month</span></h2>
            </div>
            <div class="row">
              <div v-for="(category, index) in categories" :key="index" class="col-12 col-md-6 col-xl-4">
                <div class="category-list-top">
                  <div class="row no-gutters">
                    <div class="col">
                      <a href="#" aria-label="catalog">
                        <span class="img-native-wrap" style="padding-bottom: 100%;">
                          <img class="img-fluid" :src="category.image" :alt="category.title" width="168" height="168"
                            loading="lazy" />
                        </span>
                      </a>
                    </div>
                    <div class="col">
                      <div class="title"><a href="#">{{ category.title }}</a></div>
                      <ul>
                        <li v-for="(item, i) in category.items" :key="i"><a href="#">{{ item }}</a></li>
                      </ul>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div
            data-mage-init='{"widgetTemplate":{"loadUrl": "https://martfury02.magebig.com/widgetplus/index/ajax/", "parameters": {"type":"MageBig\\WidgetPlus\\Block\\StaticPlus","block_id":"deals-of-the-day-v2","is_ajax":0,"countdown":"1","slider":"0","background_type":"0","template":"MageBig_WidgetPlus::widget\/static_block.phtml"}, "offset": 200}}'
            class="ajax-widget" id="ajax-widgetplus-block-1912201016" style="min-height: 300px"></div>
          <input name="form_key" type="hidden" value="HAPdytnD7dxITe7u">
          <div id="authenticationPopup" style="display: none;"></div>
          <div
            data-mage-init='{"widgetTemplate":{"loadUrl": "https://martfury02.magebig.com/widgetplus/index/ajax/", "parameters": {"type":"MageBig\\WidgetPlus\\Block\\StaticPlus","block_id":"block-content-v2","is_ajax":0,"countdown":"0","slider":"0","background_type":"0","template":"MageBig_WidgetPlus::widget\/static_block.phtml"}, "offset": 200}}'
            class="ajax-widget" id="ajax-widgetplus-block-1461978581" style="min-height: 300px"></div>
          <div id="social-login-popup" class="white-popup mfp-with-anim mfp-hide"
            data-mage-init='{"socialPopupForm": {"headerLink":".header.links","popupEffect":"mfp-move-from-top","formLoginUrl":"https:\/\/martfury02.magebig.com\/customer\/ajax\/login\/","forgotFormUrl":"https:\/\/martfury02.magebig.com\/sociallogin\/popup\/forgot\/","createFormUrl":"https:\/\/martfury02.magebig.com\/sociallogin\/popup\/create\/","fakeEmailUrl":"https:\/\/martfury02.magebig.com\/sociallogin\/social\/email\/","popupCreate":0,"popupForgot":0}}'>
            <div class="social-login block-container fake-email" style="display:none">
              <div class="social-login-title">
                <h2 class="forgot-pass-title">Real email address is required to social networks</h2>
              </div>
              <div class="block col-mp mp-12">
                <div class="block-content">
                  <form class="form-fake-email" id="social-form-fake-email" data-mage-init='{"validation":{}}'>
                    <fieldset class="fieldset" data-hasrequired="* Required Fields">
                      <div class="field note">Please enter your email address below to create
                        account.</div>
                      <div class="field email required"> <label for="real_email_address"
                          class="label"><span>Email</span></label>
                        <div class="control"> <input type="email" name="realEmail" id="real_email_address"
                            class="input-text" data-validate="{required:true, 'validate-email':true}">
                        </div>
                      </div>
                    </fieldset>
                    <div class="actions-toolbar">
                      <div class="primary"> <button type="button" id="bnt-social-login-fake-email"
                          class="action send primary">
                          <span>Submit</span> </button></div>
                    </div>
                  </form>
                </div>
              </div>
            </div>
            <div class="social-login block-container authentication">
              <div class="social-login-title">
                <h2 class="login-title">Log In</h2>
              </div>
              <div class="block social-login-customer-authentication login-container" id="social-login-authentication">
                <div class="block-content">
                  <form class="form-customer-login form-login" id="social-form-login" data-mage-init='{"validation":{}}'
                    method="post"> <input name="form_key" type="hidden" value="HAPdytnD7dxITe7u">
                    <fieldset class="fieldset login" data-hasrequired="* Required Fields">
                      <div class="field email required"> <label class="label d-none"
                          for="email-login"><span>Email</span></label>
                        <div class="control"> <input name="username" id="email-login" type="email" class="input-text"
                            value="" autocomplete="off" title="Email"
                            data-validate="{required:true, 'validate-email':true}" placeholder="Email"></div>
                      </div>
                      <div class="field password required"> <label class="label d-none"
                          for="pass-popup"><span>Password</span></label>
                        <div class="control"> <input name="password" id="pass-popup" type="password" class="input-text"
                            autocomplete="off" title="Password" data-validate="{required:true}" placeholder="Password">
                          <a class="action remind" href="customer/account/forgotpassword/index.html"
                            title="Forgot Your Password?"><span>Forgot?</span></a>
                        </div>
                      </div>
                      <div class="actions-toolbar">
                        <div class="primary"> <button type="submit" class="action login primary"
                            id="btn-social-login-authentication"> <span>Login</span>
                          </button></div>
                      </div>
                      <div class="actions-toolbar">
                        <div class="primary"> <a class="action create"
                            href="customer/account/create/index.html"><span>Create New
                              Account?</span></a></div>
                      </div>
                    </fieldset>
                  </form>
                </div>
              </div>
              <div class="block social-login-authentication-channel">
                <div class="block-title"> <span>Or</span></div>
                <div class="block-content">
                  <div class="actions-toolbar social-btn facebook-login"> <a
                      class="btn btn-block btn-social btn-facebook" href="#"
                      data-mage-init='{"socialProvider": {"url": "https://martfury02.magebig.com/sociallogin/social/login/type/facebook/", "label": "Login By Facebook"}}'>
                      <svg version="1.1" xmlns="http://www.w3.org/2000/svg" width="16" height="28" viewBox="0 0 16 28">
                        <title>facebook</title>
                        <path
                          d="M14.984 0.187v4.125h-2.453c-1.922 0-2.281 0.922-2.281 2.25v2.953h4.578l-0.609 4.625h-3.969v11.859h-4.781v-11.859h-3.984v-4.625h3.984v-3.406c0-3.953 2.422-6.109 5.953-6.109 1.687 0 3.141 0.125 3.563 0.187z">
                        </path>
                      </svg> Sign in with Facebook </a></div>
                  <div class="actions-toolbar social-btn google-login"> <a class="btn btn-block btn-social btn-google"
                      href="#"
                      data-mage-init='{"socialProvider": {"url": "https://martfury02.magebig.com/sociallogin/social/login/type/google/", "label": "Login By Google"}}'>
                      <svg xmlns="http://www.w3.org/2000/svg" version="1.1" width="24" height="28" viewBox="0 0 24 28">
                        <title>google</title>
                        <path
                          d="M12 12.281h11.328c0.109 0.609 0.187 1.203 0.187 2 0 6.844-4.594 11.719-11.516 11.719-6.641 0-12-5.359-12-12s5.359-12 12-12c3.234 0 5.953 1.188 8.047 3.141l-3.266 3.141c-0.891-0.859-2.453-1.859-4.781-1.859-4.094 0-7.438 3.391-7.438 7.578s3.344 7.578 7.438 7.578c4.75 0 6.531-3.406 6.813-5.172h-6.813v-4.125z" />
                      </svg> Sign in with Google </a></div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="page-bottom">
      <div class="page-bottom-content container">
        <div
          data-mage-init='{"widgetTemplate":{"loadUrl": "https://martfury02.magebig.com/widgetplus/index/ajax/", "parameters": {"type":"MageBig\\WidgetPlus\\Block\\StaticPlus","block_id":"blog-v2","is_ajax":0,"countdown":"0","slider":"0","background_type":"0","template":"MageBig_WidgetPlus::widget\/static_block.phtml"}, "offset": 200}}'
          class="ajax-widget" id="ajax-widgetplus-block-3267836150" style="min-height: 300px"></div>
        <div class="admin__data-grid-outer-wrap" data-bind="scope: 'widget_recently_viewed.widget_recently_viewed'">
          <!-- ko template: getTemplate() --><!-- /ko -->
        </div>
      </div>
    </div>
  </main>
</template>

<style>
.mySwiper {
  width: 100%;
  height: 330px;
}

.swiper-button-next,
.swiper-button-prev {
  width: 25px;
  /* button area */
  height: 25px;
  /* button area */
}

.swiper-button-next::after,
.swiper-button-prev::after {
  color: grey;
  font-size: 18px;
  /* icon size */
}
</style>
