# OrcaSlicer

<div align="center">
  <img alt="OrcaSlicer logo" src="resources/images/OrcaSlicer.png" width="15%" height="15%">
</div>

OrcaSlicer：一款开源的下一代精密3D打印切片软件。
通过超快切片、智能支撑生成和无缝打印机兼容性来优化您的打印效果——为完美而设计。

## 官方链接和社区

#### 官方网站：
<a href="https://www.orcaslicer.com/" style="font-size:2em;">OrcaSlicer.com</a>

#### GitHub仓库：
<a href="https://github.com/OrcaSlicer/OrcaSlicer"><img src="https://img.shields.io/badge/OrcaSlicer-181717?style=flat&logo=github&logoColor=white" width="200" alt="GitHub Logo"/> </a>

#### 关注我们：
<a href="https://twitter.com/real_OrcaSlicer"><img src="https://img.shields.io/badge/real__OrcaSlicer-000000?style=flat&logo=x&logoColor=white" width="200" alt="X Logo"/> </a>

#### 加入我们的Discord社区：
<a href="https://discord.gg/P4VE9UY9gJ"><img src="https://img.shields.io/badge/-Discord-5865F2?style=flat&logo=discord&logoColor=fff" width="200" alt="discord logo"/> </a>

## 项目简介

OrcaSlicer是一款开源的3D打印切片软件，源自Bambu Studio分支，专注于提供高精度、高速度和智能化的打印解决方案。

主要功能包括：
- **高级校准工具**：全面的套件，包括温度塔、流速、回抽等，以实现最佳性能
- **精确壁厚和接缝控制**：调整外壁间距并应用斜接缝以提高打印精度
- **夹心模式和多孔支撑**：使用变化填充图案和精确孔形以提高清晰度
- **悬垂和支撑优化**：修改几何形状以实现可打印的悬垂结构并精确放置支撑
- **粒度控制和自定义**：精确微调打印速度、层高、压力和温度
- **网络打印机支持**：与Klipper、PrusaLink和OctoPrint无缝集成，实现远程控制
- **鼠耳边缘和自适应床网**：自动边缘和自适应网格校准确保一致的附着力
- **用户友好界面**：直观的拖放设计，配有热门打印机的预设配置文件
- **开源和社区驱动**：由持续的社区贡献推动的定期更新
- **广泛的打印机兼容性**：支持广泛的打印机品牌，如Bambu Lab、Prusa、Creality、Voron等

## 工程结构

```
.
├── cmake/                      # 自定义CMake模块
│   └── modules/
├── deps/                       # 第三方依赖库的CMake构建脚本
│   ├── Blosc/
│   ├── Boost/
│   ├── CGAL/
│   ├── CURL/
│   ├── Cereal/
│   ├── EXPAT/
│   ├── FREETYPE/
│   ├── GLEW/
│   ├── GLFW/
│   ├── GMP/
│   ├── JPEG/
│   ├── MPFR/
│   ├── NLopt/
│   ├── NanoSVG/
│   ├── OCCT/
│   ├── OpenCSG/
│   ├── OpenCV/
│   ├── OpenEXR/
│   ├── OpenSSL/
│   ├── OpenVDB/
│   ├── PNG/
│   ├── Qhull/
│   ├── TBB/
│   ├── WebView2/
│   ├── ZLIB/
│   ├── libnoise/
│   ├── wxWidgets/
│   └── ...
├── deps_src/                   # 以源码形式引入的第三方库
│   ├── Shiny/                  # 性能分析库
│   ├── admesh/                 # STL网格处理库
│   ├── agg/                    # Anti-Grain Geometry图形库
│   ├── ankerl/                 # 高性能哈希表实现
│   ├── clipper/                # 多边形裁剪库
│   ├── earcut/                 # 多边形三角剖分库
│   ├── eigen/                  # 线性代数库
│   ├── expat/                  # XML解析库
│   ├── fast_float/             # 快速浮点数转换库
│   ├── glu-libtess/            # OpenGL GLU库的多边形三角剖分部分
│   ├── hidapi/                 # 跨平台HID设备访问库
│   ├── imgui/                  # 即时模式GUI库
│   ├── imguizmo/               # 3D变换小控件
│   ├── libigl/                 # 几何处理库
│   ├── libnest2d/              # 2D装箱算法库
│   ├── mcut/                   # 网格切割库
│   ├── minilzo/                # 数据压缩库
│   ├── miniz/                  # ZIP压缩和PNG编写库
│   ├── nanosvg/                # 简单的SVG解析器
│   ├── nlohmann/               # JSON处理库
│   ├── qhull/                  # 凸包计算库
│   ├── qoi/                    # QOI图像格式库
│   ├── semver/                 # 语义化版本号处理库
│   ├── spline/                 # 样条插值库
│   └── ...
├── resources/                  # 应用程序资源文件
│   ├── calib/                  # 校准模型
│   ├── data/                   # 数据文件
│   ├── fonts/                  # 字体文件
│   ├── handy_models/           # 常用模型
│   ├── hms/                    # 错误消息定义
│   ├── images/                 # 图像资源
│   ├── info/                   # 信息文件
│   ├── printers/               # 打印机配置文件
│   ├── profiles/               # 切片配置文件
│   ├── profiles_template/      # 配置文件模板
│   ├── shaders/                # 着色器程序
│   └── ...
├── sandboxes/                  # 独立示例程序
│   ├── aabb-evaluation/
│   ├── its_neighbor_index/
│   ├── meshboolean/
│   ├── opencsg/
│   ├── openvdb/
│   └── slasupporttree/
├── scripts/                    # 辅助脚本
│   ├── flatpak/
│   ├── linux.d/
│   ├── DockerBuild.sh
│   ├── DockerRun.sh
│   ├── Dockerfile
│   ├── HintsToPot.py
│   ├── auto-close-duplicates.ts
│   ├── backfill-duplicate-comments.ts
│   ├── generate_presets_vendors.py
│   ├── optimize_cover_images.py
│   ├── orca_extra_profile_check.py
│   ├── orca_filament_lib.py
│   ├── pack_profiles.sh
│   ├── run_gettext.bat
│   ├── run_gettext.sh
│   └── run_unit_tests.sh
├── src/                        # 源代码
│   ├── clipper2/               # Clipper2库包装
│   ├── dev-utils/              # 开发工具
│   ├── libslic3r/              # 核心切片算法库
│   │   ├── Algorithm/          # 算法实现
│   │   ├── Arachne/            # 壁厚生成算法
│   │   ├── CSGMesh/            # 布尔运算网格处理
│   │   ├── Execution/          # 执行控制
│   │   ├── Feature/            # 特殊功能模块
│   │   ├── Fill/               # 填充图案生成
│   │   ├── Format/             # 文件格式处理
│   │   ├── GCode/              # G代码生成和处理
│   │   ├── Geometry/           # 几何处理工具
│   │   ├── Optimize/           # 优化算法
│   │   ├── SLA/                # SLA打印相关
│   │   ├── Shape/              # 形状处理
│   │   ├── Support/            # 支撑结构生成
│   │   └── ...
│   ├── slic3r/                 # 应用程序主入口和GUI
│   │   ├── Config/             # 配置管理
│   │   ├── GUI/                # 图形用户界面
│   │   └── Utils/              # 工具类
│   ├── OrcaSlicer.cpp          # 应用程序入口点
│   ├── OrcaSlicer.hpp
│   └── OrcaSlicer_app_msvc.cpp
├── tests/                      # 测试代码
│   ├── catch2/                 # 测试框架
│   ├── data/                   # 测试数据
│   ├── fff_print/              # FFF打印测试
│   ├── libnest2d/              # 装箱算法测试
│   ├── libslic3r/              # 核心库测试
│   ├── sla_print/              # SLA打印测试
│   └── slic3rutils/            # 工具测试
└── tools/                      # 开发工具
```

## 技术架构

OrcaSlicer采用模块化设计，主要技术栈包括：

- **编程语言**：C++
- **构建系统**：CMake 3.13+
- **用户界面**：wxWidgets（带OpenGL）
- **主要依赖库**：
  - Boost 1.83.0
  - TBB (Intel Threading Building Blocks)
  - Eigen3
  - OpenVDB 5.0
  - GLEW, GLFW3
  - OpenSSL, CURL
  - NLopt 1.4
  - Freetype, PNG, ZLIB

## 编译说明

有关如何在各平台上编译OrcaSlicer的详细说明，请参考官方Wiki中的[构建指南](https://github.com/OrcaSlicer/OrcaSlicer/wiki/How-to-build)。

### Windows平台构建
```bash
# 构建全部内容
build_release_vs2022.bat

# 构建调试版本
build_release_vs2022.bat debug

# 仅构建依赖项
build_release_vs2022.bat deps

# 仅构建切片器（需先构建依赖项）
build_release_vs2022.bat slicer
```

### macOS平台构建
```bash
# 构建全部内容（依赖项和切片器）
./build_release_macos.sh

# 仅构建依赖项
./build_release_macos.sh -d

# 仅构建切片器（需先构建依赖项）
./build_release_macos.sh -s

# 使用Ninja生成器以加快构建速度
./build_release_macos.sh -x
```

### Linux平台构建
```bash
# 首次设置 - 安装系统依赖
./build_linux.sh
```

## 下载

### 稳定版发布

📥 **[下载最新稳定版](https://github.com/OrcaSlicer/OrcaSlicer/releases/latest)**
访问我们的GitHub发布页面获取OrcaSlicer的最新稳定版本，推荐大多数用户使用。

### 每夜构建版

🌙 **[下载最新每夜构建版](https://github.com/OrcaSlicer/OrcaSlicer/releases/tag/nightly-builds)**
探索OrcaSlicer的最新发展，欢迎对这些版本提供反馈。

## 支持

**OrcaSlicer**是一个开源项目，非常感谢所有赞助商和捐助者。
他们的慷慨支持使我能够购买 filament 和其他必要的 3D 打印材料用于项目开发。
谢谢你们！:)

## 背景

OrcaSlicer最初是从Bambu Studio分叉出来的，之前被称为BambuStudio-SoftFever。

[Bambu Studio](https://github.com/bambulab/BambuStudio)是从Prusa Research的[PrusaSlicer](https://github.com/prusa3d/PrusaSlicer)分叉而来，而后者则是来自Alessandro Ranellucci和RepRap社区的[Slic3r](https://github.com/Slic3r/Slic3r)。