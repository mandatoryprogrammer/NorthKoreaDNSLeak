![North Korean Flag](https://i.imgur.com/o3mHZ9h.png)
# North Korea .kp TLD Zone Data
On Sept 20, 2016 at approximately 10:00PM, one of North Korea's top level nameservers was accidentally configured to allow global DNS zone tranfers. This allows anyone who performs an `AXFR` (zone transfer) request to the country's `ns2.kptc.kp` nameserver can get a copy of the nation's top level DNS data. This was detected by the [TL;DR Project](https://github.com/mandatoryprogrammer/TLDR) - an effort to attempt zone transfers against all top level domain (TLD) nameservers every two hours and keep a running Github repo with the resulting data. This data gives us a better picture of North Korea's domains and top level DNS.

[Click here for the commit showing this incident.](https://github.com/mandatoryprogrammer/TLDR/blob/132016acc6aa8478bd050deb798178f8d5c630f8/archives/kp/ns2.kptc.kp.zone)

As of the time of this writing, zone transfers are still enabled for multiple `.kp` top level domains via `ns2.kptc.kp`.

## PoC
```
dig AXFR kp. @ns2.kptc.kp
```

## .kp Domains
```
airkoryo.com.kp.
cooks.org.kp.
friend.com.kp.
gnu.rep.kp.
kass.org.kp.
kcna.kp.
kiyctc.com.kp.
knic.com.kp.
koredufund.org.kp.
korelcfund.org.kp.
korfilm.com.kp.
ma.gov.kp.
masikryong.com.kp.
naenara.com.kp.
nta.gov.kp.
portal.net.kp.
rcc.net.kp.
rep.kp.
rodong.rep.kp.
ryongnamsan.edu.kp.
sdprk.org.kp.
silibank.net.kp.
star-co.net.kp.
star-di.net.kp.
star.co.kp.
star.edu.kp.
star.net.kp.
vok.rep.kp.
```

## .kp Zone File Data
```
; <<>> DiG 9.9.5-3ubuntu0.8-Ubuntu <<>> AXFR kp. @ns2.kptc.kp. +nocomments +nocmd +noquestion +nostats +time=15
;; global options: +cmd
kp.         432000  IN  SOA ns1.kptc.kp. root.kptc.kp. 2013083001 28800 86400 1209600 86400
kp.         432000  IN  NS  ns1.kptc.kp.
kp.         432000  IN  NS  ns2.kptc.kp.
kp.         432000  IN  NS  ns3.kptc.kp.
co.kp.          432000  IN  NS  ns1.co.kp.
co.kp.          432000  IN  NS  ns2.co.kp.
ns1.co.kp.      432000  IN  A   175.45.176.15
ns2.co.kp.      432000  IN  A   175.45.176.16
com.kp.         432000  IN  NS  ns1.com.kp.
com.kp.         432000  IN  NS  ns2.com.kp.
ns1.com.kp.     432000  IN  A   175.45.176.15
ns2.com.kp.     432000  IN  A   175.45.176.16
edu.kp.         432000  IN  NS  ns1.edu.kp.
edu.kp.         432000  IN  NS  ns2.edu.kp.
ns1.edu.kp.     432000  IN  A   175.45.176.15
ns2.edu.kp.     432000  IN  A   175.45.176.16
gov.kp.         432000  IN  NS  ns1.gov.kp.
gov.kp.         432000  IN  NS  ns2.gov.kp.
ns1.gov.kp.     432000  IN  A   175.45.176.15
ns2.gov.kp.     432000  IN  A   175.45.176.16
kcna.kp.        432000  IN  NS  ns1.kcna.kp.
kcna.kp.        432000  IN  NS  ns2.kcna.kp.
ns1.kcna.kp.        432000  IN  A   175.45.176.8
ns2.kcna.kp.        432000  IN  A   175.45.176.9
ns1.kptc.kp.        432000  IN  A   175.45.176.15
ns2.kptc.kp.        432000  IN  A   175.45.176.16
net.kp.         432000  IN  NS  ns1.net.kp.
net.kp.         432000  IN  NS  ns2.net.kp.
ns1.net.kp.     432000  IN  A   175.45.176.15
ns2.net.kp.     432000  IN  A   175.45.176.16
org.kp.         432000  IN  NS  ns1.org.kp.
org.kp.         432000  IN  NS  ns2.org.kp.
ns1.org.kp.     432000  IN  A   175.45.176.15
ns2.org.kp.     432000  IN  A   175.45.176.16
rep.kp.         432000  IN  NS  ns1.rep.kp.
rep.kp.         432000  IN  NS  ns2.rep.kp.
ns1.rep.kp.     432000  IN  A   175.45.176.15
ns2.rep.kp.     432000  IN  A   175.45.176.16
kp.         432000  IN  SOA ns1.kptc.kp. root.kptc.kp. 2013083001 28800 86400 1209600 86400
```

## .co.kp Zone File Data

```
; <<>> DiG 9.8.3-P1 <<>> AXFR co.kp. @ns2.kptc.kp
;; global options: +cmd
co.kp.          432000  IN  SOA ns1.co.kp. root.co.kp. 2013082900 28800 86400 1209600 86400
co.kp.          432000  IN  NS  ns1.co.kp.
co.kp.          432000  IN  NS  ns2.co.kp.
ns1.co.kp.      432000  IN  A   175.45.176.15
ns2.co.kp.      432000  IN  A   175.45.176.16
star.co.kp.     432000  IN  NS  ns1.star.co.kp.
star.co.kp.     432000  IN  NS  ns2.star.co.kp.
ns1.star.co.kp.     432000  IN  A   175.45.176.15
ns2.star.co.kp.     432000  IN  A   175.45.176.16
co.kp.          432000  IN  SOA ns1.co.kp. root.co.kp. 2013082900 28800 86400 1209600 86400
;; Query time: 437 msec
;; SERVER: 175.45.176.16#53(175.45.176.16)
;; WHEN: Mon Sep 19 22:28:46 2016
;; XFR size: 10 records (messages 1, bytes 241)
```

## .com.kp Zone File Data

```
; <<>> DiG 9.8.3-P1 <<>> AXFR com.kp. @ns2.kptc.kp
;; global options: +cmd
com.kp.         432000  IN  SOA ns1.com.kp. root.com.kp. 2013112203 28800 86400 1209600 86400
com.kp.         432000  IN  NS  ns1.com.kp.
com.kp.         432000  IN  NS  ns2.com.kp.
airkoryo.com.kp.    432000  IN  NS  ns1.airkoryo.com.kp.
airkoryo.com.kp.    432000  IN  NS  ns2.airkoryo.com.kp.
ns1.airkoryo.com.kp.    432000  IN  A   175.45.176.8
ns2.airkoryo.com.kp.    432000  IN  A   175.45.176.9
friend.com.kp.      432000  IN  NS  ns1.friend.com.kp.
friend.com.kp.      432000  IN  NS  ns2.friend.com.kp.
ns1.friend.com.kp.  432000  IN  A   175.45.176.8
ns2.friend.com.kp.  432000  IN  A   175.45.176.9
kiyctc.com.kp.      432000  IN  NS  ns1.kiyctc.com.kp.
kiyctc.com.kp.      432000  IN  NS  ns2.kiyctc.com.kp.
ns1.kiyctc.com.kp.  432000  IN  A   175.45.176.8
ns2.kiyctc.com.kp.  432000  IN  A   175.45.176.9
knic.com.kp.        432000  IN  NS  ns1.knic.com.kp.
knic.com.kp.        432000  IN  NS  ns2.knic.com.kp.
ns1.knic.com.kp.    432000  IN  A   175.45.176.8
ns2.knic.com.kp.    432000  IN  A   175.45.176.9
korfilm.com.kp.     432000  IN  NS  ns1.korfilm.com.kp.
korfilm.com.kp.     432000  IN  NS  ns2.korfilm.com.kp.
ns1.korfilm.com.kp. 432000  IN  A   175.45.176.8
ns2.korfilm.com.kp. 432000  IN  A   175.45.176.9
masikryong.com.kp.  432000  IN  NS  ns1.masikryong.com.kp.
masikryong.com.kp.  432000  IN  NS  ns2.masikryong.com.kp.
ns1.masikryong.com.kp.  432000  IN  A   175.45.176.8
ns2.masikryong.com.kp.  432000  IN  A   175.45.176.9
naenara.com.kp.     432000  IN  NS  ns1.naenara.com.kp.
naenara.com.kp.     432000  IN  NS  ns2.naenara.com.kp.
ns1.naenara.com.kp. 432000  IN  A   175.45.176.8
ns2.naenara.com.kp. 432000  IN  A   175.45.176.9
ns1.com.kp.     432000  IN  A   175.45.176.15
ns2.com.kp.     432000  IN  A   175.45.176.16
com.kp.         432000  IN  SOA ns1.com.kp. root.com.kp. 2013112203 28800 86400 1209600 86400
;; Query time: 252 msec
;; SERVER: 175.45.176.16#53(175.45.176.16)
;; WHEN: Mon Sep 19 22:29:01 2016
;; XFR size: 34 records (messages 1, bytes 700)
```

## edu.kp Zone File Data

```
; <<>> DiG 9.8.3-P1 <<>> AXFR edu.kp. @ns2.kptc.kp
;; global options: +cmd
edu.kp.         432000  IN  SOA ns1.edu.kp. root.edu.kp. 2013082903 28800 86400 1209600 86400
edu.kp.         432000  IN  NS  ns1.edu.kp.
edu.kp.         432000  IN  NS  ns2.edu.kp.
ns1.edu.kp.     432000  IN  A   175.45.176.15
ns2.edu.kp.     432000  IN  A   175.45.176.16
ryongnamsan.edu.kp. 432000  IN  NS  ns1.ryongnamsan.edu.kp.
ryongnamsan.edu.kp. 432000  IN  NS  ns2.ryongnamsan.edu.kp.
ns1.ryongnamsan.edu.kp. 432000  IN  A   175.45.176.8
ns2.ryongnamsan.edu.kp. 432000  IN  A   175.45.176.9
star.edu.kp.        432000  IN  NS  ns1.star.edu.kp.
ns1.star.edu.kp.    432000  IN  A   175.45.179.76
edu.kp.         432000  IN  SOA ns1.edu.kp. root.edu.kp. 2013082903 28800 86400 1209600 86400
;; Query time: 1433 msec
;; SERVER: 175.45.176.16#53(175.45.176.16)
;; WHEN: Mon Sep 19 22:29:19 2016
;; XFR size: 12 records (messages 1, bytes 288)
```

## gov.kp Zone File Data

```
; <<>> DiG 9.8.3-P1 <<>> AXFR gov.kp. @ns2.kptc.kp
;; global options: +cmd
gov.kp.         432000  IN  SOA ns1.gov.kp. root.gov.kp. 2013082901 28800 86400 1209600 86400
gov.kp.         432000  IN  NS  ns1.gov.kp.
gov.kp.         432000  IN  NS  ns2.gov.kp.
ma.gov.kp.      432000  IN  NS  ns1.ma.gov.kp.
ma.gov.kp.      432000  IN  NS  ns2.ma.gov.kp.
ns1.ma.gov.kp.      432000  IN  A   175.45.176.8
ns2.ma.gov.kp.      432000  IN  A   175.45.176.9
ns1.gov.kp.     432000  IN  A   175.45.176.15
ns2.gov.kp.     432000  IN  A   175.45.176.16
nta.gov.kp.     432000  IN  NS  ns1.nta.gov.kp.
nta.gov.kp.     432000  IN  NS  ns2.nta.gov.kp.
ns1.nta.gov.kp.     432000  IN  A   175.45.176.8
ns2.nta.gov.kp.     432000  IN  A   175.45.176.9
gov.kp.         432000  IN  SOA ns1.gov.kp. root.gov.kp. 2013082901 28800 86400 1209600 86400
;; Query time: 1638 msec
;; SERVER: 175.45.176.16#53(175.45.176.16)
;; WHEN: Mon Sep 19 22:29:36 2016
;; XFR size: 14 records (messages 1, bytes 312)
```

## net.kp Zone File Data

```
; <<>> DiG 9.8.3-P1 <<>> AXFR net.kp. @ns2.kptc.kp
;; global options: +cmd
net.kp.         432000  IN  SOA ns1.net.kp. root.net.kp. 2013082901 28800 86400 1209600 86400
net.kp.         432000  IN  NS  ns1.net.kp.
net.kp.         432000  IN  NS  ns2.net.kp.
ns1.net.kp.     432000  IN  A   175.45.176.15
ns2.net.kp.     432000  IN  A   175.45.176.16
portal.net.kp.      432000  IN  NS  ns1.portal.net.kp.
portal.net.kp.      432000  IN  NS  ns2.portal.net.kp.
ns1.portal.net.kp.  432000  IN  A   175.45.176.8
ns2.portal.net.kp.  432000  IN  A   175.45.176.9
rcc.net.kp.     432000  IN  NS  ns1.rcc.net.kp.
rcc.net.kp.     432000  IN  NS  ns2.rcc.net.kp.
ns1.rcc.net.kp.     432000  IN  A   175.45.176.8
ns2.rcc.net.kp.     432000  IN  A   175.45.176.9
silibank.net.kp.    432000  IN  NS  ns1.silibank.net.kp.
silibank.net.kp.    432000  IN  NS  ns2.silibank.net.kp.
ns1.silibank.net.kp.    432000  IN  A   175.45.176.8
ns2.silibank.net.kp.    432000  IN  A   175.45.176.9
star.net.kp.        432000  IN  NS  ns1.star.net.kp.
star.net.kp.        432000  IN  NS  ns2.star.net.kp.
ns1.star.net.kp.    432000  IN  A   175.45.176.8
ns2.star.net.kp.    432000  IN  A   175.45.176.9
star-co.net.kp.     432000  IN  NS  ns1.star-co.net.kp.
star-co.net.kp.     432000  IN  NS  ns2.star-co.net.kp.
ns1.star-co.net.kp. 432000  IN  A   175.45.176.8
ns2.star-co.net.kp. 432000  IN  A   175.45.176.9
star-di.net.kp.     432000  IN  NS  ns1.star-di.net.kp.
star-di.net.kp.     432000  IN  NS  ns2.star-di.net.kp.
ns1.star-di.net.kp. 432000  IN  A   175.45.176.8
ns2.star-di.net.kp. 432000  IN  A   175.45.176.9
net.kp.         432000  IN  SOA ns1.net.kp. root.net.kp. 2013082901 28800 86400 1209600 86400
;; Query time: 409 msec
;; SERVER: 175.45.176.16#53(175.45.176.16)
;; WHEN: Mon Sep 19 22:30:04 2016
;; XFR size: 30 records (messages 1, bytes 618)
```

## org.kp Zone File Data

```
; <<>> DiG 9.8.3-P1 <<>> AXFR org.kp. @ns2.kptc.kp
;; global options: +cmd
org.kp.         432000  IN  SOA ns1.org.kp. root.org.kp. 2013082900 28800 86400 1209600 86400
org.kp.         432000  IN  NS  ns1.org.kp.
org.kp.         432000  IN  NS  ns2.org.kp.
cooks.org.kp.       432000  IN  NS  ns1.cooks.org.kp.
cooks.org.kp.       432000  IN  NS  ns2.cooks.org.kp.
ns1.cooks.org.kp.   432000  IN  A   175.45.176.8
ns2.cooks.org.kp.   432000  IN  A   175.45.176.9
kass.org.kp.        432000  IN  NS  ns1.kass.org.kp.
kass.org.kp.        432000  IN  NS  ns2.kass.org.kp.
ns1.kass.org.kp.    432000  IN  A   175.45.176.8
ns2.kass.org.kp.    432000  IN  A   175.45.176.9
koredufund.org.kp.  432000  IN  NS  ns1.koredufund.org.kp.
koredufund.org.kp.  432000  IN  NS  ns2.koredufund.org.kp.
ns1.koredufund.org.kp.  432000  IN  A   175.45.176.8
ns2.koredufund.org.kp.  432000  IN  A   175.45.176.9
korelcfund.org.kp.  432000  IN  NS  ns1.korelcfund.org.kp.
korelcfund.org.kp.  432000  IN  NS  ns2.korelcfund.org.kp.
ns1.korelcfund.org.kp.  432000  IN  A   175.45.176.8
ns2.korelcfund.org.kp.  432000  IN  A   175.45.176.9
ns1.org.kp.     432000  IN  A   175.45.176.15
ns2.org.kp.     432000  IN  A   175.45.176.16
sdprk.org.kp.       432000  IN  NS  ns1.sdprk.org.kp.
sdprk.org.kp.       432000  IN  NS  ns2.sdprk.org.kp.
ns1.sdprk.org.kp.   432000  IN  A   175.45.176.8
ns2.sdprk.org.kp.   432000  IN  A   175.45.176.9
org.kp.         432000  IN  SOA ns1.org.kp. root.org.kp. 2013082900 28800 86400 1209600 86400
;; Query time: 409 msec
;; SERVER: 175.45.176.16#53(175.45.176.16)
;; WHEN: Mon Sep 19 22:30:24 2016
;; XFR size: 26 records (messages 1, bytes 548)
```

## rep.kp Zone File Data

```
; <<>> DiG 9.8.3-P1 <<>> AXFR rep.kp. @ns2.kptc.kp
;; global options: +cmd
rep.kp.         432000  IN  SOA ns1.rep.kp. root.rep.kp. 2013082900 28800 86400 1209600 86400
rep.kp.         432000  IN  NS  ns1.rep.kp.
rep.kp.         432000  IN  NS  ns2.rep.kp.
gnu.rep.kp.     432000  IN  NS  ns1.gnu.rep.kp.
gnu.rep.kp.     432000  IN  NS  ns2.gnu.rep.kp.
ns1.gnu.rep.kp.     432000  IN  A   175.45.176.8
ns2.gnu.rep.kp.     432000  IN  A   175.45.176.9
ns1.rep.kp.     432000  IN  A   175.45.176.15
ns2.rep.kp.     432000  IN  A   175.45.176.16
rodong.rep.kp.      432000  IN  NS  ns1.rodong.rep.kp.
rodong.rep.kp.      432000  IN  NS  ns2.rodong.rep.kp.
ns1.rodong.rep.kp.  432000  IN  A   175.45.176.8
ns2.rodong.rep.kp.  432000  IN  A   175.45.176.9
vok.rep.kp.     432000  IN  NS  ns1.vok.rep.kp.
vok.rep.kp.     432000  IN  NS  ns2.vok.rep.kp.
ns1.vok.rep.kp.     432000  IN  A   175.45.176.8
ns2.vok.rep.kp.     432000  IN  A   175.45.176.9
rep.kp.         432000  IN  SOA ns1.rep.kp. root.rep.kp. 2013082900 28800 86400 1209600 86400
;; Query time: 410 msec
;; SERVER: 175.45.176.16#53(175.45.176.16)
;; WHEN: Mon Sep 19 22:30:37 2016
;; XFR size: 18 records (messages 1, bytes 388)
```
