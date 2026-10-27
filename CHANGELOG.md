# Changelog / 更新日志

All notable changes to CCNVR are documented here.

这里记录 CCNVR 的所有重要更新。

## [1.0.2] - 2026-10-25

- 新增 电视墙多分屏：支持 4/6/9/16/32 分屏和异型布局，可拖拽换位、关闭单格、云台控制 — Added multi-view video wall with 4/6/9/16/32 and irregular layouts, drag-to-swap, per-pane close and PTZ control
- 新增 ONVIF 告警接入：支持移动侦测、区域入侵、绊线、遮挡、视频丢失、报警输入等事件 — Added ONVIF alarms for motion, intrusion, tripwire, tamper, video loss and alarm input events
- 新增 统一告警中心：国标与 ONVIF 告警集中展示，支持来源、类型筛选和详情查看 — Added a unified alarm center for GB28181 and ONVIF alarms, with source/type filters and detail view
- 新增 界面设置：分屏顶部信息条常亮、画面拉伸填充 — Added interface settings for always-visible multi-view top bar and stretched video fill
- 优化 多分屏在顶部导航下的布局、设备树和全屏体验 — Improved multi-view layout under top navigation, channel list and fullscreen behavior
- 修复 国标告警偶发不入库、通道信息缺失的问题 — Fixed intermittent GB28181 alarm persistence and missing channel information

## [1.0.1] - 2026-10-22

- 新增 用户角色权限管理和摄像头分配 — Added user roles and permissions, with per-user camera assignment
- 新增 录像视频快照 — Added video snapshots for recordings
- 修复 部分视频播放卡顿问题 — Fixed playback stuttering for some videos
- 修复 ONVIF 设备状态异常 — Fixed incorrect ONVIF device status
- 优化 部分直播流畅度 — Improved smoothness for some live streams
- 优化 网页手机端支持 — Improved mobile web support
- 优化 日志输出，减少冗余日志 — Improved log output and reduced redundant logs

## [1.0.0] - 2026-10-18

- 新增 RTSP、ONVIF、GB28181、RTMP 协议支持 — Added support for RTSP, ONVIF, GB28181 and RTMP
- 新增 HTTP-FLV、WS-FLV、WebRTC 直播分发 — Added live streaming over HTTP-FLV, WS-FLV and WebRTC
- 新增 录像回放、录像下载、录像管理 — Added recording playback, download and management
- 新增 系统资源监控、系统日志、系统配置 — Added system resource monitoring, system logs and system configuration
- 新增 GB28181 告警、ONVIF 设备云台控制、GB28181 设备云台控制 — Added GB28181 alarms, ONVIF PTZ control and GB28181 PTZ control
- 新增 H.265 支持，兼容 Web H.265 解码 — Added H.265 support, including in-browser H.265 decoding
