# Project 7 - WordPress Pentesting

Time spent: **X** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. WordPress 3.3-4.7.4 - Large File Upload Error XSS
  - [ ] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.15
  - [ ] GIF Walkthrough: 
  1.gif
  - [ ] Steps to recreate: 
  first create a file exceeding the maximum size that can be uploaded, rename the file “Dinosaurs secret life<img src=x onerror=alert(1)>.png”, then go to Upload New Media page, click on Select Files and choose the file you just created. An error message “Dinosaurs secret life.png exceeds the maximum upload size for this site” will be shown, following by an alert box.
  - [ ] Affected source code:
    - [Link 1](https://github.com/WordPress/WordPress/commit/8c7ea71edbbffca5d9766b7bea7c7f3722ffafa6)

2. 
