# AD
这是我第一个仓库，体验一下github使用。

## Surge

Remove Weibo's ads, promotion and recommend

```
[MITM]
hostname = api.weibo.cn, mapi.weibo.com, *.uve.weibo.com

[Script]
http-response ^https?://m?api\.weibo\.c(n|om)/2/(statuses/(unread|extend|positives/get|(friends|video)(/|_)timeline)|stories/(video_stream|home_list)|(groups|fangle)/timeline|profile/statuses|comments/build_comments|photo/recommend_list|service/picfeed|searchall|cardlist|page) script-path=https://raw.githubusercontent.com/tielog/AD/master/wb_ad.js,requires-body=true
http-response ^https?://(sdk|wb)app\.uve\.weibo\.com(/interface/sdk/sdkad.php|/wbapplua/wbpullad.lua) script-path=https://raw.githubusercontent.com/tielog/AD/master/wb_launch.js,requires-body=true
```
## Quan-X

Remove Weibo's ads, promotion and recommend

```
[rewrite_local]
^https?://m?api\.weibo\.c(n|om)/2/(statuses/(unread|extend|positives/get|(friends|video)(/|_)timeline)|stories/(video_stream|home_list)|(groups|fangle)/timeline|profile/statuses|comments/build_comments|photo/recommend_list|service/picfeed|searchall|cardlist|page) url script-response-body https://raw.githubusercontent.com/tielog/AD/master/wb_ad.js
^https?://(sdk|wb)app\.uve\.weibo\.com(/interface/sdk/sdkad.php|/wbapplua/wbpullad.lua) url script-response-body https://raw.githubusercontent.com/tielog/AD/master/wb_launch.js

[mitm]
hostname = api.weibo.cn, mapi.weibo.com, *.uve.weibo.com
```
