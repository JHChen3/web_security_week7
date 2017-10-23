# Project 7 - WordPress Pentesting

Time spent: **X** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. WordPress 3.3-4.7.4 - Large File Upload Error XSS (CVE-ID: CVE-2017-9061)
  - [ ] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.15
  - [ ] GIF Walkthrough: 
  https://user-images.githubusercontent.com/21267287/31911869-0dcbd798-b810-11e7-9ad2-e1a1c052dfe1.gif
  - [ ] Steps to recreate: 
  first create a file exceeding the maximum size that can be uploaded, rename the file “Dinosaurs secret life<img src=x onerror=alert(1)>.png”, then go to Upload New Media page, click on Select Files and choose the file you just created. An error message “Dinosaurs secret life.png exceeds the maximum upload size for this site” will be shown, following by an alert box.
  - [ ] Affected source code:
    - [Link 1](https://github.com/WordPress/WordPress/commit/8c7ea71edbbffca5d9766b7bea7c7f3722ffafa6)

2. WordPress  4.0-4.7.2 - Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds (CVE-ID: CVE-2017-6817)
- [ ] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.13
  - [ ] GIF Walkthrough: 
  https://user-images.githubusercontent.com/21267287/31911870-0dd61294-b810-11e7-93f3-20af76d255e1.gif
  - [ ] Steps to recreate: 
  when creating a new post, try to insert a link, type [embed src='https://youtube.com/embed/12345\x3csvg onload=alert(1)\x3e'][/embed] in URL, you can have any Link Text you want. After publishing it, click on View Post, which may direct you to the post, then an alert box will be shown. 
  - [ ] Affected source code:
   - [Link 1](https://github.com/WordPress/WordPress/commit/419c8d97ce8df7d5004ee0b566bc5e095f0a6ca8)
 
 
 3. WordPress <= 4.2.3 - Legacy Theme Preview Cross-Site Scripting (XSS)
 - [ ] Summary: 
    - Vulnerability types:
    - Tested in version:
    - Fixed in version: 
  - [ ] GIF Walkthrough: 
  https://user-images.githubusercontent.com/21267287/31911871-0dde0b2a-b810-11e7-9956-4fb60ee0f875.gif
  - [ ] Steps to recreate: 
  - [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/changeset/33549)
