  // 百度地图API功能
  var map = new BMap.Map("container");    // 创建Map实例
  map.centerAndZoom(new BMap.Point(116.404, 39.915),20);  // 初始化地图,设置中心点坐标和地图级别

  // 创建地址解析器实例
  var myGeo = new BMap.Geocoder();
  // 将地址解析结果显示在地图上,并调整地图视野
  myGeo.getPoint("北京市海淀区", function(point){
    if (point) {
      map.centerAndZoom(point, 20);
      map.addOverlay(new BMap.Marker(point));
    }else{
      alert("您选择地址没有解析到结果!");
    }
  }, "北京市");
  map.enableScrollWheelZoom(true);

 /* //添加地图类型控件
  map.addControl(new BMap.MapTypeControl({
    mapTypes:[
      BMAP_NORMAL_MAP,
      BMAP_HYBRID_MAP
    ]}));
  map.setCurrentCity("北京");          // 设置地图显示的城市 此项是必须设置的
  map.enableScrollWheelZoom(true);     //开启鼠标滚轮缩放*/