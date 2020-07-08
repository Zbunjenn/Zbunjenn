#default config
#Date: 2020.06.22
#Author: Fake iAP Server & iSteal

[General]
ipv6 = false
skip-proxy = 192.168.0.0/16,10.0.0.0/8,172.16.0.0/12,localhost,*.local,e.crashlynatics.com
bypass-tun = 10.0.0.0/8,100.64.0.0/10,127.0.0.0/8,169.254.0.0/16,172.16.0.0/12,192.0.0.0/24,192.0.2.0/24,192.88.99.0/24,192.168.0.0/16,198.18.0.0/15,198.51.100.0/24,203.0.113.0/24,224.0.0.0/4,255.255.255.255/32
dns-server = system,8.8.4.4,8.8.8.8,1.1.1.1,1.0.0.1,45.90.28.0
allow-udp-proxy = false
host = 127.0.0.1

[Proxy]

[Remote Proxy]
Fake iAP Server = http://co-op.iapserver.com/isteal/loon/server/server-master.txt
[Remote Filter]
[Proxy Group]
Zbunjen|VS🔮 = select,Fake iAP Server
Zbunjen|Other Apps🛸 = select,DIRECT
Fake iAP Policy = select,Tự Động,Tuỳ Chọn
Fake PXX Policy = select,Tắt,Fake iAP Policy
Tự Động = url-test,Fake iAP Server,url = http://www.google.com/generate_204,interval = 600
Tuỳ Chọn = select,Fake iAP Server
Chặn OTA = select,Tắt,Bật
Chặn Ads = select,Bật,Tắt
Chặn Theo Dõi FB = select,Tắt,Bật
Cydia Tweak = select,Tắt
Bật = select,REJECT
Tắt = select,DIRECT
[Rule]
#Type:DOMAIN-SUFFIX,DOMAIN,DOMAIN-KEYWORD,USER-AGENT,URL-REGEX,IP-CIDR
#Strategy:DIRECT,PROXY,REJECT
#Options:force-remote-dns(Default:false),no-resolve

FINAL,Zbunjen|VS🔮

[Remote Rule]
http://co-op.iapserver.com/isteal/loon/filter/iap-rule.txt, policy=Fake iAP Policy, tag=Fake iAP Rule, enabled=true
http://co-op.iapserver.com/isteal/loon/filter/pxx-rule.txt, policy=Fake PXX Policy, tag=Fake  PXX Rule, enabled=true
[URL Rewrite]
enable = false
^https?:\/\/(www.)?(g|google)\.cn https://www.google.com 302

[Script]
enable = false
[Remote Script]
[Mitm]
ca-p12 = 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
ca-passphrase = TINYCARROTVN2020
skip-server-cert-verify = false
enable = true
hostname = testapps.videostarapp.com
