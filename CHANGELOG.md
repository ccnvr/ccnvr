# Changelog

All notable changes to CCNVR are documented here.
Format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/); versions follow [SemVer](https://semver.org/).

## [1.0.1] - 2026-10-11

First stable release.

### Added

- RTSP, ONVIF, GB28181 and RTMP protocol support
- HTTP-FLV, WS-FLV and WebRTC live streaming distribution
- Video playback, video download and video management
- System resource monitoring, system logs and system configuration
- GB28181 alarm handling, ONVIF device PTZ control and GB28181 device PTZ control
- H.265 support, including in-browser H.265 decoding

### Notes

- Free edition runs 5 channels; a license file is imported in **System info → License** and takes effect without a restart.
- Docker deployments must mount `/opt/media/bin/configs` — it holds the config, database, machine ID and license file.
- GB28181 device registration requires UDP 15060 in addition to TCP.
