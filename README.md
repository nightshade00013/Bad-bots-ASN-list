# 🛡️ Bad Bots & ASN Blocklist with Advanced IP Blocker Honeypot for WordPress

This is a fork from https://github.com/ycomiti/Bad-bots-ASN-list that has been expanded to be used with the tool **[Advanced IP Blocker](https://wordpress.org/plugins/advanced-ip-blocker/)** All credits for the original ASN list go to ycomiti.  All credits for the advanced IP Blocker go to it's developers.

A comprehensive, curated list of Autonomous System Numbers (ASNs) and malicious directory paths used by automated botnets, AI scrapers, and vulnerability scanners.

This repository is maintained to protect the digital assets of **MuttMutt Outdoors** and the **DogHouse Diving Foundation**. Our mission is to provide SCUBA diving therapy for young survivors of childhood abuse; keeping our servers secure ensures our resources go toward helping kids, not fighting bots.  There is a lot of work being done on it currently so check back for more updates in the coming weeks.

---

## 🚀 Implementation Tools

To make this list actionable, we recommend the following tools for WordPress and Cloudflare:

### 1. WordPress: Advanced IP Blocker
For WordPress-hosted sites, we recommend using the **[Advanced IP Blocker](https://wordpress.org/plugins/advanced-ip-blocker/)** plugin.
* **Why:** It allows for deep integration with Cloudflare and handles ASN blocking natively.
* **After installation** be sure to go through the steps to allow Advanced IP Blocker to integrate with CloudFlare, this will allow your website to **push** IP blocks and prevent access directly at the CloudFlare level and prevent the IP from accessing any information on your server AT ALL.  This will greatly relieve the pressure on your website and/or webhosting or server resources.

### 2. Cloudflare: Copy-Paste Firewall Rules
We have provided two specialized files for Cloudflare users to implement these blocks at the Edge (before they reach your server):
* **`Part 1 ASN list Expressions.txt`**: The first segment of the ASN blocklist formatted for the Cloudflare WAF.
* **`Part 2 ASN list Expressions.txt`**: The second segment (ensures you stay within Cloudflare's rule character limits).
* **How to use:** Copy the contents and paste them into a "Custom Rule" under **Security > Security Rules** in your Cloudflare dashboard.  You will need to create **two** rules to stay under the CloudFlare character limits. It is recommended to use the action of **Managed Challenge** which presents an interactive or non-interactive challenge to the client.

### 3. The Honeypot List
Located in `Wordpress Advanced IP Blocker Honeypot.txt`, this list contains paths that **no legitimate user or crawler should ever touch** (e.g., `/.env`, `/wp-config.php.bak`).
* **Warning:** If an IP hits any of these paths, it is 100% a malicious probe. 
* **Integration:** Use these paths within the Advanced IP Blocker "Honeypot" features to auto-ban offenders.
* **How to use:** Navigate to to the Advanced IP Blocker Honeypot section located at /wp-admin/admin.php?page=advaipbl_settings_page&tab=rules&sub-tab=honeypot



### If this feels overwhelming for you read this section.
I understand how it can feel reading all of this I will (hopefully) be completed with a page with much more instructions for those who need them here https://www.muttmutt.us/the-titan-shield-security-project/
It also incorporates some other things that I call the Titan Shield Security Project.  
It is a set of 4 plugins that offload most of the traffic to your webserver and allows you to leverage the CloudFlare resources for free while protecting your site from many malicious actors.

** I have put in a few weeks worth of time on compiling and sorting the information in this project as well as incorporating them into my websites.**
** I am also a survivor of childhood mental, physical, and sexual abuse.**
** I often get overwhelmed and right now I am nearly at my breaking point so please give me some time to work on the step by step pages.**



---

## ⚠️ Disclaimer & Safety

**Use at your own risk.** While this list is optimized to avoid blocking legitimate traffic (like Googlebot or SSL renewals), every server environment is different.
1. **Whitelist your own IP** and your hosting provider's ASN or IP addresses before applying.
2. **Monitor Logs:** Check for "False Positives" during the first 48 hours of implementation.
3. **Big 3 Caution:** Blocks for AWS (AS16509), Google (AS15169), and Azure (AS8075) are included but should be used with caution as they may host legitimate services you use.

---

## 🌊 About the Mission
The security of this repository supports the **[DogHouse Diving Foundation](https://www.doghousediving.org)**. We use our platforms to fund SCUBA diving certifications and trips for teens and young adults who have survived mental, physical, or sexual abuse. It is being shared with others to help them in their projects and show that the foundation is truly about giving to others.  We Support and use Open Source Software and do our best to support the commuunity. 

**Learn more at [muttmutt.us](https://www.muttmutt.us) or visit our [YouTube Channel](https://youtube.com/@MuttMuttOutdoors).**

If you would like to thanks us for the work we have done and help support us simply subscribe to the channel, watch some content, and consider heading over to [this page](https://www.muttmutt.us/your-welcome-here-is-how-you-can-say-thank-you/) for other information 

---
*Contributions welcome via Pull Request.*
