轮播滑动效果 --- transition="transform .3s"

hover 旋转放大

.box {
    border-style: solid;
    border-width: 1px;
    display: block;
    width: 100px;
    height: 100px;
    background-color: #0000FF;
    -webkit-transition:width 2s, height 2s,
        background-color 2s, -webkit-transform 2s;
    transition:width 2s, height 2s, background-color 2s, transform 2s;
}
.box:hover {
    background-color: #FFCCCC;
    width:200px;
    height:200px;
    -webkit-transform:rotate(180deg);
    transform:rotate(180deg);
}


添加背景图：
bg={`url(${banner}) top center no-repeat`} bgSize="cover"

bg={`url(${footer}) no-repeat`} bgPosition="center 101%" bgSize="100% 280px"