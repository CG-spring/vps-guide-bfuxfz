# VPS Buying & Maintenance — Complete Guide

> 📚 This repository provides a zero-to-expert VPS buying guide, in-depth performance benchmarking scripts, one-click deployment tools, and security hardening walkthroughs. Includes head-to-head comparisons of BandwagonHOST, CloudCone, Tencent Cloud, and other major providers — helping you find the best cost-performance VPS for a stable, unrestricted internet experience.
>
> **Keywords**: VPS buying guide, BandwagonHOST CN2 GIA, CloudCone hourly billing, Tencent Cloud Lighthouse, BBR scripts, mihomo setup, VPS benchmark, proxy server, overseas VPS ranking

---

## Table of Contents

- [VPS Buying Essentials](#-vps-buying-essentials)
- [Provider Head-to-Head Comparison](#-provider-head-to-head-comparison)
- [One-Click Script Toolbox](#-one-click-script-toolbox)
- [VPS Security Hardening](#-vps-security-hardening)
- [FAQ](#-faq)
- [Related Resources](#-related-resources)

---

## 🔍 VPS Buying Essentials

### 5 Dimensions That Actually Matter

99% of beginners focus only on price. These five dimensions actually determine your experience:

| Dimension | Weight | What It Means |
|-----------|--------|----------------|
| **Line Quality** | 35% | CN2 GIA > CN2 GT > 163 Backbone > Standard BGP |
| **Geographic Location** | 25% | Hong Kong > Japan > Los Angeles > Others |
| **Bandwidth / Traffic** | 15% | Prefer larger bandwidth; monthly-reset traffic > one-time packages |
| **Control Panel** | 15% | Chinese-provider panels are more user-friendly; Alipay support a plus |
| **Support Quality** | 10% | Ticket response time, Chinese-language support |

### What Is CN2 GIA?

CN2 GIA (China Telecom Next Carrier Network – Global Internet Access) is China's highest-tier international exit routing. Compared to standard 163 backbone:

- **Lower latency**: Shanghai → Los Angeles via CN2 GIA ≈ 150–180 ms; standard route ≈ 200–230 ms
- **Less jitter**: Smoother gaming and voice experience
- **Independent exit**: Not affected by peak-hour domestic export congestion
- **Higher cost**: CN2 GIA is typically 2–3× the price of standard routes for the same specs

**How to identify**: Use `traceroute` or `mtr` — CN2 GIA routes pass through the 59.43.x.x IP segment.

### Storage: SSD vs. HDD

| Type | Read/Write Speed | Best For | Price |
|------|----------------|----------|-------|
| **NVMe SSD** | 3000+ MB/s | High IOPS, proxy use | Slightly higher |
| **SATA SSD** | ~500 MB/s | General use — fully sufficient | Medium |
| **HDD** | 80–160 MB/s | Storage/backup only | Cheap |

**Bottom line**: SATA SSD is fine for proxy use; go NVMe if budget allows.

### Traffic vs. Bandwidth — Know the Difference

- **Traffic (allowance)**: Total monthly data limit, e.g., 1 TB/month. Exceeding means throttling or extra charges.
- **Bandwidth**: Instantaneous data transfer speed, e.g., 1 Gbps (peak rate, not sustained).

**Buying tips**:
- Video users → Prioritize high-traffic plans (e.g., 2 TB/month)
- Light users → 500 GB–1 TB is sufficient
- Watch out for "throttled to 1 Mbps after exceeding limit" clauses — avoid these!

---

## ⚖️ Provider Head-to-Head Comparison

### Tier 1: CN2 GIA Dedicated Lines (Maximum Stability)

#### 1. BandwagonHOST

```
Official site: https://vpsvip.net (Chinese proxy)
Panel: KiwiVM / ZenLayer
Payment: Alipay / WeChat Pay / Credit Card
Support: Ticket response 2–12 hours
```

**Recommended Plans**:
- **$49.99/year**: CN2 GIA Limited, 1 vCPU / 1 GB RAM / 20 GB NVMe / 1 Gbps / 1 TB
- **$89.99/year**: CN2 GIA Regular, 2 vCPU / 2 GB RAM / 40 GB NVMe / 1 Gbps / 2 TB
- **$169.99/year**: Dual-path CN2 GIA, 4 vCPU / 4 GB RAM / 80 GB NVMe / 2 Gbps / 3 TB

**Pros**: Best-in-class line quality, minimal overselling, solid ticket system, Alipay support
**Cons**: Frequent stockouts, premium pricing

**Real-world results (Shanghai Telecom, Q1 2026)**:
```
wget speed test: 280–310 Mbps (no degradation during peak hours)
Netflix unlock: ✅ All regions
YouTube 4K: ✅ Smooth
Latency: 160–180 ms
```

#### 2. Tencent Cloud Lighthouse

```
Official site: https://cloud.tencent.com (or via nav.clashvip.net referral)
Panel: Tencent Cloud Console (Chinese)
Payment: WeChat Pay / Alipay / Bank Card
Support: 24/7 online chat
```

**Recommended Plans**:
- **Hong Kong node**: 2 vCPU / 4 GB RAM / 200 GB SSD / 30 Mbps / 2000 GB ≈ ¥68/month
- **Singapore node**: 2 vCPU / 2 GB RAM / 50 GB SSD / 30 Mbps / 1500 GB ≈ ¥50/month

**Pros**: Fast access from mainland China, Alipay/WeChat Pay direct, Chinese-language support
**Cons**: 30 Mbps bandwidth is limiting for heavy multi-user scenarios; requires real-name registration

### Tier 2: Best Value Picks

#### 3. CloudCone (Hourly Billing)

```
Official site: https://cloudcone.com
Panel: CloudCone Dashboard (English)
Payment: Credit Card / PayPal
Support: Ticket-based
```

**Recommended Plans**:
- **SC2 plan**: $3.88/month — 1 vCPU / 1 GB RAM / 20 GB SSD / 1 Gbps / 2 TB
- **SC3 plan**: $5.88/month — 2 vCPU / 2 GB RAM / 40 GB SSD / 1 Gbps / 3 TB
- **Backup storage**: $0.007/GB/hour — ideal for temporary needs

**Pros**: Hourly billing, destroy anytime; IPv6 support; automatic backups
**Cons**: Non-CN2 routes; no Chinese support; Los Angeles datacenter underperforms for Telecom users

**Real-world results (Guangdong Telecom)**:
```
wget speed test: 200–250 Mbps (≈180 Mbps during peak hours)
Latency: 190–220 ms
Streaming: Netflix ✅ YouTube ✅
```

#### 4. RackNerd (Rock-Solid Budget Option)

```
Official site: https://www.racknerd.com
Panel: SolusVM
Payment: PayPal / Credit Card
```

**Recommended Plans**:
- **$16.88/year**: 1 vCPU / 1.5 GB RAM / 11 GB NVMe / 3 TB / 1 Gbps
- **$27.88/year**: 2 vCPU / 3 GB RAM / 22 GB NVMe / 6 TB / 1 Gbps

**Pros**: Exceptional price-to-performance ratio, reliable stability, generous traffic
**Cons**: No CN2 routing; return path may use 163 backbone; higher latency for Asia-Pacific users

---

## 🛠️ One-Click Script Toolbox

All scripts are tested on Ubuntu 18.04+ / Debian 11+ / CentOS 7+.

### 1. VPS Benchmark Performance Test

```bash
wget -qO- https://raw.githubusercontent.com/CG-spring/vps-guide-bfuxfz/main/bench.sh | bash
```

**What it tests**:
- 🖥️ CPU model, core count, clock speed
- 💾 Total RAM and available disk space
- 💿 Disk I/O read/write speeds
- 🌐 Multi-node bandwidth tests (Cachefly / Linode / OVH)
- 📺 Streaming unlock detection (Netflix / YouTube)
- 📡 Latency tracing (mtr)

### 2. BBR Acceleration — One-Click

```bash
wget -qO- https://raw.githubusercontent.com/CG-spring/vps-guide-bfuxfz/main/bbr.sh | bash
```

Auto-detects and enables:
- BBR (Bottleneck Bandwidth and RTT)
- BBRv2 (Enhanced)
- BBR+CAKE
- LotServer (锐速)
- Tuned BBR variants

**Expected result**: Single-connection bandwidth boost of 2–5×, latency reduction of 20–40%.

### 3. mihomo (Clash Meta) — One-Click Install

```bash
wget -qO- https://raw.githubusercontent.com/CG-spring/vps-guide-bfuxfz/main/clash.sh | bash
```

Automatically: downloads and installs mihomo v1.18.0 → generates config.yaml → configures Systemd service → opens firewall ports → outputs management panel URL.

**Management panel**: `http://<your-VPS-IP>:9090/ui`

### 4. Docker + Docker Compose Install

```bash
wget -qO- https://raw.githubusercontent.com/CG-spring/vps-guide-bfuxfz/main/docker.sh | bash
```

Includes: Docker CE + Docker Compose v2 + Portainer web management panel

---

## 🔒 VPS Security Hardening

### Must-Do Security Checklist (New Users: Read First!)

#### 1. Change the Default SSH Port

```bash
sudo vim /etc/ssh/sshd_config
# Find "Port 22" and change it to:
Port 2222
sudo systemctl restart sshd
```

#### 2. Switch to Key-Based Auth, Disable Password Login

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
ssh-copy-id -p 2222 -i ~/.ssh/id_ed25519.pub root@<your-VPS-IP>

sudo vim /etc/ssh/sshd_config
# Change to:
PasswordAuthentication no
PubkeyAuthentication yes
sudo systemctl restart sshd
```

#### 3. Configure UFW Firewall

```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw allow 2222/tcp   # SSH
sudo ufw allow 80/tcp     # HTTP
sudo ufw allow 443/tcp   # HTTPS
sudo ufw allow 9090/tcp   # mihomo panel
sudo ufw enable
```

#### 4. Install Fail2Ban Against Brute-Force Attacks

```bash
sudo apt install fail2ban -y
sudo systemctl enable fail2ban
sudo systemctl start fail2ban
```

---

## ❓ FAQ

### Q1: Which provider is best for internet freedom?

**There is no single answer** — it depends on your location and ISP:

| ISP | Recommended | Reason |
|-----|-------------|--------|
| **China Telecom** | BandwagonHOST CN2 GIA / Tencent Cloud HK | Best Telecom→CN2 GIA performance |
| **China Unicom** | Tencent Cloud HK / BandwagonHOST | Unicom international exit quality is strong |
| **China Mobile** | Tencent Cloud SG / RackNerd | Mobile international exit is generally decent |

### Q2: Annual vs. Monthly — Which is better?

- **Annual**: Usually 20–40% cheaper; suitable for established, proven providers
- **Monthly**: More flexibility; you can switch anytime — but more expensive

**Tip**: Test a new provider for 1–2 weeks on a monthly plan before committing to annual.

### Q3: How do I test VPS line quality?

```bash
curl -sL https://raw.githubusercontent.com/CG-spring/vps-guide-bfuxfz/main/bench.sh | bash
```

### Q4: My VPS got blocked — what now?

1. **Diagnose first**: Did you violate the provider's ToS (e.g., encryption proxies)?
2. **Swap IP**: Most providers charge $1–5 for an IP change
3. **Try a different port**: Some providers block 25/53 and similar ports
4. **Contact support**: Explain the situation and request assistance

### Q5: NAT VPS vs. Dedicated Server — What's the difference?

| Type | Public IP | Ports | Price | Best For |
|------|-----------|-------|-------|----------|
| **Dedicated** | Independent public IP | Full port access | Higher | Web hosting / proxy / services |
| **NAT VPS** | Shared / port-mapped | Limited port count | Lower | Proxy-only use case |

**Conclusion**: For proxy use only, NAT VPS offers far better value.

---

## 📚 Related Resources

| Resource | Link |
|----------|------|
| 🏠 ClashHub Rulesets | [https://clashhub.net](https://clashhub.net) |
| 📥 Clash for Windows Download | [https://clash-for-windows.net](https://clash-for-windows.net) |
| 🧭 VPS Recommendation Hub | [https://nav.clashvip.net](https://nav.clashvip.net) |
| 🛒 VPS Top Picks | [https://vpsvip.net](https://vpsvip.net) |
| 💬 ClashHub Forum | [https://bbs.clashhub.net](https://bbs.clashhub.net) |

---

## 📋 Quick Command Reference

```bash
# Performance benchmark
wget -qO- https://raw.githubusercontent.com/CG-spring/vps-guide-bfuxfz/main/bench.sh | bash

# BBR acceleration
wget -qO- https://raw.githubusercontent.com/CG-spring/vps-guide-bfuxfz/main/bbr.sh | bash

# mihomo installation
wget -qO- https://raw.githubusercontent.com/CG-spring/vps-guide-bfuxfz/main/clash.sh | bash

# Docker environment
wget -qO- https://raw.githubusercontent.com/CG-spring/vps-guide-bfuxfz/main/docker.sh | bash
```

---

> ⚡ **Pro Tip**: Before running any script, use `screen` or `tmux` to create a session — this prevents installation interruption if your SSH connection drops.
>
> ```bash
> sudo apt install screen -y
> screen -S vps-setup
> # To reattach after disconnect:
> screen -r vps-setup
> ```

---

*Maintained by [ClashHub](https://clashhub.net) · Last updated: 2026-04-17*
*If you found this useful, please ⭐ Star — share it with others who need it!*
