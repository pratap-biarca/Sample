
## Intro

[![Build Status](https://travis-ci.org/drwetter/testssl.sh.svg?branch=master)](https://travis-ci.org/drwetter/testssl.sh)
[![Gitter](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/drwetter/testssl.sh?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

`testssl.sh` is a free command line tool which checks a server's service on
any port for the support of TLS/SSL ciphers, protocols as well as some
cryptographic flaws.

#### Key features

* Clear output: you can tell easily whether anything is good or bad
* Ease of installation: It works for Linux, Darwin, FreeBSD, NetBSD and
  MSYS2/Cygwin out of the box: no need to install or configure something,
  no gems, CPAN, pip or the like.
* Flexibility: You can test any SSL/TLS enabled and STARTTLS service, not
  only webservers at port 443
* Toolbox: Several command line options help you to run YOUR test and
  configure YOUR output
* Reliability: features are tested thoroughly
* Verbosity: If a particular check cannot be performed because of a missing
  capability on your client side, you'll get a warning
* Privacy: It's only you who sees the result, not a third party
* Freedom: It's 100% open source. You can look at the code, see what's
  going on and you can change it.
* Heck, even the development is open (github)

#### Status

Here in the _2.9dev branch you find the development version_ of the software
-- with new features and maybe some bugs. For the stable version and **a
more thorough description of the command line options** please see
[testssl.sh](https://testssl.sh/ "Go to the site with the stable version
and more documentation") or https://github.com/drwetter/testssl.sh/wiki/Usage-Documentation.

#### Compatibility

testssl.sh is working on every Linux/BSD distribution out of the box. In 2.9dev most
of the limitations of disabled features from the openssl client are gone due to bash-socket-based
checks. testssl.sh also works on otherunixoid system out of the box, supposed they have
`/bin/bash` and standard tools like sed and awk installed. System V needs to have GNU versions
of grep and sed installed. MacOS X and Windows (using MSYS2 or cygwin) work too. OpenSSL
version >= 1 is a must.  OpenSSL version >= 1.0.2 is needed for better LOGJAM checks and to
display bit strengths for key exchanges.

Update notification here or @ [twitter](https://twitter.com/drwetter).

#### Features implemented in [2.9dev](Readme.md#devel)
* Support of supplying timeout value for ``openssl connect`` -- useful for batch/mass scanning
* TLS 1.2 protocol check via socket
* Further tests via TLS sockets and improvements (handshake parsing, completeness, robustness)
* Finding more TLS extensions via sockets
* Using bash sockets where ever possible
* TLS Supported Groups Registry (RFC 7919), key shares extension
* Non-flat JSON support
* File output (CSV, JSON flat, JSON non-flat) supports a minimum severity level (only above supplied level there will be output)
* Native HTML support instead going through 'aha'
* Testing 359 default ciphers (``testssl.sh -e/-E``) with a mixture of sockets and openssl. Same speed as with openssl only but addtional ciphers such as post-quantum ciphers, new CHAHA20/POLY1305, CamelliaGCM etc.
* LUCKY13 and SWEET32 checks
* Ticketbleed check
* LOGJAM: now checking also for known DH parameters
* Check for CAA RR
* Check for OCSP must staple
* Check for session resumption (Ticket, ID)
* Better formatting of output (indentation)
* Choice showing the RFC naming scheme only
* Parallel mass testing
* File input for mass testing can be also nmap grep(p)able (-oG)

#### Further features planned in 2.9dev

https://github.com/drwetter/testssl.sh/issues?q=is%3Aopen+is%3Aissue+milestone%3A2.9dev

#### Contributions

Contributions, feedback,  bug reports are welcome! For contributions please
note: One patch per feature -- bug fix/improvement. Please test your
changes thouroughly as reliability is important for this project.

There's a [coding guideline](https://github.com/drwetter/testssl.sh/wiki/Coding-Style).

Please file bug reports @ https://github.com/drwetter/testssl.sh/issues.

#### Documentation

For a start see the
[wiki](https://github.com/drwetter/testssl.sh/wiki/Man-Page).
Help is needed here. Will Hunt provides a good [description](https://www.4armed.com/blog/doing-your-own-ssl-tls-testing/) for version 2.8, including useful background info.

#### Bug reports

Please file bugs in the issue tracker. Do not forget to provide detailed information,
see https://github.com/drwetter/testssl.sh/wiki/Bug-reporting. Nobody can read your
thoughts -- yet. And only agencies your screen ;-)

----

## External/related projects

Please address questions not specifically to the code of testssl.sh to the
respective projects

#### Cool web frontend
* https://github.com/TKCERT/testssl.sh-webfrontend

#### mass scanner w parallel scans and elastic searching the results
* https://github.com/TKCERT/testssl.sh-masscan

#### Ready-to-go docker images are available at:
* https://quay.io/repository/jumanjiman/testssl
* https://hub.docker.com/r/mvance/testssl/

#### Brew package

* see [#233](https://github.com/drwetter/testssl.sh/issues/233) and
  [https://github.com/Homebrew/homebrew](https://github.com/Homebrew/homebrew)
