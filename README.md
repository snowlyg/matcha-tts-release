# matcha-tts-release

Matcha zh-en 离线神经 TTS 引擎的 Android 发布仓库（APK 分发）。基于 sherpa-onnx 1.12.18，装完即用、完全离线、不联网。

源码与训练工程在私有仓库维护，本仓库只存放可安装的 APK 发布件。

## 下载

到 [Releases](https://github.com/snowlyg/matcha-tts-release/releases) 页面，按设备 ABI 选择对应 APK：

| 架构 | 适用设备 |
| --- | --- |
| arm64-v8a | 绝大多数现代 Android 手机 / 平板 |
| armeabi-v7a | 较老的 32 位 ARM 设备 |
| x86_64 | x86_64 模拟器 / 设备 |
| x86 | 32 位 x86 模拟器 / 设备 |

## 版本

- **v0.0.2**（tag `android-tts-1.12.18-r2`）：包名 `com.google.android.tts`、纯 service 无界面，替换谷歌 TTS 后可正常播报。
- **v0.0.1**（tag `android-tts-1.12.18`）：首个发布版本。

## 性能

中文 / 英文，16 kHz，4 线程推理；端侧实时合成（同模型真机取证 RTF≈1.2，≤2 预算内）。首次冷启动后台加载模型，之后实时。

> 替换系统 TTS 后需重启播报应用：其静态持有的旧 TextToSpeech 实例不会自动重连。