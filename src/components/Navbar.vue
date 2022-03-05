<template>
    <nav>
        <div class="navbar">
            <div class="navbar-layout">
                <div class="instagram-logo">
                    <img src="@/assets/Instagram Logo.png" alt="Instagram">
                </div>
                <div class="search-area">
                    <div class="search-area-layout">
                        <img v-if="!searchClick" style="width:14px; height:14px; margin-right:4px;"
                            src="@/assets/magnify.png" alt="search">
                        <input @focus="searchClickFocus()" @blur="searchClickBlur()"
                            style="border:none; width:100%; outline:none; background-color: #fafafa; color:rgba(142,142,142,1); "
                            placeholder="Ara" type="text">
                        <img v-show="searchClick" style="width:16px; height:16px; cursor:auto;"
                            src="@/assets/close-circle.png" alt="close">
                    </div>
                </div>
                <div class="navigator">
                    <div class="navigator-icons">
                        <img v-for="tab in tabs" :key="tab" style="cursor:pointer;" :src="require('@/assets/'+tab.imgSrc)" :alt="tab.alt">
                        <img style="border-radius:50%; cursor:pointer;" src="@/assets/profil foto.jpg" alt="">
                    </div>
                </div>
            </div>
        </div>
    </nav>
</template>

<script>
    export default {
        data() {
            return {
                searchClick: false,
                tabs:[
                    {imgSrc:"home-clean.png", clickedimgSrc:"home-clean.png", path:"/", alt:"Ana Sayfa"},
                    {imgSrc:"direct-clean.png", clickedimgSrc:"direct-clean.png", path:"/direct/inbox", alt:"Direkt Mesaj"},
                    {imgSrc:"post-clean.png", clickedimgSrc:"post-clean.png", path:"/create/select", alt:"Yeni Gönderi"},
                    {imgSrc:"explore-clean.png", clickedimgSrc:"explore-clean.png", path:"/explore", alt:"Keşfet"},
                    {imgSrc:"flow-clean.png", clickedimgSrc:"flow-clean.png", path:"/accounts/activity", alt:"Hareket Akışı"},
                ]
            }
        },
        methods: {
            searchClickFocus() {
                this.searchClick = true;
            },
            searchClickBlur() {
                this.searchClick = false;
            }
        }
    }
</script>

<style scoped>
    .navbar {
        background-color: #fff;
        color: #262626;
        width: 100%;
        height: 60px;
        border-bottom: 1px solid rgba(219, 219, 219, 1);
        display: flex;
        flex-direction: column;
        position: fixed;
        top: 0;
        align-items: center;
        line-height: 18px;
        font-size: 14px;
        z-index: 1;
    }

    .navbar-layout {
        display: flex;
        width: 975px;
        height: 60px;
        padding: 0px 20px;
        justify-content: center;
        align-items: center;
    }

    .instagram-logo {
        cursor: pointer;
        width: 334px;
        height: 36px;
        padding: 7px 0px 0px 0px;
    }

    .search-area {
        border: 1px solid #dbdbdb;
        border-radius: 3px;
        background-color: #fafafa;
        width: 268px;
        display: flex;
        flex-direction: column;
        justify-content: center;
        color: #8e8e8e;
        text-align: left;
        font-weight: 300;
        height: 36px;
        cursor: text;
        padding: 0px 12px;
    }

    .search-area-layout {
        display: flex;
        flex-direction: row;
        align-items: center;
    }

    .navigator {
        flex: 1;
        height: 24px;
        display: flex;
        justify-content: flex-end;
        align-items: center;
        flex-wrap: wrap;
        flex-basis: 127px;
    }

    .navigator-icons {
        height: 24px;
        width: 278px;
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: stretch;
        padding: 0px 0px 0px 24px;
    }

    ::placeholder {
        /* Chrome, Firefox, Opera, Safari 10.1+ */
        color: rgba(142, 142, 142, 1);
        opacity: 1;
        font-weight: 100;
        /* Firefox */
    }

    :-ms-input-placeholder {
        /* Internet Explorer 10-11 */
        color: rgba(142, 142, 142, 1);
    }

    ::-ms-input-placeholder {
        /* Microsoft Edge */
        color: rgba(142, 142, 142, 1);
    }
</style>