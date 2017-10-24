# Project 7 - WordPress Pentesting


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
  
  First create a file exceeding the maximum size to be uploaded, rename the file “life<img src=x onerror=alert(1)>.png”, then go to Upload New Media page, click on Select Files and choose the file you just created. An error message “life.png exceeds the maximum upload size for this site” will be shown, following by an alert box.
- [ ] Affected source code:
    - [Link 1](https://github.com/WordPress/WordPress/commit/8c7ea71edbbffca5d9766b7bea7c7f3722ffafa6)

2. WordPress  4.0-4.7.2 - Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds (CVE-ID: CVE-2017-6817)
- [ ] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.13
- [ ] GIF Walkthrough: 
  
  https://user-images.githubusercontent.com/21267287/31912391-be29f63c-b811-11e7-99a4-4506fb1dedc9.gif
- [ ] Steps to recreate: 
  
  When creating a new post, try to insert a link, type "[embed src='https://youtube.com/embed/12345\x3csvg onload=alert(1)\x3e'][/embed]" in URL, then inter anything onto Link Text. After publishing it, click on View Post, which may direct to the post, then an alert box will be shown. 
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
  
    First, go to the Page and select Example Front Page, click on View Page, scroll down to Comment, enter "<a href='/wp-admin/' title="" style="position:absolute;top:0;left:0;width:100%;height:100%;display:block;" onmouseover=alert(1)//'>Test</a>". Then the alert box will show up.
- [ ] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/changeset/33549)



## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/):

https://user-images.githubusercontent.com/21267287/31911869-0dcbd798-b810-11e7-9ad2-e1a1c052dfe1.gif

https://user-images.githubusercontent.com/21267287/31912391-be29f63c-b811-11e7-99a4-4506fb1dedc9.gif

https://user-images.githubusercontent.com/21267287/31911871-0dde0b2a-b810-11e7-9956-4fb60ee0f875.gif

## Notes

Doing those installments took a lot of time. When encountering some technical issues that are not mentioned in the instructions, I needed to spend additional time on finding out the solution on my own. And I think it is hard to choose a vulnerability to regenerate because many reference links do not give enough information.

## License

    Copyright Jin Hui Chen

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
