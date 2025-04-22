# Scheduled Requests

这个 GitHub Actions 工作流用于定时向特定的 URL 发送请求。

## 工作流详情

此工作流包含一个名为 `request` 的作业，运行在 `ubuntu-latest` 环境上。

### 计划任务

工作流根据以下计划触发：

1.  **每半小时执行一次 (`*/30 * * * *`)**: 
    - 向以下 URL 发送 `curl` 请求：
        - `http://b.you.anneng.ggff.net/api.php/timming/index.html?enforce=1&name=ziyuanku`
        - `https://ane.anneng.ggff.net/api.php/timming/index.html?enforce=1&name=hongniuzy`
        - `https://dy.wangzhetq.asia/api.php/timming/index.html?enforce=1&name=aa`

2.  **每天执行一次 (`0 0 * * *`)**: 
    - 向以下 URL 发送 `curl` 请求：
        - `http://b.you.anneng.ggff.net/bbj/haibao.php?cmsname=maccms10&bbjtype=hot&codetype=php&filtercondi=doubanid&orderby=ASC&num=10&level=9`
        - `https://ane.anneng.ggff.net/bbj/haibao.php?cmsname=maccms10&bbjtype=hot&codetype=php&filtercondi=doubanid&orderby=ASC&num=10&level=9`

### 步骤

1.  **Checkout repository**: 使用 `actions/checkout@v2` 拉取仓库代码。
2.  **Access webpage every half hour**: 如果触发事件是半小时计划任务，则执行对应的 `curl` 命令。
3.  **Access webpage once a day**: 如果触发事件是每日计划任务，则执行对应的 `curl` 命令。

## 注意

请确保目标 URL 是可访问的，并且这些定时请求符合相关服务的使用条款。
