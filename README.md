# local-scratch-archive

2026-10-10 设备磁盘清理时，从这里删掉的本地草稿工程的**源码与笔记**备份。

只保留源码、配置、脚本和文档；构建产物（build/、gradle 缓存）、node_modules、二进制 assets、CI 下载产物、日志转储均已剔除。所以这里不能直接编译运行，需要按各项目自己的 build 脚本还原依赖。

## 内容

workspace/ 下是 Operit 工作区里的草稿工程：

- scriptc-try：scriptc 交叉编译试验（TS→原生，Android 目标探测）
- scratch-08：ZCode 内核链接/加载器试验，PROTOCOL-NOTES.md 与各 README 是主要产出
- zfull：ZCode 全量导出/构建脚本与报告、profiles、compat 兼容层
- zcode-port：把 zcode 内核以 .so + JNI 方式移植的最小工程（build.sh、jni、port-entry*.ts、profile*.json）
- zgh：Android 侧工程骨架与 zcode-adaptations.patch
- zgh-logs：推送与构建过程日志
- zcode-core-apk：Android 壳工程源码（app/src 仅保留 java 与 manifest，assets 里的 node/zcode 二进制约 190MB 未保留）
- scriptc-android-demo：scriptc 安卓库模式最小样例（lib.ts、probe.c、profile.json）
- zcode-refs：ZCode 界面参考截图
- HANDOFF.md、HANDOFF-2026-09-29.md：当时的交接文档

home/ 下是 /home 里的自建小工程：

- jbshell：just-bash 的 Android 壳（com.jbshell）
- splitstep：基于 Shizuku 的分屏/虚拟显示实验（com.splitstep.app）
- zcode-android：ZCode 原生核心的最早 Android 壳（com.zcode.port）

## 还原方式

项目都是 Gradle 或 pnpm/npm 工程，进对应目录后按常规还原：Gradle 需要自己补 local.properties 与 SDK 路径，Node 工程执行 install 即可。

## 相关记录

被删掉的可重建大件（Lawnchair 源码包、OpenFlip 解包副本、nowinandroid 快照、各类 build 产物与 CI 下载物）没有备份，需要时从各自上游仓库重新拉取。其余上下文见同目录清理记录与设备上的 README-removed-repos.md。
