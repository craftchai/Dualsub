# Dualsub iOS 流媒体 App 字幕脚本
# Disney+ HBO Max Hulu Netflix Paramount+ Prime Video YouTube

## 功能

- 双语官方字幕
    
- 双语外挂字幕
   
- 双语机器翻译字幕（Google、DeepL）
   
- 自定义字幕语言和位置

## 手册

- Surge 版
    1. 下载并安装[捷径](https://www.notion.so/Dualsub-b8b2c5259ef54b349722717ec25c2853)
    2. 下载并安装对应版本的 Surge [模块](https://www.notion.so/Dualsub-b8b2c5259ef54b349722717ec25c2853)
    3. 运行捷径选择对应流媒体 App 并设置语言（参考捷径部分）
    4. 打开流媒体 App 播放并开启字幕（非更改语言，无需重复操作捷径）
    
    <aside>
    💡 Surge 模块安装：首页 → 模块 → 安装新模块
    Surge 模块更新：首页 → 模块 → 侧滑模块 → 更新
    Surge 脚本更新：首页 → 配置 → 外部资源 → 更新
    
    </aside>
    
- Quantumult X 版
    1. 下载并安装[捷径](https://www.notion.so/Dualsub-b8b2c5259ef54b349722717ec25c2853)
    2. 下载并安装对应版本的 Quantumult X [Snippet](https://www.notion.so/Dualsub-b8b2c5259ef54b349722717ec25c2853)
    3. 运行捷径选择对应流媒体 App 并设置语言（参考捷径部分）
    4. 打开流媒体 App 播放并开启字幕（非更改语言，无需重复操作捷径）
    
    <aside>
    💡 Quantumult X Snippet 安装：设置 → 重写 → 引用 → 添加
    Quantumult X Snippet 更新：设置 → 重写 → 引用 → 侧滑 → 更新
    Quantumult X 脚本更新：首页 → 重写规则 → 更新脚本
    
    </aside>
    
- Shortcuts
    - 捷径仅为快捷设置工具，需配合 Surge 或 Quantumult X 使用
    - 切换操作语言：编辑捷径并修改第一个字典内 App_Lang 后面的参数，支持 en 和 cn
    - 设置 DeepL API Key：编辑捷径并修改第一个字典内 DeepL_Key 后面的参数为 API Key
    - 官方字幕
        1. 选择 官方
        2. 选择 官方字幕语言
        3. 选择 字幕位置
        4. 确定
    - Google 翻译
        1. 选择 Google
        2. 选择 源语言（推荐：自动识别）
        3. 选择 目标语言
        4. 选择 字幕位置
        5. 确定
    - DeepL 翻译
        1. 选择 DeepL
        2. 选择 源语言（推荐：自动识别）
        3. 选择 目标语言
        4. 选择 字幕位置
        5. 确定
    - 外挂字幕
        1. 选择 外挂（SRT）
        2. 选择 字幕文件（仅支持 .srt 文件）
        3. 确定
    
    <aside>
    💡 Shortcuts 更新：重新下载安装
    当前仅支持 DeepL API Free 版，暂无支持 Pro 版计划
    
    </aside>
    
- General（自配流媒体）
    - General 为 iOS 端采用 WebVTT 格式字幕的流媒体 App 通用设置，用户需自行配置 Surge 的脚本 或 Quantumult X 的重写
    - 配置流程：
        - 获取字幕请求
            1. 开启 Surge / Quantumult X 全局抓包
            2. 打开流媒体 App 并播放视频
            3. 开启字幕待字幕出现
            4. 关闭  Surge / Quantumult X 抓包
            5. 在抓包数据中搜索请求链接中含有 `vtt` 字段的链接（一般以 `.vtt` 或 `.webvtt` 结尾，部分链接可能为 `.vtt?其他参数` 或  `.webvtt?其他参数` 结尾） 
            6. 查看请求返回数据是否为 WebVTT 格式字幕
            
            <aside>
            💡 常见 WebVTT 格式字幕如下：
            
            WEBVTT
            
            STYLE（字幕样式）
            
            00:00:01:345 —>  00:00:02:678（其他参数）
            字幕内容
            
            00:00:03:456 —>  00:00:04:789（其他参数）
            字幕内容
            
            </aside>
            
        - 配置字幕设置
            1. 打开捷径并编辑
            2. 在 注释动作 `General streaming media service domain list` 下面的 文本动作 内填写请求链接中链接的域名
                
                以 Disney+ 为例，抓取的请求链接为：`https://vod-akc-ap-west-2.media.dssott.com/其他参数.vtt` 这里我们填写  `media.dssott.com` 或 `dssott.com` ，前面的  `vod-akc-ap-west-2` 实际为一个变量，所以我们仅采用后面的内容即可，填写的内容尽可能与其他域名区分，以防止误匹配。有多个域名，一行一个填写在 文本动作 内即可。
                
            3. 运行捷径选择 General 并配置 机器翻译 或 外挂字幕
        - 配置  Surge 脚本 / Quantumult X 重写
            
            Surge 脚本：
            
            ```jsx
            [Script]
            脚本名 = type=http-response,pattern=链接匹配正则,requires-body=1,max-size=0,timeout=30,script-path=脚本路径
            
            [MITM]
            hostname = 链接的 hostname
            ```
            
            Quantumult X 重写：
            
            ```jsx
            [rewrite_local]
            链接匹配正则 url script-response-body 脚本路径
            
            [mitm]
            hostname = 链接的 hostname
            ```
            
        - 部分流媒体配置参考
            - ‎[ARROW Player](https://apps.apple.com/us/app/arrow-player/id1531918842)
                
                ```jsx
                捷径内添加：vimeocdn.com
                
                Surge:
                
                [Script]
                Criterion-Channel = type=http-response,pattern=https:\/\/.+vimeocdn.com\/.+\.webvtt,requires-body=1,max-size=0,timeout=30,script-path=https://raw.githubusercontent.com/Neurogram-R/Surge/master/Dualsub.js
                
                [MITM]
                hostname = *.vimeocdn.com
                
                Quantumult X:
                
                [rewrite_local]
                https:\/\/.+vimeocdn.com\/.+\.webvtt url script-response-body https://raw.githubusercontent.com/Neurogram-R/Quantumult-X/main/Dualsub.js
                
                [mitm]
                hostname = *.vimeocdn.com
                ```
                
            - [‎BritBox by BBC & ITV](https://apps.apple.com/us/app/britbox-by-bbc-itv/id1206838907)
                
                ```jsx
                捷径内添加：britbox.com
                
                Surge:
                
                [Script]
                BritBox = type=http-response,pattern=https:\/\/.+britbox.com\/v1\/subtitles,requires-body=1,max-size=0,timeout=30,script-path=https://raw.githubusercontent.com/Neurogram-R/Surge/master/Dualsub.js
                
                [MITM]
                hostname = *.britbox.com
                
                Quantumult X:
                
                [rewrite_local]
                https:\/\/.+britbox.com\/v1\/subtitles url script-response-body https://raw.githubusercontent.com/Neurogram-R/Quantumult-X/main/Dualsub.js
                
                [mitm]
                hostname = *.britbox.com
                ```
                
            - [BritBox UK](https://apps.apple.com/gb/app/britbox-uk/id1459650701)
                
                ```jsx
                捷径内添加：britbox.co.uk
                
                Surge:
                
                [Script]
                BritBox-UK = type=http-response,pattern=https:\/\/.+britbox.co.uk\/.+\.webvtt,requires-body=1,max-size=0,timeout=30,script-path=https://raw.githubusercontent.com/Neurogram-R/Surge/master/Dualsub.js
                
                [MITM]
                hostname = *.britbox.co.uk
                
                Quantumult X:
                
                [rewrite_local]
                https:\/\/.+britbox.co.uk\/.+\.webvtt url script-response-body https://raw.githubusercontent.com/Neurogram-R/Quantumult-X/main/Dualsub.js
                
                [mitm]
                hostname = *.britbox.co.uk
                ```
                
            - [HBO GO](https://apps.apple.com/sg/app/hbo-go/id1441047916)
                
                ```jsx
                捷径内添加：akamaized.net
                
                Surge:
                
                [Script]
                HBO-GO = type=http-response,pattern=https:\/\/.+akamaized.net\/.+\.vtt,requires-body=1,max-size=0,timeout=30,script-path=https://raw.githubusercontent.com/Neurogram-R/Surge/master/Dualsub.js
                
                [MITM]
                hostname = *.akamaized.net
                
                Quantumult X:
                
                [rewrite_local]
                https:\/\/.+akamaized.net\/.+\.vtt url script-response-body https://raw.githubusercontent.com/Neurogram-R/Quantumult-X/main/Dualsub.js
                
                [mitm]
                hostname = *.akamaized.net
                ```
                
            - [MUBI: Curated Cinema](https://apps.apple.com/us/app/mubi-curated-films/id626148774)
                
                ```jsx
                捷径内添加：mubicdn.net
                
                Surge:
                
                [Script]
                MUBI = type=http-response,pattern=https:\/\/.+mubicdn.net\/.+\.webvtt,requires-body=1,max-size=0,timeout=30,script-path=https://raw.githubusercontent.com/Neurogram-R/Surge/master/Dualsub.js
                
                [MITM]
                hostname = *.mubicdn.net
                
                Quantumult X:
                
                [rewrite_local]
                https:\/\/.+mubicdn.net\/.+\.webvtt url script-response-body https://raw.githubusercontent.com/Neurogram-R/Quantumult-X/main/Dualsub.js
                
                [mitm]
                hostname = *.mubicdn.net
                ```
                
            - ‎[Kanopy](https://apps.apple.com/us/app/kanopy/id1205614510)
                
                ```jsx
                捷径内添加：kanopy.com
                
                Surge:
                
                [Script]
                Kanopy = type=http-response,pattern=https:\/\/.+kanopy.com\/.+\.vtt,requires-body=1,max-size=0,timeout=30,script-path=https://raw.githubusercontent.com/Neurogram-R/Surge/master/Dualsub.js
                
                [MITM]
                hostname = *.kanopy.com
                
                Quantumult X:
                
                [rewrite_local]
                https:\/\/.+kanopy.com\/.+\.vtt url script-response-body https://raw.githubusercontent.com/Neurogram-R/Quantumult-X/main/Dualsub.js
                
                [mitm]
                hostname = *.kanopy.com
                ```
                
            - [Peacock TV: Stream TV & Movies](https://apps.apple.com/us/app/peacock-tv-stream-tv-movies/id1508186374)
                
                ```jsx
                捷径内添加：peacocktv.com
                
                Surge:
                
                [Script]
                Peacock-TV = type=http-response,pattern=https:\/\/.+peacocktv.com\/.+\.webvtt,requires-body=1,max-size=0,timeout=30,script-path=https://raw.githubusercontent.com/Neurogram-R/Surge/master/Dualsub.js
                
                [MITM]
                hostname = *.peacocktv.com
                
                Quantumult X:
                
                [rewrite_local]
                https:\/\/.+peacocktv.com\/.+\.webvtt url script-response-body https://raw.githubusercontent.com/Neurogram-R/Quantumult-X/main/Dualsub.js
                
                [mitm]
                hostname = *.peacocktv.com
                ```
                
            - [Stan.](https://apps.apple.com/au/app/stan/id948095331)
                
                ```jsx
                捷径内添加：stan.com.au
                
                Surge:
                
                [Script]
                Stan = type=http-response,pattern=https:\/\/.+stan.com.au\/.+\.vtt,requires-body=1,max-size=0,timeout=30,script-path=https://raw.githubusercontent.com/Neurogram-R/Surge/master/Dualsub.js
                
                [MITM]
                hostname = *.stan.com.au
                
                Quantumult X:
                
                [rewrite_local]
                https:\/\/.+stan.com.au\/.+\.vtt url script-response-body https://raw.githubusercontent.com/Neurogram-R/Quantumult-X/main/Dualsub.js
                
                [mitm]
                hostname = *.stan.com.au
                ```
                
            - ‎[STARZ](https://apps.apple.com/us/app/starz/id550221096)
                
                ```jsx
                捷径内添加：starz.com
                
                Surge:
                
                [Script]
                STARZ = type=http-response,pattern=https:\/\/.+starz.com\/.+\.vtt,requires-body=1,max-size=0,timeout=30,script-path=https://raw.githubusercontent.com/Neurogram-R/Surge/master/Dualsub.js
                
                [MITM]
                hostname = *.starz.com
                
                Quantumult X:
                
                [rewrite_local]
                https:\/\/.+starz.com\/.+\.vtt url script-response-body https://raw.githubusercontent.com/Neurogram-R/Quantumult-X/main/Dualsub.js
                
                [mitm]
                hostname = *.starz.com
                ```
                
            - [‎The Criterion Channel](https://apps.apple.com/us/app/the-criterion-channel/id1454275199)
                
                ```jsx
                捷径内添加：vimeocdn.com
                
                Surge:
                
                [Script]
                Criterion-Channel = type=http-response,pattern=https:\/\/.+vimeocdn.com\/.+\.webvtt,requires-body=1,max-size=0,timeout=30,script-path=https://raw.githubusercontent.com/Neurogram-R/Surge/master/Dualsub.js
                
                [MITM]
                hostname = *.vimeocdn.com
                
                Quantumult X:
                
                [rewrite_local]
                https:\/\/.+vimeocdn.com\/.+\.webvtt url script-response-body https://raw.githubusercontent.com/Neurogram-R/Quantumult-X/main/Dualsub.js
                
                [mitm]
                hostname = *.vimeocdn.com
                ```
                
            - ‎[Udemy Online Video Courses](https://apps.apple.com/us/app/udemy-online-video-courses/id562413829)
                
                ```jsx
                捷径内添加：udemycdn.com
                
                Surge:
                
                [Script]
                Udemy = type=http-response,pattern=https:\/\/.+udemycdn.com\/.+\.vtt,requires-body=1,max-size=0,timeout=30,script-path=https://raw.githubusercontent.com/Neurogram-R/Surge/master/Dualsub.js
                
                [MITM]
                hostname = *.udemycdn.com
                
                Quantumult X:
                
                [rewrite_local]
                https:\/\/.+udemycdn.com\/.+\.vtt url script-response-body https://raw.githubusercontent.com/Neurogram-R/Quantumult-X/main/Dualsub.js
                
                [mitm]
                hostname = *.udemycdn.com
                ```
                
            - [‎Viki : 精彩亚洲电视剧和电影](https://apps.apple.com/us/app/viki-%E7%B2%BE%E5%BD%A9%E4%BA%9A%E6%B4%B2%E7%94%B5%E8%A7%86%E5%89%A7%E5%92%8C%E7%94%B5%E5%BD%B1/id445553058)
                
                ```jsx
                捷径内添加：viki.io
                
                Surge:
                
                [Script]
                Viki= type=http-response,pattern=https:\/\/.+viki.io\/.+\.vtt,requires-body=1,max-size=0,timeout=30,script-path=https://raw.githubusercontent.com/Neurogram-R/Surge/master/Dualsub.js
                
                [MITM]
                hostname = *.viki.io
                
                Quantumult X:
                
                [rewrite_local]
                https:\/\/.+viki.io\/.+\.vtt url script-response-body https://raw.githubusercontent.com/Neurogram-R/Quantumult-X/main/Dualsub.js
                
                [mitm]
                hostname = *.viki.io
                ```
                
            
            <aside>
            ⚠️ 以上配置均为 用户 提供抓包链接截图后编写，未经测试
            
            </aside>
            
        
        <aside>
        💡 General 的字幕设置优先级高于其他设置，如果 General 设置包含 Disney+、HBO Max 等，则优先采用 General 的设置方案
        
        </aside>
        
- 常见问题
