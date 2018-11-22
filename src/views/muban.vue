<template>
    <div class="page">
        <swiper :options="swiperOption" ref="mySwiper" >
            <!-- slides -->
            <swiper-slide><img class="main-img" src="../assets/images/shouye_nvsheng_haircare_five.png"></swiper-slide>
            <swiper-slide><img class="main-img" src="../assets/images/shouye_nvsheng_haircare_five.png"></swiper-slide>
            <swiper-slide><img class="main-img" src="../assets/images/shouye_nvsheng_haircare_five.png"></swiper-slide>
            <swiper-slide><img class="main-img" src="../assets/images/shouye_nvsheng_haircare_five.png"></swiper-slide>
            <swiper-slide><img class="main-img" src="../assets/images/shouye_nvsheng_haircare_five.png"></swiper-slide>

        </swiper>
        <div class="swiper-pagination"   id="pagination"></div>
    </div>
</template>

<script>
    var name='aa';
    export default {
        data () {
            return {
                swiperOption: {
                    slidesPerView: "auto",
                    centeredSlides: !0,
                    watchSlidesProgress: !0,
                    pagination: ".swiper-pagination",
                    paginationClickable: !0,
                    paginationBulletRender: function (swiper, index, className) {
                        switch (index) {
                            case 0:
                                name = "龙猫";
                                break;
                            case 1:
                                name = "熊猫";
                                break;
                            case 2:
                                name = "小白";
                                break;
                            case 3:
                                name = "仓鼠";
                                break;
                            case 4:
                                name = "兔子";
                                break;
                            default:
                                name = ""
                        }
                        return '<span class="' + className + '"><i>' + name + '</i></span>';

                    },
                    onProgress: function (a) {
                        var b, c, d,scale,es;
                        for (b = 0; b < a.slides.length; b++) c = a.slides[b], d = c.progress, scale = 1 - Math.min(Math.abs(.2 * d), 1),
                            es = c.style,
                            es.opacity = 1 - Math.min(Math.abs(d / 2), 1),
                            es.webkitTransform = es.MsTransform =
                            es.msTransform = es.MozTransform =
                            es.OTransform = es.transform =
                            "translate3d(0px,0," + -Math.abs(150 * d) + "px)"
                    },
                    onSetTransition: function (a, b) {
                        var es;
                        for (var c = 0; c < a.slides.length; c++) es = a.slides[c].style, es.webkitTransitionDuration = es.MsTransitionDuration = es.msTransitionDuration = es.MozTransitionDuration = es.OTransitionDuration = es.transitionDuration = b + "ms"
                    }
                }
            }
        },
        mounted() {
            console.log('app init')

            console.log(
                'This is current swiper instance object', this.mySwiper,
                'It will slideTo banners 3')
        }
    }
</script>

<style >
    @import "../assets/css/swiper.min.css";
    @import "../assets/css/choumei.min.css";
</style>