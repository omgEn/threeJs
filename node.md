## 摄像机

###  ArrayCamera -- 摄像机阵列

相机组：一个ArrayCamera实例中包含一组子摄像机，需为每个子相机定义viewport(视口)属性，决定了改子摄像机所渲染的视口区域的大小。

### Camera -- 摄像机

摄像机基类

### CubeCamera -- 立方相机

### OrthographicCamera -- 正交相机

在这种投影模式下，无论物体距离相机距离远或者近，在最终渲染的图片中物体的大小都保持不变。

这对于渲染2D场景或者UI元素是非常有用的。

### PerspectiveCamera -- 透视相机

### StereoCamera -- 立体相机

双透视摄像机


## 控制器
### DragControls -- 拖放控制器
该类被用于提供一个拖放交互
### FirstPersonControls
### FlyControls -- 飞行控制器
在3D空间中任意变换摄像机，且无任何限制
### OrbitControls -- 轨道控制器
使相机围绕目标进行轨道运动
* MapControls
### PointerLockControls -- 指针锁定控制器
适用于第一人称3D游戏
### TrackballControls -- 轨道球控制器
### TransformConttols -- 变换控制器

## 核心
### Object3D
### BufferAttribute
* Float64BuffferAttribute
* Float32BufferAttribute
* Float16BufferAttribute
* Uint32BufferAttribute
* Int32BufferAttribute
* Uint16BufferAttribute
* Int16BufferAttribute
* Uint8ClampedBufferAttribute
* Uint8BufferAttribute
* Int8BufferAttribute
### BufferGeometry
是面片、线或点几何体的有效表述。包括顶点位置，面片索引、法相量、颜色值、UV 坐标和自定义缓存属性值。使用 BufferGeometry 可以有效减少向 GPU 传输上述数据所需的开销。
### BufferAttribute
读取或编辑 BufferGeometry 中的数据

### Raycaster -- 光线投射
用于进行鼠标拾取（在三维空间中计算出鼠标移过了什么物体）。

## 灯光
### AmbientLight -- 环境光
会均匀的照亮场景中的所有物体。
不能用来投射阴影，因为它没有方向。
### AmbientLightProbe -- 环境光探针
### DirectionalLight -- 平行光
DirectionalLightHelper
沿着特定方向发射的光。这种光的表现像是无限远,从它发出的光线都是平行的。常用于模拟太阳光。
能投射阴影

### HemisphereLight -- 半球光
HemisphereLightHelper
光源直接放置于场景之上，光照颜色从天空光线颜色渐变到地面光线颜色。
半球光不能投射阴影
### HemisphereLightProbe --
### Light --
### LightProbe -- 光照探针

光照探针不发光
LightProbeHelper


### PointLight -- 点光源

从一个点向各个方向发射的光源

PointLightHelper

### RectAreaLight -- 平面光光源

 RectAreaLightHelper

平面光光源从一个矩形平面上均匀地发射光线。这种光源可以用来模拟像明亮的窗户或者条状灯光光源。

* 不支持阴影
* 只支持 MeshStandardMaterial 和 MeshPhysicalMaterial 两种材质。
* 必须在你的场景中加入 [RectAreaLightUniformsLib](https://threejs.org/examples/jsm/lights/RectAreaLightUniformsLib.js) ，并调用**init()**。

### SpotLight -- 聚光灯

光线从一个点沿一个方向射出，随着光线照射的变远，光线圆锥体的尺寸也逐渐增大。

#### SpotLightHelper



## 材质
### 材质常量
**面**
THREE.FrontSide
THREE.BackSide
THREE.DoubleSide
定义了哪一边的面将会被渲染 —— 正面，或是反面，还是两个面都渲染

**混合模式**

**深度模式**


### LineBasicMaterial -- 基础线条材质

### LineDashedMaterial --

### Materia --

### MeshBasicMateroal

### MeshDepthMaterial

### MeshLambertMaterial -- 

### MeshNormalMaterial --

### ShaderMaterial -- 着色器材质

## 物体
### Bone
继承Object3D
### Group
几乎与Object3D相同，其目的是使得组中对象在语法上的结构根据清晰。
### InstanceMesh -- 实例化网格
一种具有实例化渲染支持的特殊版本的Mesh。
### Line -- 线
### LineLoop -- 环线
一条头尾相接的连续的线。
### LinesSegments -- 线段
在若干对的顶点之间绘制的一系列的线。
### LOD -- 多细节层次
### Mesh -- 网格
### Points -- 点
### Skeleton -- 骨架
### SkinnedMesh -- 蒙皮网格
### Sprite --精灵


## 动画
### AnimationMixer
### AnimationAction



## 加载器

### AnimationLoader

以JSON格式来加载 AnimationClips 的一个类。内部使用 FileLoader 来加载文件。

### AudioLoader

用来加载 [AudioBuffer](https://developer.mozilla.org/en-US/docs/Web/API/AudioBuffer)的一个类。内部默认使用FileLoader来加载文件。

### BufferGeometryLoader

用来加载BufferGeometry的加载器。 内部使用FileLoader来加载文件。

### Cache

一个简单的缓存系统，内部使用FileLoader。

### CompressedTextureLoader

基于块的纹理加载器 (dds, pvr, ...)的抽象类。 内部使用FileLoader来加载文件。

### CubeTextureLoader

加载CubeTexture的一个类。 内部使用ImageLoader来加载文件。

### DataTextureLoader

用于加载二进制文件格式的(rgbe, hdr, ...)的抽象类。 内部使用FileLoader来加载文件， 和创建一个新的 DataTexture.

### FileLoader

使用XMLHttpRequest来加载资源的低级类，并由大多数加载器内部使用。 它也可以直接用于加载任何没有对应加载器的文件类型。

### ImageBitmapLoader

一个把Image加载为[ImageBitmap](https://developer.mozilla.org/en-US/docs/Web/API/ImageBitmap)的加载器。 ImageBitmap提供了一种异步且有效的资源的途径，用于在WebGL中渲染的纹理。
不像FileLoader, ImageBitmapLoader无需避免对同一的URL进行多次请求。

### ImageLoader

用来加载一个Image的加载器。 内部使用FileLoader来加载文件，并被 CubeTextureLoader、ObjectLoader、TextureLoader所使用。

###  Loader  --  加载器基类

### LoaderUtils

具有多个实用的加载器函数功能的对象

### MaterialLoader

以JSON格式来加载Material的加载器。 默认使用FileLoader进行加载文件。

### ObjectLoader

此加载器内部使用FileLoader进行加载文件。

###  TextureLoader

加载texture的一个类。 内部使用ImageLoader来加载文件。



## 辅助对象

### ArrowHelper

### AxesHelper

坐标轴，红色：X轴，绿色：Y轴，蓝色：Z轴

## BoxHelper
用于图形化地展示对象世界轴心对齐的包围盒的辅助对象。

### Box3Helper

### GridHelper 

坐标格辅助对象. 坐标格实际上是2维线数组.

### PolarGridHelper

极坐标格辅助对象. 坐标格实际上是2维线数组.



## 常用代码片段
````js
renderer = new THREE.WebGLRenderer( { antialias: true } );
renderer.setPixelRatio( window.devicePixelRatio );
renderer.setSize( window.innerWidth, window.innerHeight );
document.body.appendChild( renderer.domElement );

function onWindowResize() {

    camera.aspect = window.innerWidth / window.innerHeight;
    camera.updateProjectionMatrix();

    renderer.setSize( window.innerWidth, window.innerHeight );

}

function animate() {

    requestAnimationFrame( animate );

    controls.update(); // only required if controls.enableDamping = true, or if controls.autoRotate = true

    render();

}

function render() {

    renderer.render( scene, camera );

}

````