# 2d游戏地图编辑器  

去年（2018）在和小伙伴们开发一款横版滚轴平台游戏，用到了  `Tiled Map` 编辑器,但在使用的过程中遇到了很多坑，用过它的人都知道。  

Tiled 功能很强大，但我需要的功能好像不是很多，是否能造个轮子？来简单快速的进行地图编辑

## 导入demo  

在左上角的导入按钮中，导入根目录中的 `Hello World.json` 地图资源文件，得益于 图片被转成了 `base 64` 字符串，你可以快捷的预览到地图效果，而不需要下载图片原资源  
## 导出demo  

现可以导出两种类型，一种编辑器可以解析的地图文件，一种游戏引擎解析的地图文件，点击左上角导出，可选择导出类型  

## 游戏内应用  
我写了一个简单的基于白鹭引擎的地图解析demo，你可以去这看它 [egret Map](https://github.com/checkmind/Map-editer-parse)  
地图json格式为：  
``` typescript

export interface matrixItem {
  src: string | undefined;
  width: number;
  row: number;
  col: number;
  height: number;
  name: string;
  extra?: Array<any: any>
}

export interface LayerItem {
  // 图层id
  id: number,
  // 图层名称
  name: string,
  // 是否显示
  show: boolean,
  matrix: Array<Array<matrixItem>>
}
export interface layer { 
  layers: Array<LayerItem>;
  // 表格横轴个数
  tableRow: number;
  // 表格纵轴个数
  tableCol: number;
  // 单元格宽度和高度
  boxWidth: number;
  boxHeight: number;
  name: string
}
```

## 编辑器  

### 新建项目  

![新建项目](https://i.loli.net/2019/04/21/5cbc45122f27d.png)  

### 功能简介  

![新建项目](https://i.loli.net/2019/04/21/5cbc45125c508.png) 

### 制作地图  

![新建项目](https://i.loli.net/2019/04/21/5cbc4512df1eb.png)  

### 改变图块属性  

每当图块改变时，之前已画在地图的图块不会随之改变，考虑到图块在使用时会有不同属性的需求，图块每次改变都是新的！  

![新建项目](https://i.loli.net/2019/04/21/5cbc4512e7cbe.png)  

### 关闭辅助线  

![新建项目](https://i.loli.net/2019/04/21/5cbc45130c064.png)  

## 现有功能  

- 图层：新建、上移、下移、重命名、删除
- 图块：新建、删除、编辑大小、添加额外属性  
- 工具：橡皮擦、导入、导出、撤销、取消撤销、全局属性
- 网格：是否显示网格  

## TODO  
没啥TODO了
