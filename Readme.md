#  Order Confirmation w/ Unfold Animation
此專案是練習的一個專案，使用單純HTML、CSS(SCSS)撰寫，用於呈現淡入及3D翻頁的Animation。

##  撰寫步驟

### HTML
wrapper
    card
        icon、h1、p
    card
        ul
            li*4
    card
        div
            button
            button

### CSS
1. 導入"Inter"字體
2. 使用body做出格子背景，::before做出更大的格子
3. 只有最上面的card使用h1跟p，所以直接在兩者上使用淡入的animation效果
4. 製作card外觀
    *   製作陰影：只有card最下層底部會顯示陰影，上面不會有下陰影，因此使用ntf-of-type(3)::before獨自添加有下陰影的程式碼
    *   第一張card的animation是淡入，下兩張是翻頁效果，所以使用first-of-type套用淡入效果，並把原始css的透明度調整為0(這樣才可以淡入)
            下兩張使用not(:first-of-type)套用翻頁效果，並讓其成為3D物件，事先調整X軸為-90度
    *   製作卡片之間的裁切線，用::after製作上框線(父元素做虛線會跟著圓角走)，用not(:first-of-type)::after，其中需注意的是：卡的四周是圓角，因此設定width為98%(扣除兩邊圓角的1%)，並讓left往右推進1%，使其在正確的位置上
