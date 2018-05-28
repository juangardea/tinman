# tinman
CodePath assignments
# Project 7 - WordPress Pentesting

Time spent: **6** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. (Required) Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds
  - [X] Summary: I copied the youtube video URL and used the embed shortcut to create the attack. I was able to recreate the attack because backlash charaters are filtered out using HTML sanitazion function wp_kses() and it does not consider the escape sequences like \x3c that correspons to < and >.
    - Vulnerability types: XSS
    - Tested in version: WP 4.2
    - Fixed in version: 4.2.13
  - [X] GIF Walkthrough: <img src="https://github.com/juangardea/tinman/blob/master/XSS1.gif" width="800">
  - [X] Steps to recreate: Log in to word press as admin. Create new post and copy [embed src='https://www.youtube.com/embed/M_nIIcKTxGk\x3csvg onload=alert(1)\x3e'][/embed] into the text field. Then publish the post and view.
  - [X] Affected source code: <a href="https://core.trac.wordpress.org/changeset/40160/trunk/src/wp-includes/embed.php?old=38361&old_path=trunk%2Fsrc%2Fwp-includes%2Fembed.php">
  -Link
  
2. (Required) Authenticated Shortcode Tags Cross-Site Scripting (XSS)
  - [X] Summary: XSS scripting vulnerability allows remote attackers to inject web script or HTML by leveraging the mishandling of enclosed HTML elements during processing of shortcode tags. 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.5 
  - [X] GIF Walkthrough: <img src="https://github.com/juangardea/tinman/blob/master/onmouseover.gif" width="800">
  - [X] Steps to recreate: Log in to WP as admin. Create new post and insert code as shows in GIF, then publish the post and view. Hover over "Hover here."
  - [X] Affected source code: <a href="https://github.com/WordPress/WordPress/commit/f72b21af23da6b6d54208e5c1d65ececdaa109c8">
   -Link
  
3. (Required) Authenticated Cross-Site Scripting (XSS)
  - [X] Summary: Multiple cross-site scripting (XSS) vulnerabilities in wp-includes/class-wp-theme.php in WordPress before 4.4.1 allow remote attackers to inject arbitrary web script or HTML via a (1) stylesheet name or (2) template name to wp-admin/customize.php. 
    - Vulnerability types: XSS
    - Tested in version: 4.2
    - Fixed in version: 4.2.6
  - [X] GIF Walkthrough: <img src="https://github.com/juangardea/tinman/blob/master/authenticatedXSS.gif" width= "800">
  - [X] Steps to recreate: Log in as admin to WP. Create a new post and insert code as shown in GIF. Publish post and view. 
  /a>
  - [X] Affected source code: <a href="https://core.trac.wordpress.org/changeset/36185">
   -Link


## Assets

List any additional assets, such as scripts or files

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work

## License

    Copyright [yyyy] [name of copyright owner]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
