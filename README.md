

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Report

1. (Required)  Authenticated Stored Cross-Site Scripting (XSS)
  - [x] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2.2
    - Fixed in version: 4.3.2
  - [x] GIF Walkthrough: ![image](https://i.gyazo.com/12ebc32af0d6a198aa6f980135175fcf.gif)
  - [x] Steps to recreate: 
    - Get posting privileges from admin, then exploit how HTML is processed and paste the following code onto the post: 
    ```
     <a href="[caption code=">]</a><a title=" onmouseover=alert('exploited')  ">link</a>
    ```

  - [x] Affected source code:
    - [Link 1](https://klikki.fi/adv/wordpress3.html)
1. (Required) YouTube URL Embeds Authenticated Stored Cross-Site Scripting (XSS)
  - [x] Summary: 
    - Vulnerability types: XSS
    - Tested in version: 4.2.2
    - Fixed in version: 4.7.0
  - [x] GIF Walkthrough: [![Image from Gyazo](https://i.gyazo.com/42f2efeaa5d5ed7cc471d78e18178fd4.gif)](https://gyazo.com/42f2efeaa5d5ed7cc471d78e18178fd4)
  - [x] Steps to recreate: 
  - Comment the following on a post: 
    ```
     http://youtube.com/watch?v=exploit<svg onload=alert('Virus')>
    ```
  - [x] Affected source code:
    - media.php
1. (Required) User Account Enumaration
  - [x] Summary: 
    - Vulnerability types: Enumarating Users
    - Tested in version: 4.2.2
    - Fixed in version: Not fixed
  - [x] GIF Walkthrough: [![Image from Gyazo](https://i.gyazo.com/75f3781e86ee15a7cec0073b6119c2ed.gif)](https://gyazo.com/75f3781e86ee15a7cec0073b6119c2ed)
  - [x] Steps to recreate: 
    - Simply log in with different usernames to see whether the user exists. Unfortunately this is also possible through permalinks:
    ```
    http://example.com/author/[insertusernamehere]
    ```
  - [x] Affected source code:
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [Gyazo](http://www.gyazo.com).

## License

    Copyright [2020] [Sam Lee]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
