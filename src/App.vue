<script setup lang="ts">
import { onMounted } from "vue";
// import worldTexture from "./image/earth.png";
import worldTexture from "./image/tencent_earth.png";
import world from "./map/world.json";
import chart from "@/entry";
import ChartScene from "@/lib/chartScene";
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
      rotateSpeed: .004,
      config: {
        bgColor: '#f5f7fa',
        R: 220,
        texture: worldTexture,
        earth: {
          // color: "#13162c",
          color: "white",
        },
        // mapStyle: {
        //   areaColor: "red",
        //   lineColor: "blue",
        // },
        spriteColor: "white", //光圈
        pathStyle: {
          // color: "#507FE4", //飞线路径配置
          color: "#b0c7ec",
          size: 0.1,
        },
        flyLineStyle: {
          //飞线样式配置
          color: "#507FE4",
          size: 0.05,
        },
        scatterStyle: {
          //涟漪
          color: "white",
          size: 1,
          // duration: 0,
          // delay: 0,
          // repeat: 0
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
      // 广州 经纬度：113.27143 , 23.13534 - 香港
      {
        from: {
          lon: 113.27143, lat: 23.13534
        },
        to: {
          lon: 114.15, lat: 22.15
        }
      },
      // 广州 - 新加坡
      {
        from: {
          lon: 113.17, lat: 23.13534
        },
        to: {
          lon: 103.51, lat: 1.18
        }
      },
      // 广州 - 墨尔本   经纬度：144.96306 , -37.81363
      {
        from: {
          lon: 113.17, lat: 23.13534
        },
        to: {
          lon: 144.96306, lat: -37.81363
        }
      },
      // 广州 - 台湾 经纬度：121.57463 , 25.04094
      {
        from: {
          lon: 113.17, lat: 23.13534
        },
        to: {
          lon: 121.57463, lat: 25.04094
        }
      },
      // 广州 - 马来西亚
      {
        from: {
          lon: 113.17, lat: 23.13534
        },
        to: {
          lon: 119, lat: 7
        }
      },
      // 广州 - 菲律宾 经纬度：123.04535 , 11.06157
      {
        from: {
          lon: 113.17, lat: 23.13534
        },
        to: {
          lon: 123.04535, lat: 11.06157
        }
      },
      // 广州 - 泰国
      {
        from: {
          lon: 113.17, lat: 23.13534
        },
        to: {
          lon: 101.01890, lat: 16.42992
        }
      },
      // 广州 - 迪拜 经纬度：55.30883 , 25.26952
      {
        from: {
          lon: 113.17, lat: 23.13534
        },
        to: {
          lon: 55.30883, lat: 25.26952
        }
      },
      // 广州 - 越南
      {
        from: {
          lon: 113.17, lat: 23.13534
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
          lon: -122.32945, lat: 47.60357
        }
      },
      // 上海 经纬度：121.48054 , 31.23593  - 美国洛杉矶 经纬度：-118.24532 , 34.05349
      {
        from: {
          lon: 121.48054, lat: 31.23593
        },
        to: {
          lon: -118.24532, lat: 34.05349
        }
      },
      // 上海 经纬度：121.48054 , 31.23593  - 美国华盛顿 经纬度：-83.88307 , 41.96398
      {
        from: {
          lon: 121.48054, lat: 31.23593
        },
        to: {
          lon: -83.88307, lat: 41.96398
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
      // 北京 经纬度：116.41339 , 39.91092 - 伦敦 经纬度：-0.12776 , 51.50735
      {
        from: {
          lon: 116.41339, lat: 39.91092
        },
        to: {
          lon: -0.12776, lat: 51.50735
        }
      },
      // 北京 经纬度：116.41339 , 39.91092 - 莫斯科 经纬度：37.61501 , 55.75696
      {
        from: {
          lon: 116.41339, lat: 39.91092
        },
        to: {
          lon: 37.61501, lat: 55.75696
        }
      },
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
</script>

<template>
  <div id="container1"></div>
  <!-- <div id="container"></div> -->
</template>

<style lang="less" scoped>
#container1 {
  width: 1200px;
  height: 900px;
}
</style>
