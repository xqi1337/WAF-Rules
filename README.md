Created by xqi :)
 
Cloudflare > Sicherheit > WAF
 
5 Regeln erstellen.
 
1. CLOUDFLARE IP BLOCKS
(ip.src in {173.245.48.0/20 103.21.244.0/22 103.22.200.0/22 103.31.4.0/22 141.101.64.0/18 108.162.192.0/18 190.93.240.0/20 188.114.96.0/20 197.234.240.0/22 198.41.128.0/17 162.158.0.0/15 104.16.0.0/13 104.24.0.0/14 172.64.0.0/13 131.0.72.0/22}) 
or (ip.src in {2400:cb00::/32 2606:4700::/32 2803:f800::/32 2405:b500::/32 2405:8100::/32 2a06:98c0::/29 2c0f:f248::/32})
 
Blockieren
 
2. USERAGENT BLOCKS
(http.user_agent contains "Go-http-client") 
or (http.user_agent contains "Dart") 
or (http.user_agent contains "kakao") 
or (http.user_agent contains "RepoLookoutBot") 
or (http.user_agent contains "Dalvik") 
or (http.user_agent contains "okhttp") 
or (http.user_agent contains "zgrab") 
or (http.user_agent contains "Autoplius") 
or (http.user_agent contains "scanner") 
or (http.user_agent contains "BrightSign") 
or (http.user_agent contains "HeadlessChrome") 
or (http.user_agent contains "GuzzleHttp") 
or (http.user_agent contains "SiteLockSpider") 
or (http.user_agent contains "TwitterBot") 
or (http.user_agent contains "Googlebot") 
or (http.user_agent contains "apache-http-client") 
or (http.user_agent contains "apache-httpclient") 
or (http.user_agent contains "Apache-HttpClient") 
or (http.user_agent contains "Netcraft") 
or (http.user_agent contains "Phishfort") 
or (http.user_agent contains "curl") 
or (http.user_agent contains "axios") 
or (http.user_agent contains "Python") 
or (http.user_agent contains "python") 
or (http.user_agent contains "wget") 
or (cf.client.bot) 
or (http.user_agent contains "Applebot") 
or (http.user_agent contains "Cloudflare-AlwaysOnline") 
or (http.user_agent contains "Cloudflare-AMP") 
or (http.user_agent contains "Cloudflare Insights") 
or (http.user_agent contains "Cloudflare-Workers") 
or (http.user_agent contains "Cloudflare-LoadBalancer") 
or (http.user_agent contains "Cloudflare-Bot-Management") 
or (http.user_agent contains "CloudflareBot")
 
Blockieren
 
3. GENERAL BLOCKS
(ip.geoip.asnum in {13335 209242 202623 139190 12735 22616 18779 12695 2856 64080 209854 215240 14315 132335 4134 23693 50580 134761 212238 42831 61112 16276 132825 12816 59577 47890 140292 17622 263735 13737 46805 9009 328309 51852 400536 4760 132199 8767 9304 48573 211680 35297 398779 137687 34892 58065 19318 46516 4847 394380 11878 46475 47583 133159 30633 44709 137695 56430 44477 46562 27176 38040 35120 41232 209116 7552 133073 56046 212994 206804 42730 64200 63023 207459 397373 55836 202425 12668 15244 10557 45671 30083 16135 15083 16509 399486 29802 42675 398704 44679 137280 45090 203999 47881 15397 12876 28615 23470 9095 43060 398722 60729 24651 60068 393886 41564 54825 134543 27895 198605 58519 141995 55720 13213 207651 38136 36352 38731 11351 45102 8285 62874 207990 62240 136787 7203 136907 17557 135377 14061 396982 45669 45899 36884 29465 55960 55536 9299 44133 3223 49544 46261 60781 137409 46573 203020 8075 147049 398324 18403 399045 262159 37611 42708 20278 55286 135391 13238 18190 22363 206264 1101 45899 29465 4775 17448 32475 14618 24940 60729 63888 132203 22363 8100 29075 197540 200651 15169 17557 210558 12735 55960 60781 46261 211298 62041 206092}) 
or (http.request.method eq "HEAD") 
or (http.host contains ":80") 
or (http.host contains ":8443") 
or (http.host contains ":2095") 
or (http.host contains ":2082") 
or (http.host contains ":443") 
or (http.host contains "www.")
 
Blockieren
 
4. IP BLOCKS
(ip.src in {104.223.104.0/24 110.166.0.0/16 85.234.0.0/16 89.149.38.0/24 2600:1000::/28 2600:1010::/29 191.101.217.0/24 202.43.6.0/24 2001:861::/32 180.150.38.0/24 68.235.50.0/24 103.38.130.0/23 212.103.60.0/23 128.90.160.0/20}) or (ip.src eq 2a05:91c0:1506:14e::) or (ip.src eq 2603:8081:4200:8da:6050:f2d9:3303:815d) or (ip.src eq 142.122.156.94) or (ip.src eq 185.218.127.146) or (ip.src eq 2404:9400:1:0:216:3eff:fef1:dad7) or (ip.src eq 2a00:63c1:a:196::2) or (ip.src eq 45.58.174.18) or (ip.src eq 37.47.166.24) or (ip.src eq 202.185.29.138) or (ip.src eq 212.102.51.248) or (ip.src eq 154.80.68.208) or (ip.src eq 66.115.176.23) or (ip.src eq 27.122.12.157) or (ip.src eq 105.156.45.38) or (ip.src eq 31.20.181.45) or (ip.src eq 176.37.134.214) or (ip.src eq 51.7.168.96) or (ip.src eq 94.71.203.204) or (ip.src eq 87.208.156.40) or (ip.src eq 31.23.129.91) or (ip.src eq 94.102.49.123) or (ip.src eq 88.154.32.178) or (ip.src eq 104.247.100.142) or (ip.src eq 31.204.153.205) or (ip.src eq 99.127.187.112) or (ip.src eq 94.176.48.130) or (ip.src eq 188.94.87.184) or (ip.src eq 37.19.205.152) or (ip.src eq 68.118.143.85) or (ip.src eq 194.116.166.184) or (ip.src eq 95.127.249.55) or (ip.src eq 196.65.197.140) or (ip.src eq 195.66.69.19) or (ip.src eq 31.223.64.93) or (ip.src eq 91.54.34.242) or (ip.src eq 178.151.253.34) or (ip.src eq 117.136.87.165) or (ip.src eq 97.97.66.174) or (ip.src eq 98.25.179.6) or (ip.src eq 202.43.6.55) or (ip.src eq 87.198.28.37) or (ip.src eq 46.246.122.74) or (ip.src eq 198.7.56.228) or (ip.src eq 37.30.10.86) or (ip.src eq 83.219.77.50) or (ip.src eq 65.154.226.170) or (ip.src eq 65.154.226.166) or (ip.src eq 211.25.3.117) or (ip.src eq 89.209.33.3) or (ip.src eq 5.212.154.253) or (ip.src eq 37.14.86.120) or (ip.src eq 107.146.200.255) or (ip.src eq 91.193.131.120) or (ip.src eq 89.28.99.239) or (ip.src eq 102.217.157.223) or (ip.src eq 154.30.116.103) or (ip.src eq 91.234.141.36) or (ip.src eq 92.15.161.107) or (ip.src eq 197.210.77.104) or (ip.src eq 189.40.71.133) or (ip.src eq 99.22.221.187) or (ip.src eq 85.254.125.5) or (ip.src eq 216.247.24.120) or (ip.src eq 102.129.152.96) or (ip.src eq 79.178.152.179) or (ip.src eq 223.190.87.135) or (ip.src eq 143.0.65.207) or (ip.src eq 37.47.144.54) or (ip.src eq 82.221.111.10) or (ip.src eq 73.12.99.33) or (ip.src eq 64.46.184.151) or (ip.src eq 151.47.0.53) or (ip.src eq 37.65.15.246) or (ip.src eq 51.89.128.195) or (ip.src eq 73.223.199.18) or (ip.src eq 116.48.102.21) or (ip.src eq 73.131.60.19) or (ip.src eq 2603:6081:83f0:8b60:ad3b:5aaf:c90c:5340) or (ip.src eq 2607:fb90:ef82:5088:c508:c707:8c41:a168) or (ip.src eq 2607:fb91:90c:a9d3:d110:f29a:69fe:2ce6) or (ip.src eq 2804:431:c7ed:7f25:ed38:8dbc:f476:1cec) or (ip.src eq 2001:b400:e701:516f:7d4c:a816:77bf:1eb8) or (ip.src eq 2600:1700:7d0:eef0:ad59:cdff:4aef:8841) or (ip.src eq 46.4.227.116) or (ip.src eq 138.201.202.232) or (ip.src eq 88.99.92.200) or (ip.src eq 79.151.22.166) or (ip.src eq 65.155.30.101) or (ip.src eq 117.203.69.88) or (ip.src eq 38.181.79.249) or (ip.src eq 157.254.20.4) or (ip.src eq 175.176.65.119) or (ip.src eq 138.199.25.98) or (ip.src eq 85.153.236.141) or (ip.src eq 2402:800:6214:905e:283a:97ec:9468:ec34) or (ip.src eq 43.159.129.209) or (ip.src eq 45.76.45.202) or (ip.src eq 43.128.68.127)
 
Blockieren
 
5. CHALLENGES
(ip.geoip.asnum in {9231 12271 134026 63949 24560 10753 45245 7713 3269 63199 812 201341 701 36873 36923 12849 8560 198488 6568 8764 8772 2860 2914 4808 53831 1103 8167 9121 5400 49434 39134 9541 28283 12695 268581 2516 36903 25133 134756 9365 39351 29091 62041 45609 209 140819 28573 9304 9808 6167 63949 47331 31898 61317 4837 174 47524 5432 10143 20473 396507 45727 3257 174 6057 12389 5669 8928 8881 15717 210329 12552 9500 6830 6799 56040 1680 56048 56041 204287 35672 39486 200107 209030 7754 50881 203507 206970 9605 198621 44684 12400 19891 16880 17749 36421 199524 398667 44418 54538 32780 213230 210228 202306 53667 64512}) or (ip.geoip.asnum in {209588 14315 398101 37963 400377 51559 19994 8560 45839 12876 49532 212329 24565 7224 136557 26496 34665 133480 205016 211138 19527 4804 50804 577}) or (ip.geoip.country eq "PK") or (ip.geoip.country eq "NE") or (ip.geoip.country eq "IL") or (ip.geoip.country eq "MM") or (ip.geoip.country eq "BD") or (ip.geoip.country eq "GH") or (ip.geoip.country eq "ZW") or (ip.geoip.country eq "SG") or (ip.geoip.country eq "JM") or (ip.geoip.country eq "SN") or (ip.geoip.country eq "TG") or (ip.geoip.country eq "TO") or (ip.geoip.country eq "TR") or (ip.geoip.country eq "VN") or (ip.geoip.country eq "KW") or (ip.geoip.country eq "NG") or (ip.geoip.country eq "BR") or (ip.geoip.country eq "ZA") or (ip.geoip.country eq "HK") or (ip.geoip.country eq "PH") or (ip.geoip.country eq "AU") or (ip.geoip.country eq "TR") or (ip.geoip.country eq "CN") or (http.user_agent contains "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7)") or (http.user_agent contains "Mozilla/5.0 (X11; Linux i686; rv:109.0)") or (http.request.version eq "HTTP/1.1")
 
Interaktive Herausforderung
 
Nun IPv6 blockieren per:
https://reqbin.com/curl
 
Command einfügen und die Daten ersetzen wie ZONE ID / EMAIL / GLOBAL API, danach auf Start drücken und das wars:
 
curl -X PATCH "https://api.cloudflare.com/client/v4/zones/YOUR-ZONE-ID/settings/ipv6" \
-H "X-Auth-Email: YOUR-CLOUDFLARE-EMAIL@proton.me" \
-H "X-Auth-Key: YOUR-GLOBAL-API-TOKEN" \
-H "Content-Type: application/json" \
--data '{"value":"off"}'
