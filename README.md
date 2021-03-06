<h1 align="left"><code>htrace.sh</code></h1>

<p align="left">
  <a href="https://travis-ci.org/trimstray/htrace.sh">
    <img src="https://travis-ci.org/trimstray/htrace.sh.svg?branch=master"
        alt="Travis-CI">
  </a>
  <a href="https://github.com/trimstray/htrace.sh/tree/master/build">
    <img src="https://img.shields.io/badge/Docker-Support-blue.svg"
        alt="Docker">
  </a>
</p>

<br>

<p align="center">
    <img src="https://github.com/trimstray/htrace.sh/blob/master/doc/img/htrace.sh_preview.png"
        alt="Master">
</p>

<div align="center">
  <sub>Created by
  <a href="https://twitter.com/trimstray">trimstray</a> and
  <a href="https://github.com/trimstray/htrace.sh/graphs/contributors">
    contributors
  </a>
</div>

<br>

## Description

`htrace.sh` is a shell script that allows you to validate your domain configuration and catch any errors (e.g. redirect loops).

It also displays basic information about the ssl configuration (if available), response headers, response body, extended ssl configuration using testssl.sh tool, checks for mixed content and performs security scans using Nmap scripts and great external tools such as Ssllabs or Mozilla Observatory.

## How To Use

  > Detailed understanding all parameters and how it works, see the **[Wiki](https://github.com/trimstray/htrace.sh/wiki)**.

It's simple:

```bash
# Clone this repository
git clone https://github.com/trimstray/htrace.sh

# Go into the repository
cd htrace.sh

# Install
./setup.sh install

# Run the app
htrace.sh -d http://nmap.org -s -h
```

> * symlink to `bin/htrace.sh` is placed in `/usr/local/bin`
> * man page is placed in `/usr/local/man/man8`

## Parameters

Provides the following options:

```bash
    htrace.sh v1.0.9

Usage:
    htrace.sh <option|long-option>

  Examples:
    htrace.sh -d https://example.com -s -h --testssl --ssllabs
    htrace.sh --domain https://example.com --cache-bypass "?${RANDOM}"
    htrace.sh --domain https://example.com --ssl --headers --proxy "socks5h://127.0.0.1:9501"

  Options:
        --help                                show this message
        -d|--domain <domain_name>             set domain name
        -s|--ssl                              show basic ssl server/connection params
        -h|--headers                          show response headers
        -b|--body                             show response body
        -p|--proxy                            set proxy server (not for external tools)
        --testssl                             test ssl protocols and ciphers with testssl.sh
        --observatory                         scan domain with mozilla observatory security tool
        --ssllabs                             scan domain with ssllabs security tool
        --mixed-content                       scan website for mixed content
        --nse                                 scan website with nmap nse library
        --cache-bypass <val>                  try (proxy) cache bypass
        --user-agent <val>                    set 'User-Agent' header
        --max-redirects <num>                 set max redirects (default: 10)
        --timeout <num>                       set max timeout (default: 15)
        --hide-src-ip                         hide source ip from output
```

## Contributing

See **[this](CONTRIBUTING.md)**.

## License

GPLv3 : <http://www.gnu.org/licenses/>

**Free software, Yeah!**
