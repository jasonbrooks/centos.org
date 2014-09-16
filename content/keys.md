---
title:      "CentOS GPG Keys"
markdown:   basic
is_dynamic: true
---
* Table of contents will replace this text.
{:toc}

#CentOS GPG Keys
{:.no_toc}

#How CentOS uses GPG keys
Each stable RPM package that is published by CentOS Project is signed with a GPG signature. By default, yum and the graphical update tools will verify these signatures and refuse to install any packages that are not signed, or have an incorrect signature. You should always verify the signature of a package prior to installation. These signatures ensure that the packages you install are what was produced by the CentOS Project and have not been altered by any mirror or website providing the packages. 

#Importing Keys
The Project GPG keys are included in the centos-release package, and are typically found in /etc/pki/rpm-gpg. Please note that not all keys in this directory are used by the CentOS project. Some keys may be placed in this directory by 3rd party repositories to enable the secure use of extra packages as well. The keys used by CentOS are enabled in the yum repository configuration, so you generally don't need to manually import them. 

If you want to verify that the keys installed on your system match the keys listed here, you can use GnuPG to check that the key fingerprint matches. For example:

    gpg --quiet --with-fingerprint /etc/pki/rpm-gpg/RPM-GPG-KEY-CentOS-7
    pub  4096R/F4A80EB5 2014-06-23 CentOS-7 Key (CentOS 7 Official Signing Key) <security@centos.org>
      Key fingerprint = 6341 AB27 53D7 8A78 A7C2  7BB1 24C6 A8A7 F4A8 0EB5


#Project Keys
The following keys are currently in use by the CentOS Project for the specified release versions. Please note that each CentOS Linux release may have several GPG keys assigned.

##CentOS-7 Keys

### CentOS 7 Signing Key
    pub  4096R/F4A80EB5 2014-06-23 CentOS-7 Key (CentOS 7 Official Signing Key) <security@centos.org>
      Key fingerprint = 6341 AB27 53D7 8A78 A7C2  7BB1 24C6 A8A7 F4A8 0EB5

### CentOS 7 Debug Key
    pub  2048R/B6792C39 2014-07-15 CentOS-7 Debug (CentOS-7 Debuginfo RPMS) <security@centos.org>
      Key fingerprint = 759D 690F 6099 2D52 6A35  8CBD D0F2 5A3C B679 2C39


### CentOS 7 Testing Key
    pub  4096R/8FAE34BD 2014-06-04 CentOS-7 Testing (CentOS 7 Testing content) <security@centos.org>
      Key fingerprint = BA02 A5E6 AFF9 70F7 269D  D972 C788 93AC 8FAE 34BD


## CentOS 6 Keys

###CentOS-6 Signing Key
    pub  4096R/C105B9DE 2011-07-03 CentOS-6 Key (CentOS 6 Official Signing Key) <centos-6-key@centos.org>
      Key fingerprint = C1DA C52D 1664 E8A4 386D  BA43 0946 FCA2 C105 B9DE


### CentOS-6 Debug Key
    pub  4096R/D0FF3D16 2011-07-03 CentOS-6 Debuginfo Key (CentOS-6 Debuginfo Signing Key) <centos-6-debug-key@centos.org>
      Key fingerprint = 69B3 0F26 BA2B 3AA4 C27C  E4F5 3B75 CF79 D0FF 3D16


### CentOS-6 Testing Key
    pub  4096R/EF1D6DB8 2011-07-03 CentOS-6 Testing Key (CentOS-6 Test and Beta Signing Key) <centos-6-testing-key@centos.org>
      Key fingerprint = 4233 9C29 8BC4 352C A4F9  7504 119C 1A87 EF1D 6DB8


### CentOS-6 Security Key
    pub  4096R/FE837F6F 2011-07-03 CentOS-6 Security Key (CentOS-6 Official Security Key) <centos-6-security-key@centos.org>
      Key fingerprint = 0830 F43C 928A A5A8 A6F1  AF97 0B13 2C3F FE83 7F6F


## CentOS 5 Keys

### CentOS-5 Signing Key
    pub  1024D/E8562897 2007-01-06 CentOS-5 Key (CentOS 5 Official Signing Key) <centos-5-key@centos.org>
      Key fingerprint = 473D 66D5 2122 71FD 51CC  17B1 A8A4 47DC E856 2897
    sub  1024g/1E9EA3B6 2007-01-06 [expires: 2017-01-03]

### CentOS-5 Beta Key
    pub  1024D/092D7B2B 2007-01-06 CentOS-5 Beta Key (CentOS 5 Beta Signing Key) <centos-5-beta-key@centos.org>
      Key fingerprint = 5D82 2DFA 48B3 BE04 586C  BD4D CFDA 6881 092D 7B2B
    sub  1024g/DA743639 2007-01-06 [expires: 2017-01-03]


