---
title: "Week 3 Worklog"
date: 2026-09-28
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Week 3 Objectives:

* Deploy a WordPress/WooCommerce website on Amazon Lightsail and attach a custom domain.
* Install an SSL certificate (certbot) with automatic renewal and HTTP to HTTPS redirection.
* Set up automatic backups (Auto Snapshot) and move DNS management to Amazon Route 53.
* Optimize WordPress media storage using S3 and CloudFront.
* Learn to draw AWS architecture diagrams on draw.io.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2   | - Lightsail:<br>&emsp;+ Create instance with Wordpress blueprint<br>&emsp;+ Attach static IP (fixed static IP)<br>&emsp;+ Log in wordPress Admin: connect using SSH, take username and password, http://[fixed static IP]/wp-admin<br>&emsp; + Select and edit website template: plugin woocommerce, theme - Astra, Plugin Starter Templates - E-Commerce, move coming soon -> live, set Payments<br>&emsp; + Buy domain name (NameCheap) and record DNS (Account - Domain List - Advanced DNS): A record - @ - Your static IP - Automatic, A record - www - Your static IP - Automatic<br>&emsp;                                                                                           | 28/09/2026 | 28/09/2026      | <https://000045.awsstudygroup.com/2-wp-instance/2.1-deploy-instance/> |
| 3   | - Generating SSL certificate with bncert-tool failed:<br>&emsp;+ In the new WordPress version, Bitnami completely removed the old Monolithic architecture.<br>&emsp;+ Files properties.ini and ctlscript.sh have been fully removed. When entering /opt/bitnami, bncert-tool fails to scan these files and throws an error.<br>- Generate SSL certificate using certbot.<br>- Configure SSL certificate auto-renewal for certbot.<br>- Configure automatic HTTP to HTTPS redirection for certbot.                                             | 29/09/2026   | 29/09/2026      | <https://000004.awsstudygroup.com/4-launchlinuxinstance/> |
| 4   | - Set up Auto Snapshot (automatic backup) on AWS Lightsail<br>- Move DNS management from Namecheap to AWS Route 53:<br>&emsp;+ Create a Hosted Zone on AWS Route 53<br>&emsp;+ Copy the 4 Name Server (NS) addresses from Route 53<br>&emsp;+ Create DNS records on Route 53<br>&emsp;+ Update the Name Servers (NS) on Namecheap<br>&emsp;+ Verify the DNS has switched to Route 53 using dnschecker.org| 30/09/2026   | 30/09/2026      | <https://000010.awsstudygroup.com/1-introduce/> |
| 5   | - Optimize Lightsail storage using AWS S3 & CloudFront:<br>&emsp;+ Create an S3 bucket.<br>&emsp;+ Create an IAM policy and user to grant the necessary permissions to WordPress.<br>&emsp;+ Create an AWS CloudFront distribution (CDN) in front of S3 to accelerate image delivery.<br>&emsp;+ Configure the WP Offload Media plugin on WordPress to automatically offload media from WordPress to S3.<br>&emsp;                          | 1/10/2026 | 1/10/2026      | <https://cloudjourney.awsstudygroup.com/> |
| 6   | - Learn and practice drawing AWS architectures on draw.io.                                                                                      | 2/10/2026 | 2/10/2026      | <https://youtu.be/l8isyDe-GwY?si=uqHosMXFWOeqSFcq> |


### Week 3 Achievements:

* Created a Lightsail instance with the WordPress blueprint, attached a static IP, logged in to WordPress Admin, and built an e-commerce website with WooCommerce, the Astra theme, and Starter Templates.
* Bought a domain on Namecheap and pointed its DNS (A records) to the static IP.
* Worked around the bncert-tool failure caused by Bitnami dropping the Monolithic architecture by using certbot for SSL, with auto-renewal and HTTP to HTTPS redirection.
* Set up Auto Snapshot on Lightsail and moved DNS from Namecheap to Route 53 (Hosted Zone, Name Servers, DNS records), verified with dnschecker.org.
* Created an S3 bucket, IAM policy/user, and CloudFront distribution, and configured the WP Offload Media plugin to offload media to S3 automatically.
* Learned and practiced drawing AWS architecture diagrams on draw.io.
