🇨🇳 [中文](README.md) | 🇺🇸 English | 🇷🇺 [Русский](README_RU.md) | 🇮🇷 [فارسی](README_FA.md)

> When I first started using BandwagonHost VPS, I stared at its entirely English interface for quite a while, completely lost. I had no idea where to begin, what to do after purchasing a server, or even what SSH was—I had to look it up on the spot. This guide is for anyone who feels as confused as I did back then. I'll walk you through this **BandwagonHost VPS tutorial** from start to finish, covering everything you need to know.<br>

## (Updated November 12, 2026)

## 1. What Is BandwagonHost, and How Has It Changed Over the Years?

BandwagonHost, commonly known as "Banwagong" (搬瓦工) among Chinese users, is operated by IT7 Networks, a Canadian company founded in 2004. The Chinese nickname "搬瓦工" comes from the similar pronunciation of "ban-wa-gong" and "BandwagonHost." This accidental resemblance eventually became a widely recognized name in the Chinese VPS community.

BandwagonHost has changed considerably over the years. Its early reputation was built on extremely affordable OpenVZ virtual servers, but those days are long gone. The company has transitioned its entire product lineup to KVM virtualization, and prices have risen from just a few dozen yuan per year to nearly RMB 300 annually for an entry-level VPS.

Its product lineup has also expanded significantly. Today, BandwagonHost offers everything from basic KVM servers and CN2 GIA-E optimized routes to premium Hong Kong and Tokyo connections, as well as enterprise-grade VPS plans with SLA guarantees. There are now options for nearly every budget.

One major change is worth mentioning: starting with the Singles' Day promotion in November 2025, BandwagonHost quietly discontinued almost all long-standing discount codes, including the widely used `BWHCGLUKKB`.

A new code, `NODESEEK2026`, briefly appeared in early 2026, offering a recurring 6.77% discount, but it stopped working within a couple of days.

As of this update, there are no regular discount codes available. If you want to save money, your best options are limited-edition plans or major promotional events.

---

## 2. Before You Begin This BandwagonHost VPS Tutorial: Understand What You're Buying

Many beginners jump straight to the SSH connection instructions when reading a BandwagonHost VPS tutorial, only to realize afterward that they purchased the wrong server plan.

Before getting into the technical steps, it is important to understand the different product lines.

BandwagonHost's regular VPS plans generally fall into the following categories:

**Basic VPS (Entry-Level Plans):**

These plans use KVM virtualization and allow users to switch between several Los Angeles data centers.

They are the most affordable options, suitable for learning Linux, hosting small websites with limited traffic, or practicing basic server administration.

The cheapest entry-level plan currently starts at **$49.99 per year**.

**E-Commerce VPS / CN2 GIA-E (Best Overall Value):**

This is one of BandwagonHost's most popular product lines.

It supports free data center switching through the control panel, with access to more than 12 locations, including:

- DC6 CN2 GIA-E
- DC9 CN2 GIA
- Osaka, Japan (SoftBank)
- Netherlands (AS9929)
- Vancouver, Canada

Prices start at **$49.99 quarterly** or **$169.99 annually**.

For most users who need fast and reliable connections from mainland China, CN2 GIA-E offers the best balance between price and performance.

**SLA VPS (Enterprise-Grade Reliability):**

These servers are based in the Los Angeles DC5 data center and feature dedicated AMD CPU resources, ECC memory, and NVMe RAID-10 SSD storage.

The service includes a **99.99% SLA guarantee** and allows one free IP address replacement every two weeks.

This product line is suitable for high-availability commercial applications.

**Ultra VPS (Premium Low-Latency Plans):**

The Ultra series includes premium CN2 GIA servers in Hong Kong and Tokyo.

Latency can be as low as **30–60 ms**, with bandwidth of up to **1 Gbps**.

Prices start at **$89.99 per month**, making these some of the most expensive plans in BandwagonHost's product lineup.

Once you understand these product categories, you're ready to move on to the practical steps.

👉 [View All Currently Available BandwagonHost VPS Plans](https://to.iix.im/bwg)

---

## 3. BandwagonHost VPS Tutorial – Step 1: Purchase and Account Registration

The official BandwagonHost website is entirely in English, but the purchasing process is relatively straightforward if you follow the steps carefully.

**Important things to remember when registering an account:**

First, disable your proxy or VPN software before registering. Otherwise, the system may flag your order as potentially fraudulent and cancel it automatically.

Make sure you enter a valid email address, because important VPS information will be sent to your inbox.

Your country information should be accurate. Your personal address does not necessarily need to be extremely detailed, but it should be reasonable and consistent with your actual circumstances.

When selecting a plan, you will be asked to choose a billing cycle and data center location.

The default data center assigned to a CN2 GIA-E plan is not necessarily the best option for your connection. Fortunately, you can migrate to a more suitable data center for free through the control panel after purchasing.

Therefore, there's no need to spend too much time deciding on a data center during checkout.

**Payment Methods:**

BandwagonHost supports Alipay, making payment convenient for users in mainland China.

You do not need to rely on a third-party reseller or obtain an international credit card just to complete your purchase.

---

## 4. BandwagonHost VPS Tutorial – Step 2: Log In and Obtain SSH Credentials

After purchasing your VPS, BandwagonHost will send you a confirmation email containing information about accessing your server.

Log in to your account and navigate to:

`Services → My Services`

Find the VPS you purchased and click **KiwiVM Control Panel** to access BandwagonHost's proprietary server management interface.

KiwiVM is one of BandwagonHost's distinguishing features. It offers a comprehensive range of management functions, including:

- Starting, stopping, and restarting your VPS
- Reinstalling the operating system
- Configuring reverse DNS (rDNS)
- Creating snapshots
- Monitoring traffic usage
- Migrating between data centers
- Accessing API functions

Most routine server management tasks can be completed directly through KiwiVM without installing a third-party control panel.

### How to Find Your SSH Login Information

On the main KiwiVM page, you can find:

- `IP Address`
- `SSH Port`

**Important:** BandwagonHost generally assigns a random SSH port instead of using the default port `22`.

Make sure you use the correct SSH port when connecting.

### How to Reset the Root Password

If you need to obtain or reset your root password:

1. Open the KiwiVM control panel.
2. Find `Root password modification` in the left-hand menu.
3. Shut down your VPS.
4. Click the option to generate a new root password.
5. Copy and securely save the generated password immediately.

The new password is displayed only once, so make sure you save it before leaving the page.

### Recommended SSH Clients

**For Windows:**

I recommend **Termius** because it has a user-friendly interface and supports configuration synchronization across multiple platforms.

Compared with traditional tools such as Xshell, Termius offers a more modern experience.

Of course, you can also use:

- Xshell
- PuTTY
- Git Bash
- PowerShell

Choose whichever tool you are most comfortable with.

**For macOS:**

You can use the built-in Terminal application.

The SSH command follows this format:

```bash
ssh root@YOUR_SERVER_IP -p YOUR_SSH_PORT
```

For example:

```bash
ssh root@172.80.80.20 -p 27565
```

### What If SSH Doesn't Connect?

If you cannot connect to your server locally, or if your VPS IP address has been blocked, you can use the following KiwiVM feature:

`Root shell - interactive`

This function allows you to access your VPS through a browser-based VNC console.

It is particularly useful for emergency troubleshooting when a normal SSH connection is unavailable.

---

## 5. BandwagonHost VPS Tutorial – Step 3: Initial System Setup and Application Deployment

After successfully connecting through SSH, you will see a Linux command-line interface.

What you do next depends on how you intend to use your VPS.

### If You Want to Host a Website (WordPress / LNMP)

For beginners unfamiliar with Linux, I recommend installing the **BT Panel (BaoTa Panel)** first.

It simplifies server environment deployment and provides a graphical interface for managing:

- Nginx
- Apache
- MySQL
- PHP

With a web hosting control panel, many website deployment tasks can be completed with just a few clicks.

The **LNMP one-click installation package** is another established option.

It is command-line based, more lightweight, and generally consumes fewer system resources.

### If You Want to Deploy Docker Applications (Dify, n8n, OpenClaw, etc.)

Before installing Docker-based applications, check whether your VPS has sufficient RAM.

As a general guideline:

- **Dify:** At least 2 GB RAM is recommended.
- **n8n:** Basic deployments can run with approximately 1 GB RAM.
- **OpenClaw:** May require more memory, depending on the deployment configuration.

The entry-level CN2 GIA-E plan offers only 512 MB RAM in some configurations, which may be insufficient for running these AI-related applications.

For such workloads, consider choosing a VPS with more memory.

### If You Just Want to Learn Linux

The cheapest KVM entry-level VPS should be enough.

You can experiment with commands, install packages, configure services, and practice system administration.

If something goes wrong, you can simply reinstall the operating system through KiwiVM and restore a clean environment within a few minutes.

### Recommended Operating Systems

BandwagonHost provides several Linux distributions, including:

- Debian
- Ubuntu
- CentOS

**CentOS 7 has reached end of life and no longer receives official maintenance updates.**

For most users, I recommend Debian 11/12 or Ubuntu 22.04 LTS because of their stability and extensive community documentation.

---

## 6. BandwagonHost VPS Tutorial – Step 4: Data Center Migration and Network Optimization

If you purchase a CN2 GIA-E VPS, switching between data centers is an important feature that you may use regularly.

In the KiwiVM control panel, locate:

`Migrate to different datacenter`

Then follow these steps:

1. Open the data center migration page.
2. Select your preferred destination data center.
3. Confirm the migration request.
4. Allow the system to complete the migration.

The process usually takes only a few minutes.

BandwagonHost migrates only the disk sectors that are actually in use, helping improve migration speed while preserving server data.

### Which Data Center Should You Choose?

Here is a simple guideline based on your internet service provider:

**China Telecom Users:**

- DC6 CN2 GIA-E
- DC9 CN2 GIA

These routes generally provide strong performance for China Telecom connections.

**China Unicom Users:**

- Netherlands EUNL_9 (AS9929)
- Osaka, Japan (SoftBank)

These locations often provide favorable routing and latency for China Unicom users.

**China Mobile Users:**

- Osaka JPOS_1 (SoftBank)
- Tokyo CMI routes

These options can provide smoother connectivity for China Mobile users.

If you're not sure which location is best, check the current data center's ping latency in KiwiVM.

You can also test the official IP addresses provided by BandwagonHost for each data center before deciding where to migrate.

---

## 7. Complete BandwagonHost VPS Plan Comparison

The following table compares the main regular BandwagonHost VPS plans available at the time of this update.

It should help you select the most suitable plan before following the practical steps in this tutorial.

| Plan Series | Minimum Configuration | Monthly Traffic | Bandwidth | Data Centers | Network Features | Starting Price | Purchase Link |
|---|---|---|---|---|---|---|---|
| Basic VPS (KVM) | 1 vCPU / 1 GB RAM / 20 GB SSD | 1 TB | 1 Gbps | 9 (including CN2 GT) | Standard international routes + selected CN2 GT | $49.99/year | [Buy Now](https://to.iix.im/bwg) |
| Basic VPS (KVM High Traffic) | 1 vCPU / 1 GB RAM / 20 GB SSD | 2 TB | 1 Gbps | 9 | Standard international routes + selected CN2 GT | $52.99/6 months or $99.99/year | [Buy Now](https://to.iix.im/bwg) |
| E-Commerce VPS (CN2 GIA-E) – Low Traffic | 2 vCPU / 1 GB RAM / 20 GB SSD | 1 TB | 2.5 Gbps | 12+ (including DC6/DC9 and Japan SoftBank) | CN2 GIA for all three major Chinese ISPs + SoftBank + AS9929 | $49.99/quarter or $169.99/year | [Buy Now](https://bwh81.net/aff.php?aff=80238&pid=87) |
| E-Commerce VPS (CN2 GIA-E) – High Traffic | 2 vCPU / 2 GB RAM / 40 GB SSD | 2 TB | 2.5 Gbps | 12+ | CN2 GIA for all three major Chinese ISPs + SoftBank + AS9929 | $89.99/quarter or $299.99/year | [Buy Now](https://to.iix.im/bwg) |
| SLA VPS (Enterprise) | 2 AMD vCPU / 1 GB ECC RAM / 20 GB NVMe | 1 TB | 2.5 Gbps | Los Angeles DC5 + migration to multiple data centers | CN2 GIA + CMIN2 for major Chinese ISPs; 99.99% SLA | From $27.99/month | [Buy Now](https://to.iix.im/bwg) |
| Hong Kong CN2 GIA (Ultra) | 2 vCPU / 1 GB RAM / 20 GB SSD | 500 GB | 1 Gbps | Hong Kong HKHK_8 | CN2 GIA for all three major Chinese ISPs; 30–60 ms latency | $89.99/month or $899.99/year | [Buy Now](https://to.iix.im/bwg) |
| Hong Kong CN2 GIA High Traffic (Ultra) | 2 vCPU / 2 GB RAM / 40 GB SSD | 1 TB | 1 Gbps | Hong Kong HKHK_8 | CN2 GIA for all three major Chinese ISPs; 30–60 ms latency | $155.99/month or $1559.99/year | [Buy Now](https://to.iix.im/bwg) |
| Osaka, Japan CN2 GIA | 2 vCPU / 1 GB RAM / 20 GB SSD | 500 GB | 1.2 Gbps | Mainly Osaka JPOS_6 | China Telecom CN2 GIA in both directions; CN2 GIA return routes for all three major Chinese ISPs | See current official pricing | [Buy Now](https://to.iix.im/bwg) |
| Tokyo, Japan CN2 GIA | 2 vCPU / 1 GB RAM / 20 GB SSD | 500 GB | 1.2 Gbps | Tokyo JPTYO_8 | CN2 GIA return routes for all three major Chinese ISPs | See current official pricing | [Buy Now](https://to.iix.im/bwg) |

> **Note:** Stock availability for certain BandwagonHost plans fluctuates significantly, especially limited-edition products such as THE PLAN, MINICHICKEN, MegaBox Pro, and Tokyo Plan. These plans may sell out quickly when restocked. All prices are subject to the amounts displayed on the official website at the time of purchase.

---

## 8. Latest BandwagonHost VPS Updates: What Changed Between Late 2025 and 2026?

BandwagonHost introduced several noteworthy changes during this period.

### Network and Data Center Expansion

In April 2025, BandwagonHost launched the New York CN2 GIA data center (`USNY_8`), supporting premium routes such as CN2 GIA, CMIN2, and CUP for China's three major internet service providers.

In early 2026, the company added a new Amsterdam data center in the Netherlands (`EUNL_1`).

It provides premium network access through AS10099, CMIN2, and CN2 GIA.

However, during the restricted sales period, this data center was available only for newly purchased plans. Existing VPS plans were temporarily ineligible for migration to this location.

### Limited-Edition Plan Updates

In September 2025, the MINICHICKEN plan was restocked at **$19 per year**, using the Fremont data center.

During the same month, **Tokyo Plan v2** was launched at **$99 per year**, offering:

- 2 vCPU
- 2 GB RAM
- 40 GB storage
- Tokyo DC39v2 data center
- CMI return routes for China's three major ISPs

This plan offered particularly attractive value for users seeking Japanese servers.

The **MegaBox Pro** plan was also restocked several times during 2025.

Its configuration included:

- 2 vCPU
- 2 GB RAM
- 40 GB storage
- CN2 GIA + CMIN2 network routes
- $49 per year

### Discount Code Updates

After the Singles' Day promotion ended in November 2025, BandwagonHost discontinued its regular promotional codes.

In February 2026, `NODESEEK2026` briefly offered a recurring **6.77% discount**, but it became invalid shortly afterward.

There are currently no regular discount codes available. Users seeking lower prices should monitor major promotional events and limited-edition VPS releases.

### KiwiVM Control Panel Improvements

BandwagonHost added support for **Passkeys** and **Security Keys** to KiwiVM, improving account security.

The data center migration mechanism was also optimized.

Instead of migrating the entire virtual disk, the system now transfers only occupied disk sectors, improving migration speed and reliability.

---

## 9. BandwagonHost VPS Frequently Asked Questions

### Q: My BandwagonHost SSH port isn't 22. Where can I find the correct port?

Open the KiwiVM control panel and go to the main page.

Under `Main Controls`, look below `IP Address` to find `SSH Port`.

Each VPS is assigned a randomly generated SSH port.

### Q: What should I do if my VPS IP address gets blocked?

You can request a paid IP address replacement through KiwiVM.

The replacement fee is **$8 per request**.

If you have an SLA VPS plan, you can change your IP address for free once every two weeks.

If you cannot connect to your server, try using KiwiVM's browser-based VNC console:

`Root shell - interactive`

This allows you to access your VPS for emergency troubleshooting.

### Q: Will my data remain after reinstalling the operating system?

No. Reinstalling the operating system will erase the existing data.

Before reinstalling, it is recommended to create a snapshot or backup through KiwiVM.

BandwagonHost provides free automatic backups, with a snapshot created approximately once every six days.

You can view available backups in the `Backups` section.

### Q: Which BandwagonHost VPS plan is the safest choice for beginners?

If you're unsure which plan to purchase, I recommend starting with **CN2 GIA-E**.

The entry-level plan starts at **$49.99 per quarter** and offers access to more than 12 data centers.

It provides flexibility for website hosting, application deployment, and everyday server usage.

If you choose the wrong data center, you can simply migrate to another supported location.

👉 [View BandwagonHost CN2 GIA-E VPS Plans](https://to.iix.im/bwg)

---

## 10. Conclusion

If I had to summarize this BandwagonHost VPS tutorial in one sentence, it would be:

**Choose the right VPS plan, establish your SSH connection, and everything else becomes easier with practice.**

The entry-level KVM 20 GB plan is suitable for learning Linux and experimenting with server management.

CN2 GIA-E is the most practical choice for most users.

The Hong Kong and Tokyo Ultra plans are intended for people who need exceptionally low latency.

SLA VPS plans are better suited to commercial applications with strict reliability requirements.

Over the years, BandwagonHost has moved away from its original low-cost positioning toward the mid-range and premium VPS markets.

Although regular discount codes are no longer available, the company has continued expanding its product lineup and data center coverage.

For users in mainland China who need stable, fast VPS connections with the flexibility to switch data centers, BandwagonHost remains an option worth considering.

👉 [Visit the Official BandwagonHost VPS Purchase Page](https://to.iix.im/bwg)
