**请大佬们不要随便对待site url，如果您的LookingGlass直接通过域名访问，请在site url里面填写http://xxx.com (最后不要加"/") 或者https://xxx.com (最后不要加"/")，如果LookingGlass放置在域名目录下的某个文件夹，请在site url里面填写http://xxx.com/xxx (最后不要加"/") 或者https://xxx.com/xxx (最后不要加"/")**

# LookingGlass

程序说明与搭建教程：[https://www.sabia.cc/looking-glass-ip-location.html](https://www.sabia.cc/looking-glass-ip-location.html)

## Demo
[https://lg.test.testip.xyz](https://lg.test.testip.xyz)

## Fork后的修改
1、修改IPv4下的路由追踪，结果将包含由IPIP提供的IP地理信息数据  
2、修改configure.sh文件测试文件生成方式，改由DD命令生成测试文件  
3、汉化index.php文件，并适度修改底部作者信息  
4、添加英文页面，调整路由追踪结果语言  
5、修改IPv6下的路由追踪，结果将包含由IPIP提供的IP地理信息数据  

## Overview

LookingGlass is a user-friendly PHP based looking glass that allows the public (via a web interface) to execute network
commands on behalf of your server.

Current version: v1.3.0

It's recommended that everyone updates their existing install!

## Features

* Automated install via bash script
* IPv4 & IPv6 support
* Live output via long polling
* Multiple themes
* Rate limiting of network commands

## Implemented commands

* host
* mtr
* mtr6 (IPv6)
* ping
* ping6 (IPv6)
* traceroute
* traceroute6 (IPv6)

__IPv6 commands will only work if your server has external IPv6 setup (or tunneled)__

## Requirements

* PHP >= 5.3
* PHP PDO with SQLite driver (required for rate-limit)
* SSH/Terminal access (able to install commands/functions if non-existent)

## Install

1. Download [LookingGlass](https://github.com/ILLKX/LookingGlass/archive/master.zip) to the intended
folder within your web directory
2. Extract archive:
    - Extract archive to the current directory:
        - `unzip master.zip`
3. Navigate to the `LookingGlass` subdirectory in terminal
4. Run `bash configure.sh`
5. Follow the instructions and `configure.sh` will take care of the rest

_Forgot a setting? Simply run the `configure.sh` script again_

## Updating

1. Download [LookingGlass](https://github.com/telephone/LookingGlass/archive/v1.3.0.tar.gz) to the folder containing
your existing install
2. Extract archive: `tar -zxvf LookingGlass-1.3.0.tar.gz --overwrite --strip-components 1`
    - This will overwrite/update existing files
3. Navigate to the `LookingGlass` subdirectory in terminal
4. Run `bash configure.sh`
5. Follow the instructions and `configure.sh` will take care of the rest
    - Note: Re-enter test files to create random test files from `GNU shred`

_Forgot a setting? Simply run the `configure.sh` script again_

## Apache

An .htaccess is included which protects the rate-limit database, disables indexes, and disables gzip on test files.
Ensure `AllowOverride` is on for .htaccess to take effect.

Output buffering __should__ work by default.

For an HTTPS setup, please visit:
- [Mozilla SSL Configuration Generator](https://mozilla.github.io/server-side-tls/ssl-config-generator/)

## Nginx

To enable output buffering, and disable gzip on test files please refer to the provided configuration:

[HTTP setup](LookingGlass/lookingglass-http.nginx.conf)

The provided config is setup for LookingGlass to be on a subdomain/domain root.

For an HTTPS setup please visit:
- [Best nginx configuration for security](http://tautt.com/best-nginx-configuration-for-security/)
- [Mozilla SSL Configuration Generator](https://mozilla.github.io/server-side-tls/ssl-config-generator/)

## License

Code is licensed under MIT Public License.

* If you wish to support my efforts, keep the "Powered by LookingGlass" link intact.
