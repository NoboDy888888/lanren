// ==UserScript==
// @ConfigName        墨鱼自用的QX配置文件
// @Author            Cuttlefish
// @TgChannel         𝐡𝐭𝐭𝐩𝐬://𝐭.𝐦𝐞/𝐝𝐝𝐠𝐤𝐬𝐟𝟐𝟎𝟐𝟏
// @Feedback          💡请通过邮件反馈问题[其它方式一概无视]：ddgksf2013@163.com 💡
// @WechatID          公众号墨鱼手记
// @UpdateTime        2022/10/30 10:20 UTC/GMT +8
// @Explain           🌷若有额外的需求，可以WX联系我「𝐝𝐝𝐠𝐤𝐬𝐟𝟐𝟎𝟏𝟑」🌷
// @Function          请参考对应的注释或Tag
// @Appreciate        https://shrtm.nu/hGk2
// @MainFunction      去开屏广告、超级VIP、智能分流、图标订阅、流媒体查询、Boxjs订阅、网易云解灰色Music、IOS更新屏蔽
// @ExpressThanks     @ddgksf2013,@Nick-workflow,@KOP-XIAO,@DivineEngine,@blackmatrix7,@Orz-3,@yjqiang,@O7Y0,@Peng-YM,@Neurogram-R,@id77,@NobyDa,@17mon
// @ConfigVersion     2.0 (V143)
// @ConfigURL         https://gitlab.com/ddgksf2013/Cuttlefish/-/raw/master/Profile/QuantumultX.conf
// ==/UserScript==

# 𝐂𝐮𝐭𝐭𝐥𝐞𝐟𝐢𝐬𝐡 𝐒𝐞𝐥𝐟-𝐮𝐬𝐞 𝐂𝐨𝐧𝐟𝐢𝐠𝐮𝐫𝐚𝐭𝐢𝐨𝐧 𝐂𝐡𝐚𝐧𝐠𝐞𝐥𝐨𝐠 𝐂𝐫𝐞𝐚𝐭𝐞𝐝 𝐛𝐲 𝐝𝐝𝐠𝐤𝐬𝐟𝟐𝟎𝟏𝟑
# [+]2022-03-01  1、QX小白配置2.0已全面更新，重点更新[rewrite_remote]内容  
# [+]2022-03-15  2、QX配置头增加网易云解锁指导、图标库、IOS屏蔽更新、旧版文档、Crack腾讯文档  
# [+]2022-03-26  3、增加[替换支付宝内淘票票评分为豆瓣评分]和[豆瓣添加便捷播放按钮&展示在映流媒体平台]  
# [+]2022-03-30  4、增加墨鱼专属VIPcrack订阅[请自行添加hostname]  
# [+]2022-03-30  5、新增QX的GeoIP自动更新Url链接[内容见header]  
# [+]2022-03-31  6、新增什么值得买APP去广告的引用@blackmatrix7  
# [+]2022-04-04  7、增加@Orz-3的big和mini图标链接  
# [+]2022-04-14  8、添加QX进阶版使用教程@kopshawn  
# [+]2022-04-14  9、添加魔法订阅，仅供临时使用  
# [+]2022-04-21 10、添加Siri与搜索2.0配置@VirgilClyne  
# [+]2022-04-26 11、添加微信解锁被屏蔽的URL@zZPiglet  
# [+]2022-04-30 12、对rewrite_remote进行分类，并添加Q-Search  
# [+]2022-05-02 13、更换魔法订阅链接，仅供临时使用[订阅来源于网络]  
# [+]2022-05-06 14、贴吧去广告更换为@app2smile的库链接，删除[server_local]下无用的网易云解锁节点 
# [-]2022-05-12 15、从实用性角度出发，小白2.0配置注释掉Siri搜索与油管字幕翻译，有需要者自行去掉注释  
# [+]2022-05-15 16、增加网易云的policy，替换网易云policy的图标url  
# [+]2022-05-28 17、微博油管去广告替换为原作者独有链接  
# [+]2022-06-09 18、建议网易云解锁订阅后加上[#checkurl=http://interface3.music.163.com]，添加喜马拉雅去广告  
# [+]2022-07-10 19、精简DNS，添加更多geo_location_checker选项  
# [-]2022-07-31 20、去除B站自动策略，有需要，请自行添加，精简配置头的部分说明
# [+]2022-08-05 21、新增节点响应时间限制server_check_timeout
# [+]2022-08-15 22、将geo_location_checker设置为disabled，删除几条通用去广告（与StartUp.conf有部分重复，也与知乎、值得买等有重复）
# [+]2022-08-17 23、将DivineEngine的更改为blackmatrix7的Advertising.conf，将未启用的重写放置QX界面最下端，
# [+]2022-08-21 24、添加dprefer-doh3(doh-server = https://223.5.5.5/dns-query, https://223.6.6.6/dns-query)QX1.0.30+
# [+]2022-09-19 25、将final分流绑定黑白名单policy，由用户自行选择直连或是代理，server_check_url响应地址改为http://www.gstatic.com/generate_204
# [+]2022-09-29 26、直连分流替换为VirgilClyne 的ASN.China.list，添加不mimt抖音、ios天气、google的host；更换header图标说明
# [+]2022-10-19 27、应群友邮件需求，墨鱼小白配置2.0中策略组新增自动选择，更新方法，可将policy部分进行替换
# [+]2022-10-22 28、策略组tolerance调整，自动选择的策略组自动排除网易云节点，油管去广告换回墨鱼整理的
# [+]2022-10-30 29、新增一个临时使用的魔法@Jsnzkpg

# > 建议在「其他设置」里「GeoLite2」的「来源」填写使用下面链接「任选一个」，并开启「自动更新」
# https://raw.githubusercontent.com/Loyalsoldier/geoip/release/Country.mmdb
; https://github.com/Hackl0us/GeoIP2-CN/raw/release/Country.mmdb


# > 解锁网易云灰色音乐，获取证书链接 
; https://raw.githubusercontent.com/nondanee/UnblockNeteaseMusic/master/ca.crt
# > 具体操作步骤可参考下面这篇《利用QuantumultX解锁网易云付费及非版权音乐》文章
; https://mp.weixin.qq.com/s/khPF7ti95o7-foiqiooDow


# > QuantumultX图标库订阅，打开以下URL，手机端点击图片即可快捷添加「1.0.30+」
; https://gitlab.com/ddgksf2013/Cuttlefish/-/blob/master/Icon/README.md


# > 推荐使用的旧版应用如下链接所示
; https://docs.qq.com/sheet/DYmRTQXpVY0hNcGls?tab=y6do1j
# > 利用描述文件屏蔽IOS更新提醒（兼容IOS13、14、15）
; https://app.initnil.com/tvOS.mobileconfig


[general]

# > 用于节点延迟测试
#server_check_url= http://www.gstatic.com/generate_204
# > 服务器测试超时时间 (毫秒)
#server_check_timeout = 3000
# > 用于设置图标显示
profile_img_url=https://github.githubassets.com/images/modules/site/integrators/google.png
# > 用于Check节点IP地址(以下geo_location_checker任选一个即可)
geo_location_checker=http://ip-api.com/json/?lang=zh-CN, https://raw.githubusercontent.com/I-am-R-E/Functional-Store-Hub/Master/GeoLocationChecker/QuantumultX/IP-API-TaiwanFlag.js

# > 功能强大的解析器，用于引用资源的转换
resource_parser_url=https://raw.githubusercontent.com/KOP-XIAO/QuantumultX/master/Scripts/resource-parser.js
# > 下列路径将不经过QuanX的处理
excluded_routes=239.255.255.250/32, 24.105.30.129/32, 185.60.112.157/32, 185.60.112.158/32, 182.162.132.1/32
udp_whitelist=1-442, 444-65535
# > 第一个filter为4g模式开启规则分流，第二个filter为其他wifi下开启规则分流，第三个wifi1修改成你路由器翻墙的wifi名开启直连模式，第四个wifi2为你公司或者其他有路由器翻墙的WiFi名走直连）
# > 默认关闭根据wifi切换模式，如需开启，删除下方的"#"即可
#running_mode_trigger=filter, filter, wifi1:all_direct, wifi2: all_direct
# > dns_exclusion_list
dns_exclusion_list=*.cmpassport.com, *.jegotrip.com.cn, *.icitymobile.mobi, id6.me, *.pingan.com.cn, *.cmbchina.com




[task_local]
0 8-22/3 * * * https://raw.githubusercontent.com/Peng-YM/QuanX/master/Tasks/nCov.js, tag=疫情动态, img-url=https://qxnav.com/rules/QuantumultX/img/COVID-19.png, enabled=false

# > 请手动添加下面的订阅（流媒体Task订阅集合）
; https://raw.githubusercontent.com/KOP-XIAO/QuantumultX/master/Scripts/UI-Action.json
# > 流媒体解锁查询
event-interaction https://raw.githubusercontent.com/KOP-XIAO/QuantumultX/master/Scripts/streaming-ui-check.js, tag=流媒体解锁查询, img-url=arrowtriangle.right.square.system, enabled=true




[rewrite_local]




[rewrite_remote]

#>>>>>>>>>>>解锁会员
https://gitlab.com/ddgksf2013/Cuttlefish/-/raw/master/Rewrite/ForOwnUse.conf, tag=墨鱼专属VIP@ddgksf2013, update-interval=86400, opt-parser=false, enabled=false
https://gitlab.com/ddgksf2013/Cuttlefish/-/raw/master/Rewrite/AdBlock/Bilibili.conf, tag=B站去广告+1080P高码率@ddgksf2013, update-interval=86400, opt-parser=false, enabled=true
https://gitlab.com/ddgksf2013/Cuttlefish/-/raw/master/Rewrite/UnlockVip/Spotify.conf, tag=Spotify音乐VIP@app2smile, update-interval=86400, opt-parser=false, enabled=true


#>>>>>>>>>>>软件增强
https://gitlab.com/ddgksf2013/Cuttlefish/-/raw/master/Rewrite/UnlockVip/BaiduCloud.conf, tag=百度网盘倍速@ddgksf2013, update-interval=86400, opt-parser=false, enabled=true
https://raw.githubusercontent.com/zZPiglet/Task/master/UnblockURLinWeChat.conf, tag=微信解锁被屏蔽的URL@zZPiglet, update-interval=86400, opt-parser=false, enabled=true
https://raw.githubusercontent.com/Orz-3/QuantumultX/master/TikTok.conf, tag=Tiktok解锁[需旧版V21]@Orz-3, update-interval=86400, opt-parser=false, enabled=true
https://raw.githubusercontent.com/Orz-3/QuantumultX/master/Netflix_ratings.conf, tag=Netflix评分@Orz-3, update-interval=86400, opt-parser=false, enabled=false


#>>>>>>>>>>>应用去广告
https://gitlab.com/ddgksf2013/Cuttlefish/-/raw/master/Rewrite/AdBlock/StartUp.conf, tag=应用去开屏广告@ddgksf2013, update-interval=86400, opt-parser=false, enabled=true
https://raw.githubusercontent.com/blackmatrix7/ios_rule_script/master/script/zhihu/zhihu_plus.qxrewrite, tag=知乎去广告及体验增强@blackmatrix7, update-interval=86400, opt-parser=false, enabled=true
https://raw.githubusercontent.com/blackmatrix7/ios_rule_script/master/script/smzdm/smzdm_remove_ads.qxrewrite, tag=什么值得买去广告@blackmatrix7, update-interval=86400, opt-parser=false, enabled=true
https://github.com/app2smile/rules/raw/master/module/tieba-qx.conf, tag=百度贴吧超级去广告@app2smile, update-interval=86400, opt-parser=false, enabled=true
https://gitlab.com/ddgksf2013/Cuttlefish/-/raw/master/Rewrite/AdBlock/Applet.conf, tag=微信小程序去广告@ddgksf2013, update-interval=86400, opt-parser=false, enabled=true
https://gitlab.com/ddgksf2013/Cuttlefish/-/raw/master/Rewrite/AdBlock/YoutubeAds.conf, tag=油管去广告@DivineEngine, update-interval=86400, opt-parser=false, enabled=true
https://github.com/zmqcherish/proxy-script/raw/main/weibo.conf, tag=微博去广告@zmqcherish, update-interval=86400, opt-parser=false, enabled=true
https://gitlab.com/ddgksf2013/Cuttlefish/-/raw/master/Rewrite/AdBlock/Ximalaya.conf, tag=喜马拉雅去广告@ddgksf2013, update-interval=86400, opt-parser=false, enabled=true


#>>>>>>>>>>>通用去广告
https://raw.githubusercontent.com/blackmatrix7/ios_rule_script/master/rewrite/QuantumultX/Advertising/Advertising.conf, tag=去广告重写@blackmatrix7, update-interval=86400, opt-parser=false, enabled=true
https://raw.githubusercontent.com/DivineEngine/Profiles/master/Quantumult/Rewrite/General.conf, tag=神机重定向@DivineEngine, update-interval=86400, opt-parser=false, enabled=true


#>>>>>>>>>>>网页优化
https://gitlab.com/ddgksf2013/Cuttlefish/-/raw/master/Html/WebAdBlock.conf, tag=影视网站去广告@ddgksf2013, update-interval=86400, opt-parser=false, enabled=true
https://gitlab.com/ddgksf2013/Cuttlefish/-/raw/master/Rewrite/Function/Q-Search.conf, tag=Safari超级搜索@ddgksf2013, update-interval=86400, opt-parser=false, enabled=true

#>>>>>>>>>>>未启用的重写
https://gitlab.com/ddgksf2013/Cuttlefish/-/raw/master/Rewrite/UnlockVip/Rrtv.conf, tag=人人视频VIP@ddgksf2013, update-interval=86400, opt-parser=false, enabled=false
https://gitlab.com/ddgksf2013/Cuttlefish/-/raw/master/Rewrite/UnlockVip/Kuwo.conf, tag=酷我音乐VIP@ddgksf2013, update-interval=86400, opt-parser=false, enabled=false
https://raw.githubusercontent.com/Orz-3/QuantumultX/master/JD_TB_price.conf, tag=比价脚本@Orz-3, update-interval=86400, opt-parser=false, enabled=false
https://gitlab.com/ddgksf2013/Cuttlefish/-/raw/master/Rewrite/Function/BilibiliAutoRegion.conf, tag=B站换区脚本[不会配置boxjs请勿勾选]@NobyDa, update-interval=86400, opt-parser=true, enabled=true
https://raw.githubusercontent.com/id77/QuantumultX/master/rewrite/Youtube_CC.conf#out=Hant, tag=油管字幕翻译@id77, update-interval=86400, opt-parser=false, enabled=false
https://raw.githubusercontent.com/chavyleung/scripts/master/box/rewrite/boxjs.rewrite.quanx.conf, tag=BoxJS商店版@chavyleung, update-interval=86400, opt-parser=false, enabled=true


[server_local]




[server_remote]
https://100567.xyz/api/v1/client/subscribe?token=a757069da309d076591074520ab72048#out=官方+套餐+距离, tag=宝贝云, img-url=https://raw.githubusercontent.com/Koolson/Qure/master/IconSet/Color/Renzhe.png, update-interval=172800, opt-parser=true, enabled=true
https://www.nysub.cc/api/v1/client/subscribe?token=7a06aea8b6fd13b4a8792235f11dd978, tag=奈云, img-url=https://raw.githubusercontent.com/Koolson/Qure/master/IconSet/Color/ssLinks.png, update-interval=172800, opt-parser=true, enabled=true

# > 为避免网易云解锁节点滥用，有需求的请去墨鱼手记公众号回复「网易云」获取

# > 魔法仅供临时使用




[dns]

prefer-doh3
no-ipv6
no-system
server=223.5.5.5
server=119.29.29.29
server=114.114.114.114
doh-server = https://223.5.5.5/dns-query, https://223.6.6.6/dns-query




[policy]
static=网易云音乐, direct, img-url=https://raw.githubusercontent.com/Koolson/Qure/master/IconSet/Color/Netease_Music_Unlock.png
static=香港节点, server-tag-regex=(?=.*(港|HK|(?i)Hong))^((?!(台|日|韩|新|美)).)*$, img-url=https://raw.githubusercontent.com/Orz-3/mini/master/Color/HK.png
static=狮城节点, server-tag-regex=(?=.*(新|狮|獅|SG|(?i)Singapore))^((?!(港|台|日|韩|美)).)*$, img-url=https://raw.githubusercontent.com/Orz-3/mini/master/Color/SG.png
static=台湾节点, server-tag-regex=(?=.*(台|TW|(?i)Taiwan))^((?!(港|日|韩|新|美)).)*$, img-url=https://raw.githubusercontent.com/Orz-3/mini/master/Color/TW.png

static=日本节点, server-tag-regex=(?=.*(日|JP|(?i)Japan))^((?!(港|台|韩|新|美)).)*$, img-url=https://raw.githubusercontent.com/Orz-3/mini/master/Color/JP.png
static=美国节点, server-tag-regex=(?=.*(美|US|(?i)States|American))^((?!(港|台|日|韩|新)).)*$, img-url=https://raw.githubusercontent.com/Orz-3/mini/master/Color/US.png
static=Netflix, 香港节点, 狮城节点, 台湾节点, 日本节点, 美国节点, proxy, img-url=https://raw.githubusercontent.com/Koolson/Qure/master/IconSet/Color/Netflix.png
static=Disney +, 香港节点, 狮城节点, 台湾节点, 美国节点, 日本节点, proxy, img-url=https://raw.githubusercontent.com/Koolson/Qure/master/IconSet/Color/Disney.png

static=BiliBili, direct, 香港节点, 台湾节点, img-url=https://raw.githubusercontent.com/Koolson/Qure/master/IconSet/Color/bilibili_3.png

static=YouTube, 香港节点, 台湾节点, 狮城节点, 日本节点, 美国节点, proxy, img-url=https://raw.githubusercontent.com/Koolson/Qure/master/IconSet/Color/YouTube.png

static=Telegram, 香港节点, 狮城节点, 台湾节点, 美国节点, 日本节点, proxy, img-url=https://raw.githubusercontent.com/Koolson/Qure/master/IconSet/Color/Telegram.png
static=China, direct, proxy, img-url=https://raw.githubusercontent.com/Koolson/Qure/master/IconSet/Color/China_Map.png
static=苹果服务, direct, 香港节点, 台湾节点, 美国节点, 日本节点, 狮城节点, proxy, img-url=https://raw.githubusercontent.com/Orz-3/mini/master/Color/Apple.png
static=兜底分流, direct, 香港节点, 台湾节点, 日本节点, 狮城节点, 美国节点, proxy, img-url=https://raw.githubusercontent.com/Orz-3/mini/master/Color/Final.png





[filter_remote]
https://gitlab.com/ddgksf2013/Cuttlefish/-/raw/master/Filter/NeteaseMusic.list, tag=解锁网易云音乐, force-policy=网易云音乐, update-interval=172800, opt-parser=false, enabled=false
https://raw.githubusercontent.com/DivineEngine/Profiles/master/Surge/Ruleset/Unbreak.list, tag=规则修正, force-policy=direct, update-interval=172800, opt-parser=true, enabled=true
https://raw.githubusercontent.com/DivineEngine/Profiles/master/Surge/Ruleset/Guard/Advertising.list, tag=广告拦截, force-policy=reject, update-interval=172800, opt-parser=true, enabled=true
https://raw.githubusercontent.com/DivineEngine/Profiles/master/Surge/Ruleset/Guard/AdvertisingPlus.list#type=domain-set, tag=广告拦截, force-policy=reject, update-interval=172800, opt-parser=true, enabled=true
https://raw.githubusercontent.com/NobyDa/Script/master/Surge/AdRule.list, tag=广告拦截, force-policy=reject, update-interval=172800, opt-parser=true, enabled=true
https://raw.githubusercontent.com/app2smile/rules/master/rule/tieba-ad-qx.list, tag=贴吧广告, force-policy=reject, update-interval=172800, opt-parser=false, enabled=true
https://raw.githubusercontent.com/DivineEngine/Profiles/master/Surge/Ruleset/Guard/Hijacking.list, tag=运营劫持, force-policy=reject, update-interval=172800, opt-parser=true, enabled=true
https://raw.githubusercontent.com/DivineEngine/Profiles/master/Surge/Ruleset/Guard/Privacy.list, tag=隐私保护, force-policy=reject, update-interval=172800, opt-parser=true, enabled=true
https://raw.githubusercontent.com/blackmatrix7/ios_rule_script/master/rule/QuantumultX/China/China.list, tag=中国大陆, force-policy=direct, update-interval=172800, opt-parser=true, enabled=true
https://raw.githubusercontent.com/DivineEngine/Profiles/master/Surge/Ruleset/Extra/Apple/Apple.list, tag=苹果服务, force-policy=苹果服务, update-interval=172800, opt-parser=true, enabled=true
https://raw.githubusercontent.com/VirgilClyne/GetSomeFries/main/ruleset/ASN.China.list, tag=国内网站, force-policy=direct, update-interval=172800, opt-parser=true, enabled=true
https://raw.githubusercontent.com/blackmatrix7/ios_rule_script/master/rule/QuantumultX/Netflix/Netflix.list, tag=Netflix, force-policy=Netflix, update-interval=172800, opt-parser=false, enabled=true
https://raw.githubusercontent.com/blackmatrix7/ios_rule_script/master/rule/QuantumultX/Disney/Disney.list, tag=Disney +, force-policy=Disney +, update-interval=172800, opt-parser=false, enabled=true
https://raw.githubusercontent.com/blackmatrix7/ios_rule_script/master/rule/QuantumultX/Telegram/Telegram.list, tag=Telegram 规则, force-policy=Telegram, update-interval=86400, opt-parser=false, enabled=true
https://raw.githubusercontent.com/blackmatrix7/ios_rule_script/master/rule/QuantumultX/BiliBili/BiliBili.list, tag=Bilibili 规则, force-policy=BiliBili, update-interval=86400, opt-parser=false, enabled=true
https://raw.githubusercontent.com/blackmatrix7/ios_rule_script/master/rule/QuantumultX//YouTube/YouTube.list, tag=YouTube 规则, force-policy=YouTube, update-interval=86400, opt-parser=false, enabled=true

https://raw.githubusercontent.com/DivineEngine/Profiles/master/Surge/Ruleset/Extra/Google/GoogleVoice.list, tag=Google Voice, force-policy=美国节点, update-interval=172800, opt-parser=true, enabled=false
https://raw.githubusercontent.com/DivineEngine/Profiles/master/Surge/Ruleset/StreamingMedia/Region/HK.list, tag=流媒体HK, force-policy=香港节点, update-interval=172800, opt-parser=true, enabled=false
https://raw.githubusercontent.com/DivineEngine/Profiles/master/Surge/Ruleset/StreamingMedia/Region/TW.list, tag=流媒体TW, force-policy=台湾节点, update-interval=172800, opt-parser=true, enabled=false
https://raw.githubusercontent.com/DivineEngine/Profiles/master/Surge/Ruleset/StreamingMedia/Region/JP.list, tag=流媒体JP, force-policy=日本节点, update-interval=172800, opt-parser=true, enabled=false
https://raw.githubusercontent.com/DivineEngine/Profiles/master/Surge/Ruleset/StreamingMedia/Region/US.list, tag=流媒体US, force-policy=美国节点, update-interval=172800, opt-parser=true, enabled=false




[filter_local]
# > 知乎AD屏蔽,以下规则请放置在filter_local最顶部
DOMAIN,118.89.204.198,REJECT
DOMAIN-KEYWORD,118.89.204.198,REJECT
IP-CIDR,118.89.204.198/32,REJECT
DOMAIN,appcloud2.in.zhihu.com,REJECT
HOST,mqtt.zhihu.com,reject
HOST,sugar.zhihu.com,reject
USER-AGENT,AVOS*,REJECT

# > B站自动换区
ip-cidr, 203.107.1.1/24, reject


# > local
ip-cidr, 10.0.0.0/8, direct
ip-cidr, 127.0.0.0/8, direct
ip-cidr, 172.16.0.0/12, direct
ip-cidr, 192.168.0.0/16, direct
ip-cidr, 224.0.0.0/24, direct
ip-cidr, 182.254.116.0/24, direct
geoip, cn, direct
final, 兜底分流




[http_backend]

# > Boxjs设置，改为使用http backend方式，访问地址改为http://127.0.0.1:9999，更新配置后请长按风车-更新，然后重启代理
# > BoxJs相关教程参考 https://chavyleung.gitbook.io/boxjs/
https://raw.githubusercontent.com/chavyleung/scripts/master/chavy.box.js, host=boxjs.com, tag=BoxJS, path=^/, enabled=true




[mitm]
passphrase = CE89A988
p12 = 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

skip_validating_cert = true
force_sni_domain_name = false
