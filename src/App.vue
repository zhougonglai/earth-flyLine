<script setup lang="ts">
import { onMounted } from "vue";
// import worldTexture from "./image/earth.png";
import worldTexture from "./image/tencent_earth.png";
import world from "./map/world.json";
import chart from "@/entry";
import ChartScene from "@/lib/chartScene";
let chartInstance: ChartScene;
let chartInstance1: ChartScene;

const geoJson: any = world;
chart.registerMap("world", geoJson);
onMounted(() => {
  const dom1 = document.getElementById("container1");
  if (dom1) {
    chartInstance1 = chart.init({
      dom: dom1,
      helper: false,
      map: "world",
      autoRotate: true,
      mode: "3d",
      config: {
        bgColor: 'white',
        R: 150,
        texture: worldTexture,
        earth: {
          // color: "#13162c",
          color: "white",
        },
        mapStyle: {
          areaColor: "red",
          lineColor: "blue",
        },
        spriteColor: "white", //光圈
        pathStyle: {
          color: "#2196f3", //飞线路径配置
        },
        flyLineStyle: {
          //飞线样式配置
          color: "#2196f3",
        },
        scatterStyle: {
          //涟漪
          color: "#2196f3",
        },
        // hoverRegionStyle: {
        //   areaColor: "#cd79ff",
        // },
        // regions: {
        //   China: {
        //     areaColor: "#2e3564",
        //   },
        // },
      },
    });
    const initData = [
      // {
      //   from: {
      //     id: "1",
      //     lon: -23.0075,
      //     lat: 50.4296,
      //     // style: {
      //     //   color: "#ff0000",
      //     //   duration: 2000,
      //     //   delay: 0,
      //     //   repeat: 1,
      //     //   onComplete: (data: any) => {
      //     //     //do something
      //     //   },
      //     // },
      //   },
      //   to: { id: 2, lon: 26.1223, lat: -7.8756 },
      //   // style: {
      //   //   pathStyle: {
      //   //     color: "#ff0000", //飞线路径配置
      //   //   },
      //   //   flyLineStyle: {
      //   //     //飞线样式配置
      //   //     color: "#0000ff",
      //   //   },
      //   // },
      // },
      // 广州 - 香港
      {
        from: {
          lon: 113.17, lat: 23.8
        },
        to: {
          lon: 114.15, lat: 22.15
        }
      },
      // 广州 - 新加坡
      {
        from: {
          lon: 113.17, lat: 23.8
        },
        to: {
          lon: 103.51, lat: 1.18
        }
      },
      // 广州 - 墨尔本
      {
        from: {
          lon: 113.17, lat: 23.8
        },
        to: {
          lon: 144.58, lat: 37.50
        }
      },
      // 广州 - 台湾
      {
        from: {
          lon: 113.17, lat: 23.8
        },
        to: {
          lon: 124.34, lat: 25.56
        }
      },
      // 广州 - 马来西亚
      {
        from: {
          lon: 113.17, lat: 23.8
        },
        to: {
          lon: 119, lat: 7
        }
      },
      // 广州 - 菲律宾
      {
        from: {
          lon: 113.17, lat: 23.8
        },
        to: {
          lon: 127, lat: 17
        }
      },
      // 广州 - 泰国
      {
        from: {
          lon: 113.17, lat: 23.8
        },
        to: {
          lon: 101.01890, lat: 16.42992
        }
      },
      // 广州 - 迪拜
      {
        from: {
          lon: 113.17, lat: 23.8
        },
        to: {
          lon: 55.30883, lat: 25.26952
        }
      },
      // 广州 - 越南
      {
        from: {
          lon: 113.17, lat: 23.8
        },
        to: {
          lon: 108.32982, lat: 13.85259
        }
      },
      // 上海 经纬度：121.48054 , 31.23593  - 韩国 经纬度：127.88650 , 36.04160
      {
        from: {
          lon: 121.48054, lat: 31.23593
        },
        to: {
          lon: 127.88650, lat: 36.04160
        }
      },
      // 上海 经纬度：121.48054 , 31.23593  - 日本 经纬度：140.15836 , 38.07746
      {
        from: {
          lon: 121.48054, lat: 31.23593
        },
        to: {
          lon: 140.15836, lat: 38.07746
        }
      },
      // 上海 经纬度：121.48054 , 31.23593  - 美国西雅图 经纬度：-122.32945 , 47.60357
      {
        from: {
          lon: 121.48054, lat: 31.23593
        },
        to: {
          lon: 122.32945, lat: 47.60357
        }
      },
      // 上海 经纬度：121.48054 , 31.23593  - 美国洛杉矶 经纬度：-118.24532 , 34.05349
      {
        from: {
          lon: 121.48054, lat: 31.23593
        },
        to: {
          lon: 118.24532, lat: 34.05349
        }
      },
      // 上海 经纬度：121.48054 , 31.23593  - 美国华盛顿 经纬度：-117.91040 , 46.31586
      {
        from: {
          lon: 121.48054, lat: 31.23593
        },
        to: {
          lon: 117.91040, lat: 46.31586
        }
      },
      // 北京 经纬度：116.41339 , 39.91092 - 法兰克福 经纬度：8.68213 , 50.11092
      {
        from: {
          lon: 116.41339, lat: 39.91092
        },
        to: {
          lon: 8.68213, lat: 50.11092
        }
      },
      // {
      //   from: { lon: 142.8123, lat: -58.9813 },
      //   to: { lon: 157.0064, lat: 10.7816 },
      // },
      // {
      //   from: { lon: -175.6286, lat: 72.8359 },
      //   to: { lon: -39.071, lat: -35.438 },
      // },
      // {
      //   from: { lon: 178.7439, lat: 25.8303 },
      //   to: { lon: 137.19, lat: 17.118 },
      // },
      // {
      //   from: { lon: -162.6725, lat: 37.277 },
      //   to: { lon: -37.1681, lat: 38.5162 },
      // },
      // {
      //   from: { lon: -7.5945, lat: 37.2754 },
      //   to: { lon: 41.4114, lat: 41.5946 },
      // },
      // {
      //   from: { lon: -32.529, lat: -75.5152 },
      //   to: { lon: 153.8553, lat: -39.7648 },
      // },
      // {
      //   from: { lon: -59.8013, lat: -19.3771 },
      //   to: { lon: 171.8885, lat: 71.9592 },
      // },
      // {
      //   from: { lon: 103.1917, lat: 40.3037 },
      //   to: { lon: 38.4639, lat: 89.3409 },
      // },
      // {
      //   from: { lon: 92.6181, lat: -75.1948 },
      //   to: { lon: 23.1154, lat: 54.6066 },
      // },
      // {
      //   from: { lon: -25.6806, lat: 32.5669 },
      //   to: { lon: 26.8173, lat: -23.3473 },
      // },
      // {
      //   from: { lon: -144.6571, lat: 15.0555 },
      //   to: { lon: 114.9389, lat: 25.1615 },
      // },
      // {
      //   from: { lon: 11.6155, lat: -19.31 },
      //   to: { lon: 88.6194, lat: 33.1181 },
      // },
      // {
      //   from: { lon: 162.8275, lat: 50.742 },
      //   to: { lon: -128.8369, lat: 8.1522 },
      // },
      // {
      //   from: { lon: -89.4121, lat: -47.4232 },
      //   to: { lon: -148.0117, lat: -7.9949 },
      // },
      // {
      //   from: { lon: -146.2076, lat: -83.4571 },
      //   to: { lon: 133.6261, lat: -37.512 },
      // },
      // {
      //   from: { lon: -105.7075, lat: 8.3978 },
      //   to: { lon: 48.2922, lat: 57.0248 },
      // },
      // {
      //   from: { lon: 39.599, lat: 81.3458 },
      //   to: { lon: 113.3542, lat: 44.2259 },
      // },
      // {
      //   from: { lon: -154.6959, lat: -20.9316 },
      //   to: { lon: -95.5265, lat: -74.9423 },
      // },
      // {
      //   from: { lon: -168.7863, lat: 85.2333 },
      //   to: { lon: -84.0216, lat: -35.0322 },
      // },
    ];
    // chartInstance.setData("flyLine", initData);
    chartInstance1.setData("flyLine", initData);
    // chartInstance1.addData("point", [
    //   {
    //     lon: -43.0075,
    //     lat: -40.4296,
    //     style: {
    //       color: "yellow",
    //       duration: 2000,
    //       delay: 0,
    //       repeat: 1,
    //       onComplete: (data: any) => {
    //         //do something
    //       },
    //     },
    //   },
    // ]);
  }
});
function add() {
  chartInstance.addData("flyLine", [
    {
      from: { id: 1, lon: 112.45, lat: 34.62 },
      to: { id: 2, lon: 114, lat: 22 },
    },
  ]);
}

function del() {
  chartInstance.remove("flyLine", []);
}
</script>

<template>
  <div id="container1"></div>
  <!-- <div id="container"></div> -->
</template>

<style lang="less" scoped>
#container1 {
  width: 1200px;
  height: 800px;
}
</style>
