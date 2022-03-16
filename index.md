<html>
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
    <meta name="viewport" content="initial-scale=1.0, user-scalable=no" />
    <style type="text/css">
    body, html{width: 100%;height: 100%;overflow: hidden;margin:0;font-family:"微软雅黑";}
    #allmap {
        width: 1400px;
        height: 700px;
        margin: 0;
    }
    </style>

    <script type="text/javascript" src="https://api.map.baidu.com/api?v=2.0&ak=cejMEm3GWkIOiBriHkIfGfeSj0GLyxQA"></script>
    <title>李沛谕地图展示</title>
</head>
<body>
    <div id="allmap"></div>
</body>
</html>

<script type="text/javascript">
    // 百度地图API功能
    var map = new BMap.Map("allmap");    // 创建Map实例
    map.centerAndZoom(new BMap.Point(116.403874,39.914888), 11);  // 初始化地图,设置中心点坐标和地图级别（）
    map.setCurrentCity("北京");          // 设置地图显示的城市 此项是必须设置的
    map.enableScrollWheelZoom(true);     //开启鼠标滚轮缩放
    var navigationControl = new BMap.NavigationControl();//创建平移缩放控件 
    
    var cr = new BMap.CopyrightControl({
            anchor: BMAP_ANCHOR_TOP_LEFT,
            offset: new BMap.Size(20, 20)
        });   //设置版权控件位置
	    map.addControl(cr); //添加版权控件
        var bs = map.getBounds();   //返回地图可视区域
	    cr.addCopyright({
            id: 1, 
            content: "<img src='https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fs1.lvjs.com.cn%2Fuploads%2Fpc%2Fplace2%2F2015-02-09%2F55b0290f-fe14-4cb8-8c81-c2b7639928ec_960_.jpg&refer=http%3A%2F%2Fs1.lvjs.com.cn&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1650018314&t=d2d7969c23c1888f1102170a7e7672bc' width='400px' height='200px'/><a href='#' style='font-size:16px;color:#000'>", 
            bounds: bs
        });

    var opts = {
    position: new BMap.Point(116.403874,39.914888), // 指定文本标注所在的地理位置
};
// 创建文本标注对象
var label = new BMap.Label('点击查看介绍', opts);

map.addOverlay(label);

label.addEventListener("click",function()//添加标签的点击事件
                                  {
                                      window.open("https://baike.baidu.com/item/%E5%8C%97%E4%BA%AC/128981") ;//超级链接                                
                                  }
    )



</script>
