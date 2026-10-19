# CCNVR

**Lightweight self-hosted NVR for ONVIF / RTSP / RTMP / GB28181 cameras.**

Live view · recording & playback · PTZ · WebRTC / FLV low-latency streaming · H.265 · Windows / Linux / Docker

[Website](https://ccnvr.com) · [Docs](https://ccnvr.com/docs/getting-started) · [Download](https://github.com/ccnvr/ccnvr/releases/latest) · [中文](#中文)

![CCNVR architecture](https://ccnvr.com/img/architecture_en.png)

> This repository is the **distribution and support channel** for CCNVR: release binaries, changelog and issue tracking.
> CCNVR is proprietary software — the source code is **not** published. See [LICENSE](LICENSE).

---

## What is CCNVR

CCNVR is a single-binary network video recorder for small and mid-size deployments. It talks to cameras over ONVIF, RTSP, RTMP and GB28181, records to local disk, and re-publishes the same streams to browsers with sub-second latency over WebRTC / HTTP-FLV / WS-FLV — no plugins, no cloud account, no external media server to install.

A static ffmpeg is bundled, so a fresh machine needs nothing but the package itself.

## Features

| | |
| --- | --- |
| **Ingest** | RTSP, ONVIF, RTMP, GB28181 |
| **Web playback** | WebRTC, HTTP-FLV, WS-FLV (no plugin, sub-second latency) |
| **Distribution** | Optional RTSP (2554) and RTMP (1935) re-publish |
| **Recording** | Continuous / scheduled recording, playback, download, storage management |
| **PTZ** | ONVIF and GB28181 PTZ control, GB28181 alarm handling |
| **Codec** | H.264 and H.265, including in-browser H.265 decoding |
| **Operations** | System resource monitoring, system logs, web-based configuration |
| **Deployment** | Windows zip, Linux tarball, Docker image |

## Works with

Any ONVIF-compatible camera, plus GB28181 devices. Verified with Hikvision, Dahua, Uniview, Axis, Tiandy and Ezviz hardware.

## Install

First visit always opens a setup wizard — set language, local addresses and the admin password there. Default web console: `http://<host>:16188`.

### Docker

```bash
docker run -d --name ccnvr --restart always \
  -p 16188:16188 \
  -p 15060:15060 -p 15060:15060/udp \
  -p 31100-31200:31100-31200 -p 31100-31200:31100-31200/udp \
  -p 3702:3702/udp \
  -v /opt/ccnvr/data:/opt/media/bin/configs \
  ccnvr/ccnvr:latest
```

Then open `http://<host-ip>:16188`.

- **You must mount `/opt/media/bin/configs`.** Config, database, device records, machine ID and the license file all live there. Without the mount they are lost when the container is recreated, and the license has to be reissued.
- **GB28181 needs UDP 15060.** Mapping only TCP makes devices report "registration timeout" forever with nothing in the server log.
- **ONVIF auto-discovery uses LAN multicast** and cannot see devices on a bridge network. Use `--network host` on Linux, then drop all `-p` flags.
- Add `-p 2554:2554 -p 1935:1935` only if you need RTSP / RTMP re-publish (both are off by default).

### Windows

Download `ccnvr-windows-amd64-<version>.zip` from [Releases](https://github.com/ccnvr/ccnvr/releases/latest), unzip anywhere, start it, then open `http://localhost:16188`.

### Linux

Download `ccnvr-linux-amd64-<version>.tar.gz`, then:

```bash
tar -xzf ccnvr-linux-amd64-<version>.tar.gz
cd ccnvr-linux-amd64-<version>
sudo ./start.sh
```

Requires glibc ≥ 2.31 (Ubuntu 20.04+, Debian 11+, CentOS Stream 9+). `sudo` is needed because RTSP defaults to port 554, a privileged port. To run unprivileged instead:

```bash
sudo setcap 'cap_net_bind_service=+ep' ./MediaServer/MediaServer
```

## Ports

| Purpose | Port | Protocol | Required |
| --- | --- | --- | --- |
| Web console + ONVIF SOAP | 16188 | TCP | Yes |
| GB28181 SIP signaling | 15060 | TCP + UDP | For GB28181 |
| GB28181 media | 31100-31200 | TCP + UDP | For GB28181 |
| ONVIF WS-Discovery | 3702 | UDP | Optional |
| RTSP distribution | 2554 | TCP | Optional |
| RTMP distribution | 1935 | TCP | Optional |

On a cloud server, open these in the provider's **security group** as well as the host firewall — the security group is the most commonly missed step. The media API on 16198 is internal only; do not expose it.

## Editions and licensing

Without a license CCNVR runs as the **free edition: 5 channels**. A license file is uploaded in **System info → License** and takes effect immediately, no restart. Channels beyond the licensed count can still be managed and deleted, but not previewed or played back.

Commercial and higher-channel licenses: see [ccnvr.com](https://ccnvr.com) or [contact us](https://ccnvr.com/docs/contact).

## FAQ

**Is CCNVR open source?**
No. CCNVR is proprietary software. The source code is not published and this repository contains no source. See [LICENSE](LICENSE).

**Is it free?**
The free edition runs 5 channels, for personal and non-commercial use. See [LICENSE](LICENSE) for the exact terms.

**Do I need a cloud account or an internet connection?**
No. Everything runs on your own machine; only LAN or VPN access to cameras is required.

**Do I need to install ffmpeg?**
No. A static ffmpeg is bundled in every package.

**Why is my GB28181 device stuck at "registration timeout"?**
UDP 15060 is almost always the cause — mapped only on TCP, or blocked by the cloud security group.

**Can I run it on a Raspberry Pi / ARM box?**
Server builds are published for Windows and Linux (x86_64). ARM64 is not a supported server target today — see the [Releases](https://github.com/ccnvr/ccnvr/releases/latest) page for the current artifact list.

## Support

- Bug reports and feature requests: [Issues](https://github.com/ccnvr/ccnvr/issues)
- Setup questions and configuration help: [Discussions](https://github.com/ccnvr/ccnvr/discussions) or [docs](https://ccnvr.com/docs/getting-started)
- Security issues: see [SECURITY.md](SECURITY.md) — please do not open a public issue

---

## 中文

**轻量级自托管网络录像机（NVR），支持 ONVIF / RTSP / RTMP / GB28181 接入。**

实时预览 · 录像回放 · 云台控制 · WebRTC / FLV 低延迟分发 · H.265 · Windows / Linux / Docker

[官网](https://ccnvr.com) · [文档](https://ccnvr.com/docs/getting-started) · [下载](https://github.com/ccnvr/ccnvr/releases/latest)

本仓库是 CCNVR 的**发布与支持渠道**，只存放安装包、更新日志和问题跟踪。CCNVR 为闭源商业软件，**不提供源代码**，授权条款见 [LICENSE](LICENSE)。

- 免费版默认 5 路，授权文件在「系统信息 → 授权」中导入，即时生效、无需重启
- 网页控制台端口 `16188`，首次访问进入安装向导，设置语言、本机地址和管理员密码
- Docker 部署必须挂载 `/opt/media/bin/configs`，否则重建容器后配置、设备记录与授权文件全部丢失
- GB28181 设备注册依赖 **UDP 15060**，只映射 TCP 会一直「注册超时」
- Linux 版自带静态 ffmpeg，系统只需 glibc ≥ 2.31（Ubuntu 20.04+ / Debian 11+ / CentOS Stream 9+）
- 云服务器记得同时放行**安全组**和主机防火墙

常见问题、端口表、Docker 参数说明见上方英文部分，或访问 [在线文档](https://ccnvr.com/docs/getting-started)。

## Links

| | |
| --- | --- |
| Website | https://ccnvr.com |
| Documentation | https://ccnvr.com/docs/getting-started |
| Downloads | https://ccnvr.com/down |
| Releases | https://github.com/ccnvr/ccnvr/releases |
| Contact | https://ccnvr.com/docs/contact |
