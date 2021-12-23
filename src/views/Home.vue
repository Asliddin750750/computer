<template>
  <!--Menubar-->
  <Menubar :model="items" style="margin: -8px;" class="p-px-6">
    <template #start>
      <h2>Logo</h2>
    </template>
    <template #end>
      <div class="p-d-flex p-ai-center">
        <Button class="p-mr-4 p-button-text" @click="toggle">
          <span>Til</span>
          <i class="pi pi-angle-down"></i>
        </Button>
        <Button>Kirish</Button>
      </div>
    </template>
  </Menubar>
  <Menu id="overlay_menu" ref="menu" :model="menus" :popup="true" />
  <!--Slide-->
  <div class="p-d-flex p-jc-center p-pt-6">
    <Galleria :value="images" :responsiveOptions="responsiveOptions" :numVisible="5" :circular="true" containerStyle="max-width: 94%;"
              :showItemNavigators="true" :showThumbnails="false" :autoPlay="true" :transitionInterval="3000">
      <template #item="slotProps">
        <img :src="slotProps.item.itemImageSrc" :alt="slotProps.item.alt" style="width: 100%; display: block;" />
      </template>
    </Galleria>
  </div>
  <!--Products-->
  <div class="p-px-6 p-pt-3">
    <div class="card">
      <Carousel :value="products" :numVisible="3" :numScroll="1" :responsiveOptions="responsiveOptions" class="custom-carousel" :circular="true" :autoplayInterval="3000">
        <template #header>
          <div class="p-d-flex p-ai-center">
            <h1 class="p-mr-auto">Top mahsulotlar</h1>
            <div class="p-ml-auto">
              <h3 class="p-d-inline p-mr-2">Hammasini ko'rish</h3>
              <i class="pi pi-arrow-right"></i>
            </div>
          </div>
        </template>
        <template #item="slotProps">
          <div class="product-item p-grid">
            <div class="product-item-content">
              <div class="p-mb-3">
                <img src="https://primefaces.org/primevue/showcase/demo/images/product/blue-t-shirt.jpg" :alt="slotProps.data.name" class="product-image" />
              </div>
              <div>
                <h3 class="p-mb-1 p-text-center">{{slotProps.data.name}}</h3>
                <h4 class="p-mt-0 p-mb-3 p-text-center">${{slotProps.data.price}}</h4>
              </div>
            </div>
          </div>
        </template>
      </Carousel>
    </div>
  </div>
  <div class="p-px-6 p-pt-3">
    <div class="card">
      <Carousel :value="products" :numVisible="3" :numScroll="1" :responsiveOptions="responsiveOptions" class="custom-carousel" :circular="true" :autoplayInterval="3000">
        <template #header>
          <div class="p-d-flex p-ai-center">
            <h1 class="p-mr-auto">Kompyuterlar</h1>
            <div class="p-ml-auto">
              <h3 class="p-d-inline p-mr-2">Hammasini ko'rish</h3>
              <i class="pi pi-arrow-right"></i>
            </div>
          </div>
        </template>
        <template #item="slotProps">
          <div class="product-item p-grid">
            <div class="product-item-content">
              <div class="p-mb-3">
                <img src="https://primefaces.org/primevue/showcase/demo/images/product/blue-t-shirt.jpg" :alt="slotProps.data.name" class="product-image" />
              </div>
              <div>
                <h3 class="p-mb-1 p-text-center">{{slotProps.data.name}}</h3>
                <h4 class="p-mt-0 p-mb-3 p-text-center">${{slotProps.data.price}}</h4>
              </div>
            </div>
          </div>
        </template>
      </Carousel>
    </div>
  </div>
</template>

<script>
import {defineComponent} from "vue";

export default defineComponent({
  data() {
    return {
      menus: [
        {
          label: "O'zbek tili"
        },
        {
          label: 'Rus tili'
        }
      ],
      products: [
        {
          name: "T-Shirt",
          price: 12
        },
        {
          name: "T-Shirt",
          price: 12
        },
        {
          name: "T-Shirt",
          price: 12
        },
        {
          name: "T-Shirt",
          price: 12
        },
        {
          name: "T-Shirt",
          price: 12
        }
      ],
      images: [
        {
          itemImageSrc: 'https://www.vladivlad.com/wp-content/gallery/Top-Photo-Panoramas-3-1/IMG_5129_Panorama1_wide-636.jpg'
        },
        {
          itemImageSrc: 'https://thumbs.dreamstime.com/b/banner-winter-landscape-road-trees-covered-snow-sky-sunlight-frozen-tree-branches-copy-space-soft-focus-147993743.jpg'
        },
        {
          itemImageSrc: 'https://thumbs.dreamstime.com/b/banner-white-cherry-blossom-sakura-spring-time-against-blue-sky-nature-background-soft-focus-banner-white-cherry-blossom-sakura-208909127.jpg'
        },
        {
          itemImageSrc: 'https://3.bp.blogspot.com/-j2Y_Dhu1eYo/XACiPFcuuuI/AAAAAAAAZ8A/epQog6JFXp4y4JKMd922kUy5c7tXPv5CwCLcBGAs/s1600/11Photo0068.jpg'
        },
        {
          itemImageSrc: 'https://1.bp.blogspot.com/-1ucLdkxKDL8/XAC0dspo9LI/AAAAAAAAZ8Y/5HY6W9yHEdkNjR3sJMNRtXD5DiJkjhMnQCLcBGAs/s1600/13Photo0073.jpg'
        }
      ],
      items: [
        {
          label: 'Biz haqimizda'
        },
        {
          label: 'Biz haqimizda'
        },
        {
          label: 'Biz haqimizda'
        },
        {
          label: 'Biz haqimizda'
        },
        {
          label: 'Biz haqimizda'
        }
      ],
      responsiveOptions: [
        {
          breakpoint: '1024px',
          numVisible: 5
        },
        {
          breakpoint: '768px',
          numVisible: 3
        },
        {
          breakpoint: '560px',
          numVisible: 1
        }
      ]
    }
  },
  methods: {
    toggle(event) {
      this.$refs.menu.toggle(event);
    }
  }
})
</script>
