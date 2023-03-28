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
    

        
- 常见问题

- 确保 Surge 的 MitM，脚本，模块功能正常开启
- 确保 Quantumult X 的 MitM，重写功能正常开启
- 确保 MitM 证书安装成功并信任
- 捷径运行报错或无反应：检查 Surge 或 Quantumult X 配置，一般为对应功能未开启，MitM hostname 设置问题 或 其他规则、重写、脚本、模块不是最新版等影响
- 捷径设置 YouTube 报错可尝试添加 hostname: setting.youtube.com:443
- 官方字幕可能因双语时间线不一致，部分台词仅显示 App 字幕
- Disney+ 官方字幕可能因缓存问题需重启 App 才能生效
- 机器翻译可能因翻译时间过长导致超时无法播放（Prime Video，HBO Max 较明显）
- 开始播放时间依据翻译时间可能会很长（Prime Video，HBO Max 较明显）
- 频繁换剧（即使点开不看）可能会导致 Google 翻译接口被限制（Prime Video，HBO Max 较明显）
- DeepL 注意免费额度，用光后仅显示单字幕
- Netflix 双语字幕播放中可能出现无字幕情况，部分情况重放即可（暂无解决办法）



## 下载

- Surge 模块
    - 聚合版 Dualsub：👉[下载](https://raw.githubusercontent.com/Neurogram-R/Surge/master/module/Dualsub.sgmodule)
    - 独立版
        - Disney+：👉[下载](https://raw.githubusercontent.com/Neurogram-R/Surge/master/module/DisneyPlus-Dualsub.sgmodule)
        - HBO Max：👉[下载](https://raw.githubusercontent.com/Neurogram-R/Surge/master/module/HBO-Max-Dualsub.sgmodule)
        - Hulu：👉[下载](https://raw.githubusercontent.com/Neurogram-R/Surge/master/module/Hulu-Dualsub.sgmodule)
        - Netflix：👉[下载](https://raw.githubusercontent.com/Neurogram-R/Surge/master/module/Netflix-Dualsub.sgmodule)
        - Paramount+：👉[下载](https://raw.githubusercontent.com/Neurogram-R/Surge/master/module/ParamountPlus-Dualsub.sgmodule)
        - Prime Video：👉[下载](https://raw.githubusercontent.com/Neurogram-R/Surge/master/module/Prime-Video-Dualsub.sgmodule)
        - YouTube：👉[下载](https://raw.githubusercontent.com/Neurogram-R/Surge/master/module/YouTube-Dualsub.sgmodule)
    
    <aside>
    💡 按需下载安装 聚合 或 独立版，不是全部安装！
    
    </aside>
    
- Quantumult X Snippet
    - 聚合版 Dualsub：👉[下载](https://raw.githubusercontent.com/Neurogram-R/Quantumult-X/main/snippet/Dualsub.snippet)
    - 独立版
        - Disney+：👉[下载](https://raw.githubusercontent.com/Neurogram-R/Quantumult-X/main/snippet/DisneyPlus-Dualsub.snippet)
        - HBO Max：👉[下载](https://raw.githubusercontent.com/Neurogram-R/Quantumult-X/main/snippet/HBO-Max-Dualsub.snippet)
        - Hulu：👉[下载](https://raw.githubusercontent.com/Neurogram-R/Quantumult-X/main/snippet/Hulu-Dualsub.snippet)
        - Netflix：👉[下载](https://raw.githubusercontent.com/Neurogram-R/Quantumult-X/main/snippet/Netflix-Dualsub.snippet)
        - Paramount+：👉[下载](https://raw.githubusercontent.com/Neurogram-R/Quantumult-X/main/snippet/ParamountPlus-Dualsub.snippet)
        - Prime Video：👉[下载](https://raw.githubusercontent.com/Neurogram-R/Quantumult-X/main/snippet/Prime-Video-Dualsub.snippet)
        - YouTube：👉[下载](https://raw.githubusercontent.com/Neurogram-R/Quantumult-X/main/snippet/YouTube-Dualsub.snippet)
    
    <aside>
    💡 按需下载安装 聚合 或 独立版，不是全部安装！
    
    </aside>
    
- Shortcuts：👉[安装](https://www.icloud.com/shortcuts/8ec4a2a3af514282bf27a11050f39fc2)
