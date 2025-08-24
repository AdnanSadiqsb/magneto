<script lang="ts" setup>
import { useUserStore } from '@/stores/useUserStore'

const store = useUserStore()
const { isLoggedIn, userInfo } = storeToRefs(store)
const navList = computed(() => [
  {
    label: 'Home',
    path: '/',
    show: true,
  },
  {
    label: 'Sign in',
    path: '/login',
    show: !isLoggedIn.value,
  },
  {
    label: 'Sign up',
    path: '/register',
    show: !isLoggedIn.value,
  },
  {
    label: 'New Article',
    path: '/article/create',
    show: isLoggedIn.value,
    icon: 'ion-compose',
  },
  {
    label: 'Settings',
    path: '/settings',
    show: isLoggedIn.value,
    icon: 'ion-gear-a',
  },
  {
    label: userInfo.value?.username,
    path: `/profile/${store.userInfo?.username}`,
    show: isLoggedIn.value,
    pic: userInfo.value?.image,
  },
])

const departmentMenu = [
  {
    title: "Consumer Electric",
    icon: "mbi-laundry",
    link: "consumer-electric.html",
    mega: true,
    children: [
      {
        title: "Electronics",
        link: "consumer-electric/electronics.html",
        children: [
          { title: "Home Audios & Theaters", link: "consumer-electric/electronics/home-audios-theaters.html" },
          { title: "TV & Videos", link: "consumer-electric/electronics/tv-videos.html" },
          { title: "Camera, Photos & Videos", link: "consumer-electric/electronics/camera-photos-videos.html" },
          { title: "Headphones", link: "consumer-electric/electronics/headphones.html" },
          { title: "Videogames", link: "consumer-electric/electronics/videogames.html" },
          { title: "Wireless Speakers", link: "consumer-electric/electronics/wireless-speakers.html" },
          { title: "Car Electronics", link: "consumer-electric/electronics/car-electronics.html" },
          { title: "Electronics Showcase", link: "consumer-electric/electronics/electronics-showcase.html" }
        ]
      },
      {
        title: "Accessories & Parts",
        link: "consumer-electric/accessories-parts.html",
        children: [
          { title: "Digital Cables", link: "consumer-electric/accessories-parts/digital-cables.html" },
          { title: "Audio & Video Cables", link: "consumer-electric/accessories-parts/audio-video-cables.html" },
          { title: "Batteries", link: "consumer-electric/accessories-parts/batteries.html" },
          { title: "Charger", link: "consumer-electric/accessories-parts/charger.html" }
        ]
      }
    ],
    staticBlock: {
      title: "DJI Phantom",
      subtitle: "Quadcopter",
      button: { text: "Shop Now", link: "#" },
      image: "/media/webps/png/media/wysiwyg/magebig/menu/img-menu-1.webp"
    }
  },
  {
    title: "Organic",
    icon: "mbi-grapes",
    link: "organic.html",
    label: "hot"
  },
  {
    title: "Home, Garden & Kitchen",
    icon: "mbi-lampshade",
    link: "home-garden-kitchen.html",
    children: [
      { title: "Furniture", link: "home-garden-kitchen/furniture.html" },
      { title: "Home Decor", link: "home-garden-kitchen/home-decor.html" },
      { title: "Cookware", link: "home-garden-kitchen/cookware.html" },
      { title: "Utensils & Gadget", link: "home-garden-kitchen/utensils-gadget.html" },
      { title: "Garden Tools", link: "home-garden-kitchen/garden-tools.html" }
    ]
  },
  {
    title: "Clothing & Apparel",
    icon: "mbi-shirt",
    link: "clothing-apparel.html",
    label: "new",
    children: [
      { title: "Women", link: "clothing-apparel/women.html" },
      { title: "Men", link: "clothing-apparel/men.html" },
      { title: "Girls", link: "clothing-apparel/girls.html" },
      { title: "Boys", link: "clothing-apparel/boys.html" },
      { title: "Baby", link: "clothing-apparel/baby.html" }
    ]
  },
  {
    title: "Jewelry & Watches",
    icon: "mbi-diamond4",
    link: "jewelry-watches.html"
  }
  // 👉 You can continue the rest (Computers, Babies & Moms, etc.) in the same format
];

</script>

<template>
<header class="page-header">
        <div class="panel wrapper">
          <div class="panel header"><a class="action skip contentarea" href="#contentarea"> <span> Skip to Content
              </span> </a></div>
        </div>
        <div class="header-top-inner">
          <div class="container">
            <div class="row align-items-center header-top-row">
              <div class="d-none d-md-block col-sm-3 col-lg-5">
                <div class="welcome">Welcome to Martfury Online Store</div>
              </div>
              <div class="col-12 col-md-9 col-lg-7">
                <div class="row align-items-center justify-content-end top-link-wrap">
                  <div class="col-auto top-links"><a href="contact/index.html">Store Location</a></div>
                  <div class="col-auto top-links"><a href="sales/guest/form/index.html">Track Order</a>
                  </div>
                  <div class="col-auto top-links">
                    <div class="currency-topbar switcher currency switcher-currency" id="switcher-currency">
                      <div class="currency-sym language-USD"> <span class="title"><span>USD</span><i
                            class="mbi mbi-ios-arrow-down"></i></span></div>
                      <div class="currency-list">
                        <ul class="dropdown switcher-dropdown">
                          <li class="currency-BSD switcher-option"> <a href="#"
                              data-post='{"action":"https:\/\/martfury02.magebig.com\/directory\/currency\/switch\/","data":{"currency":"BSD","uenc":"aHR0cHM6Ly9tYXJ0ZnVyeTAyLm1hZ2ViaWcuY29tLw~~"}}'>BSD</a>
                          </li>
                          <li class="currency-EUR switcher-option"> <a href="#"
                              data-post='{"action":"https:\/\/martfury02.magebig.com\/directory\/currency\/switch\/","data":{"currency":"EUR","uenc":"aHR0cHM6Ly9tYXJ0ZnVyeTAyLm1hZ2ViaWcuY29tLw~~"}}'>EUR</a>
                          </li>
                          <li class="currency-HKD switcher-option"> <a href="#"
                              data-post='{"action":"https:\/\/martfury02.magebig.com\/directory\/currency\/switch\/","data":{"currency":"HKD","uenc":"aHR0cHM6Ly9tYXJ0ZnVyeTAyLm1hZ2ViaWcuY29tLw~~"}}'>HKD</a>
                          </li>
                          <li class="currency-INR switcher-option"> <a href="#"
                              data-post='{"action":"https:\/\/martfury02.magebig.com\/directory\/currency\/switch\/","data":{"currency":"INR","uenc":"aHR0cHM6Ly9tYXJ0ZnVyeTAyLm1hZ2ViaWcuY29tLw~~"}}'>INR</a>
                          </li>
                          <li class="currency-AED switcher-option"> <a href="#"
                              data-post='{"action":"https:\/\/martfury02.magebig.com\/directory\/currency\/switch\/","data":{"currency":"AED","uenc":"aHR0cHM6Ly9tYXJ0ZnVyeTAyLm1hZ2ViaWcuY29tLw~~"}}'>AED</a>
                          </li>
                        </ul>
                      </div>
                    </div>
                  </div>
                  <div class="col-auto top-links">
                    <div class="language-topbar switcher language switcher-language" data-ui-id="language-switcher"
                      id="switcher-language">
                      <div class="lang-curr view-en2"> <span class="title"> <span class="lang-flag en2"> <img
                              class="img-fluid" alt="en2" width="18" height="12"
                              src="/media/webps/png/media/wysiwyg/magebig/languages/en2.webp" data-webp="1"> </span>
                          <span class="lang-name">English</span><i class="mbi mbi-ios-arrow-down"></i> </span></div>
                      <div class="lang-list">
                        <ul class="dropdown switcher-dropdown">
                          <li class="view-du switcher-option"> <a href="#"
                              data-post='{"action":"https:\/\/martfury02.magebig.com\/stores\/store\/redirect\/","data":{"___store":"du","___from_store":"en2","uenc":"aHR0cHM6Ly9tYXJ0ZnVyeTAyLm1hZ2ViaWcuY29tLz9fX19zdG9yZT1kdQ~~"}}'>
                              <span class="lang-flag du"> <img loading="lazy" class="img-fluid" alt="du" width="18"
                                  height="12" src="/media/webps/png/media/wysiwyg/magebig/languages/du.webp"
                                  data-webp="1"> </span> <span class="lang-name">Dutch</span> </a></li>
                          <li class="view-ar2 switcher-option"> <a href="#"
                              data-post='{"action":"https:\/\/martfury02.magebig.com\/stores\/store\/redirect\/","data":{"___store":"ar2","___from_store":"en2","uenc":"aHR0cHM6Ly9tYXJ0ZnVyeTAyLm1hZ2ViaWcuY29tLz9fX19zdG9yZT1hcjI~"}}'>
                              <span class="lang-flag ar2"> <img loading="lazy" class="img-fluid" alt="ar2" width="18"
                                  height="12" src="/media/webps/png/media/wysiwyg/magebig/languages/ar2.webp"
                                  data-webp="1"> </span> <span class="lang-name">Arabic</span> </a></li>
                        </ul>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="header-main-content sticky-menu">
          <div class="container">
            <div class="header-main-inner ">
              <div class="row align-items-center header-maininner-row">
                <div class="col-12 col-md-3 col-lg-3 col-logo">
                  <div class="menu-logo">
                    <div class="logo-top d-table-cell ">
                      <h1 class="logo text-hide"> <a class="logo" href="index.html"
                          title="Martfury&#x20;-&#x20;Best&#x20;Magento&#x20;Theme&#x20;2023" aria-label="store logo">
                          <img title="Martfury&#x20;-&#x20;Best&#x20;Magento&#x20;Theme&#x20;2023"
                            alt="Martfury&#x20;-&#x20;Best&#x20;Magento&#x20;Theme&#x20;2023" width="225" height="50"
                            src="/media/webps/png/media/logo/stores/7/martfury.webp" data-webp="1"> </a></h1>
                    </div>
                    <div class="icon-top-mobile">
                      <div class="minicart-action"> <a class="action showcart" href="checkout/cart/index.html"
                          data-bind="scope: 'minicart_content'" aria-label="My Cart"> <i class="mbi mbi-bag2"></i> <span
                            class="counter qty empty"
                            data-bind="css: { empty: !!getCartParam('summary_count') == false }, blockLoader: isLoading">
                            <span class="counter-number "
                              data-bind="html: getCartParam('summary_count') > 9 ? '&nbsp;9<sup>+</sup>' : getCartParam('summary_count')"></span>
                          </span> </a></div>
                      <div class="user-icon-mobile user-topbar"><i class="mbi mbi-user"></i></div>
                    </div>
                  </div>
                  <div class="mb-navigation vertical-menu d-none d-md-block">
                    <div class="title"><span class="mbi mbi-menu"></span><span class="d-none d-md-block">Shop By
                        Department <i class="mbi mbi-ios-arrow-down"></i></span></div>
                    <div class="navigation" data-action="navigation">
                       <ul class="smartmenu magebig-nav">
    <li
      v-for="(menu, i) in departmentMenu"
      :key="i"
      class="level0"
      :class="[{ parent: menu.children, mega_fullwidth: menu.mega }, `nav-${i+1}`, 'level-top']"
    >
      <a :href="menu.link" class="level-top">
        <i :class="`mbi ${menu.icon}`"></i>
        <span>
          {{ menu.title }}
          <span v-if="menu.label" class="cat-label" :class="`cat-label-${menu.label}`">{{ menu.label }}</span>
        </span>
      </a>
      <i v-if="menu.children" class="mbi mbi-ios-arrow-down"></i>

      <!-- Submenu -->
      <div v-if="menu.children" class="submenu show-sub">
        <div class="show-sub-content">
          <div class="mbmenu-block mbmenu-block-center menu-items col12-12 itemgrid itemgrid-2col">
            <ul class="level0">
              <li
                v-for="(child, j) in menu.children"
                :key="j"
                class="level1 groups item parent"
              >
                <a :href="child.link" class="level-top">
                  <span class="title_group">{{ child.title }}</span>
                </a>

                <!-- Sub-submenu -->
                <div v-if="child.children" class="groups-wrapper">
                  <div class="show-sub-content">
                    <ul class="level1">
                      <li
                        v-for="(sub, k) in child.children"
                        :key="k"
                        class="level2 nav-item"
                      >
                        <a :href="sub.link" class="level-top">
                          <span>{{ sub.title }}</span>
                        </a>
                      </li>
                    </ul>
                  </div>
                </div>
              </li>
            </ul>
          </div>

          <!-- Static Block -->
          <div v-if="menu.staticBlock" class="mbmenu-block mbmenu-block-bottom grid-full std">
            <div class="static-bottom-menu">
              <div class="link-text">
                <a :href="menu.staticBlock.button.link">
                  <span class="large-text" style="color: #b5892a;">{{ menu.staticBlock.title }}</span>
                  <span class="small-text">{{ menu.staticBlock.subtitle }}</span>
                </a>
              </div>
              <div>
                <a class="btn action primary" :href="menu.staticBlock.button.link">
                  <strong>{{ menu.staticBlock.button.text }}</strong>
                </a>
              </div>
              <div class="img-outside">
                <img
                  class="img-fluid"
                  :src="menu.staticBlock.image"
                  alt=""
                  width="458"
                  height="298"
                  loading="lazy"
                />
              </div>
            </div>
          </div>
        </div>
      </div>
    </li>
  </ul>
                    </div>
                  </div>
                </div>
                <div class="col-md-5 col-lg-5 col-xl-6 col-search">
                  <div class="top-search-wrap mfp-with-anim">
                    <div class="block block-search">
                      <div class="block block-title"><strong>Search</strong></div>
                      <div class="block block-content">
                        <form class="form minisearch" id="search_mini_form"
                          action="https://martfury02.magebig.com/catalogsearch/result/" method="get">
                          <div class="field search"> <label class="label" for="search" data-role="minisearch-label">
                              <span>Search</span> </label>
                            <div class="control"> <input id="search" type="text" name="q" value=""
                                placeholder="I'm looking for..." class="input-text" maxlength="128" role="combobox"
                                aria-haspopup="false" aria-expanded="false" aria-autocomplete="both" autocomplete="off">
                              <div id="search_autocomplete" class="search-autocomplete"></div>
                              <div data-bind="scope: 'ajaxsearch_form'">
                                <!-- ko template: getTemplate() --><!-- /ko -->
                              </div>
                            </div>
                          </div>
                          <div class="actions"> <button type="submit" title="Search" class="action search">
                              <span>Search</span> </button></div>
                        </form>
                      </div>
                    </div>
                  </div>
                </div>
                <div class="col-12 col-md-4 col-lg-4 col-xl-3 col-btn-actions-desktop d-none d-md-block">
                  <div class="header-content-action row no-gutters">
                    <div class="col col-wishlist d-none d-md-block">
                      <div class="wishlist-topbar" data-bind="scope: 'wishlist'"> <a class="wishlist-icon link wishlist"
                          aria-label="Wishlist" href="wishlist/index.html"> <i class="mbi mbi-heart"></i> <span
                            data-bind="html: wishlist().counter ? (wishlist().counter.replace(/[^0-9]/g,'') > 9 ? '&nbsp;9<sup>+</sup>' : wishlist().counter.replace(/[^0-9]/g,'')) : 0, css: { empty: !!wishlist().counter == false }"
                            class="counter-number qty empty"></span> </a></div>
                    </div>
                    <div class="col col-minicart">
                      <div class="minicart-action"> <a class="action showcart" href="checkout/cart/index.html"
                          data-bind="scope: 'minicart_content'" aria-label="My Cart"> <i class="mbi mbi-bag2"></i> <span
                            class="counter qty empty"
                            data-bind="css: { empty: !!getCartParam('summary_count') == false }, blockLoader: isLoading">
                            <span class="counter-number"
                              data-bind="html: getCartParam('summary_count') > 9 ? '&nbsp;9<sup>+</sup>' : getCartParam('summary_count')"></span>
                          </span> </a></div>
                      <div data-block="minicart" class="minicart-wrapper minicart-slide mfp-hide">
                        <div class="block block-minicart empty" style="display: block;">
                          <div id="minicart-content-wrapper" data-bind="scope: 'minicart_content'">
                            <!-- ko template: getTemplate() --><!-- /ko -->
                          </div>
                        </div>
                      </div>
                    </div>
                    <div class="user-topbar col"> <i class="mbi mbi-user"></i>
                      <ul class="header links">
                        <li class="authorization-link"> <a
                            href="customer/account/login/referer/aHR0cHM6Ly9tYXJ0ZnVyeTAyLm1hZ2ViaWcuY29tLw__/index.html">
                            Log In </a></li>
                        <li><a href="customer/account/create/index.html" id="idm3FTBHuy">Register</a></li>
                      </ul>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="header-menu-content d-none d-md-block">
          <div class="container">
            <div class="menu-container">
              <div class="row align-items-center">
                <div class="col-3 d-none d-md-block"></div>
                <div class="col-9 col-md-9 col-lg-6 d-none d-md-block">
                  <div class="horizontal-menu-wrap">
                    <div class="horizontal-menu">
                      <ul class="smartmenu magebig-nav">
                        <li class="level0 level-top mega_left parent"><a class="level-top" href="index.html"><span>Home
                              Layout</span></a> <i class="mbi mbi-ios-arrow-down">&nbsp;</i>
                          <div class="simple-dropdown submenu show-sub" style="width: 270px; height: auto;">
                            <div class="mbmenu-block mbmenu-block-center menu-items col12-12 itemgrid itemgrid-4col">
                              <ul class="level0">
                                <li class="level1 item level-top mega_"><a class="level-top"
                                    href="http://martfury.magebig.com/stores/store/switch/?___from_store=ar&amp;___store=en"><span>Martfury
                                      v01 - Marketplace</span></a></li>
                                <li class="level1 item level-top mega_"><a class="level-top"
                                    href="stores/store/switch/index67f1.html?___from_store=ar2&amp;___store=en2"><span>Martfury
                                      v02 - Electronic</span></a></li>
                                <li class="level1 item level-top mega_"><a class="level-top"
                                    href="http://martfury03.magebig.com/stores/store/switch/?___from_store=ar3&amp;___store=en3"><span>Martfury
                                      v03 - Organic</span></a></li>
                                <li class="level1 item level-top mega_"><a class="level-top"
                                    href="http://martfury04.magebig.com/stores/store/switch/?___from_store=ar4&amp;___store=en4"><span>Martfury
                                      v04 - Furniture</span></a></li>
                                <li class="level1 item level-top mega_"><a class="level-top"
                                    href="http://martfury05.magebig.com/stores/store/switch/?___from_store=ar5&amp;___store=en5"><span>Martfury
                                      v05 - Market</span></a></li>
                                <li class="level1 item level-top mega_"><a class="level-top"
                                    href="http://martfury05.magebig.com/stores/store/switch/?___from_store=ar5&amp;___store=es"><span>Martfury
                                      v05 - FullWidth</span></a></li>
                              </ul>
                            </div>
                          </div>
                        </li>
                        <li class="level0 level-top mega_ parent"><a class="level-top"
                            href="#"><span>Category</span></a><i class="mbi mbi-ios-arrow-down">&nbsp;</i>
                          <div class="simple-dropdown submenu show-sub" style="width: 270px; height: auto;">
                            <div class="mbmenu-block mbmenu-block-center menu-items col12-12 itemgrid itemgrid-4col">
                              <ul class="level0">
                                <li class="level1 item level-top mega_"><a class="level-top"
                                    href="consumer-electric40bd.html?product_list_mode=grid"><span>Category
                                      View - Grid</span></a></li>
                                <li class="level1 item level-top mega_"><a class="level-top"
                                    href="consumer-electric0744.html?product_list_mode=list"><span>Category
                                      View - List</span></a></li>
                              </ul>
                            </div>
                          </div>
                        </li>
                        <li class="level0 level-top mega_ parent"><a class="level-top"
                            href="#"><span>Product</span></a><i class="mbi mbi-ios-arrow-down">&nbsp;</i>
                          <div class="simple-dropdown submenu show-sub" style="width: 270px; height: auto;">
                            <div class="mbmenu-block mbmenu-block-center menu-items col12-12 itemgrid itemgrid-4col">
                              <ul class="level0">
                                <li class="level1 item level-top mega_"><a class="level-top"
                                    href="dbpower-t20-1500-lumens-lcd-projector.html"><span>Simple
                                      Product</span></a></li>
                                <li class="level1 item level-top mega_"><a class="level-top"
                                    href="sleeve-linen-blend-caro-pane-shirt.html"><span>Configurable
                                      Product</span></a></li>
                                <li class="level1 item level-top mega_"><a class="level-top"
                                    href="men-sports-running-swim-group.html"><span>Group
                                      Product</span></a></li>
                                <li class="level1 item level-top mega_"><a class="level-top"
                                    href="samsung-4k-ultra-hd-smart-led-tv.html"><span>Bundle
                                      Product</span></a></li>
                                <li class="level1 item level-top mega_"><a class="level-top"
                                    href="mvmth-classical-leather-watch-in-black.html">
                                    <span>Tier Product</span> </a></li>
                                <li class="level1 item level-top mega_"><a class="level-top"
                                    href="grand-slam-indoor-of-show-jumping-novel.html"><span>Dowloadable
                                      Product</span></a></li>
                              </ul>
                            </div>
                          </div>
                        </li>
                        <li class="level0 level-top mega_ parent"><a class="level-top"
                            href="blog.html"><span>Blog</span></a><i class="mbi mbi-ios-arrow-down">&nbsp;</i>
                          <div class="simple-dropdown submenu show-sub" style="width: 270px; height: auto;">
                            <div class="mbmenu-block mbmenu-block-center menu-items col12-12 itemgrid itemgrid-4col">
                              <ul class="level0">
                                <li class="level1 item level-top mega_"><a class="level-top"
                                    href="blog/category/bussiness/index.html"><span>Bussiness</span></a>
                                </li>
                                <li class="level1 item level-top mega_"><a class="level-top"
                                    href="blog/category/technology/index.html"><span>Technology</span></a>
                                </li>
                                <li class="level1 item level-top mega_"><a class="level-top"
                                    href="blog/category/fashion/index.html"><span>Fashion</span></a>
                                </li>
                              </ul>
                            </div>
                          </div>
                        </li>
                        <li class="level0 level-top mega_"><a class="level-top"
                            href="contact.html"><span>Contact</span></a></li>
                      </ul>
                    </div>
                  </div>
                </div>
                <div class="col-12 col-md-3 d-none d-lg-block">
                  <div class="hotline-top"><i class="mbi mbi-telephone">&nbsp;</i><span> Hotline:
                      <strong>1-800-234-5678</strong><span></span></span></div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="d-block d-md-none col-btn-actions">
          <div class="header-content-action row no-gutters">
            <div class="btn-nav-mobile col"> <button type="button"
                class="btn-nav mb-toggle-switch mb-toggle-switch__htx" aria-label="menu"><span></span></button>
              <div class="menu-btn-text">Menu</div>
            </div>
            <div class="btn-search-mobile col"> <i class="mbi mbi-magnifier"></i>
              <div class="menu-btn-text">Search</div>
            </div>
            <div class="col col-home"> <a href="index.html" aria-label="Home" class="go-home"><i
                  class="mbi mbi-home3"></i></a>
              <div class="menu-btn-text">Home</div>
            </div>
            <div class="col col-cart">
              <div class="minicart-action"> <a class="action showcart" href="checkout/cart/index.html"
                  data-bind="scope: 'minicart_content'" aria-label="My Cart"> <i class="mbi mbi-bag2"></i>
                  <span class="counter qty empty"
                    data-bind="css: { empty: !!getCartParam('summary_count') == false }, blockLoader: isLoading">
                    <span class="counter-number"
                      data-bind="html: getCartParam('summary_count') > 9 ? '&nbsp;9<sup>+</sup>' : getCartParam('summary_count')"></span>
                  </span> </a></div>
              <div class="menu-btn-text">My Cart</div>
            </div>
            <div class="user-topbar col"> <i class="mbi mbi-user"></i>
              <div class="menu-btn-text">Me</div>
            </div>
          </div>
        </div>
      </header>
</template>
