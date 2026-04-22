[小米泰国AD创建测试 - 飞书云文档](https://bluefocus.feishu.cn/wiki/BJA4wBBGZiw05XkG0TictilCnwd) 
[小米奥地利创建AD测试 - 飞书云文档](https://bluefocus.feishu.cn/wiki/UtqhwZ9FXiVNEMkFLXgcWEhZnud) 
[荣耀创建AD测试 - 飞书云文档](https://bluefocus.feishu.cn/wiki/ZwZtwCkWAiP8MHknMCBcn6brnHc)
[小米TW-4月投放广告创建 - 飞书云文档](https://bluefocus.feishu.cn/wiki/Wu04wYCtti6d1KkRgjFc8F1GnTh?sheet=g5bfLR)

```
投放目的：品牌广告
一级行业分类：电商
二级行业分类：电子产品-小米手机
投放媒体：Meta、Google、TikTok
投放国家：泰国
投放开始月份：2026-04
投放结束月份：2026-10
总预算：10,000,000 美元
最关注的广告指标：CTR

投放目的：品牌广告
一级行业分类：电商
二级行业分类：电子产品-小米手机
投放媒体：Meta、Google、TikTok
投放国家：奥地利
投放开始月份：2026-04
投放结束月份：2026-10
总预算：10,000,000 美元
最关注的广告指标：CTR

投放目的：品牌广告
一级行业分类：电商
二级行业分类：电子产品-荣耀手机
投放媒体：Meta、Google、TikTok
投放国家：泰国
投放开始月份：2026-04
投放结束月份：2026-10
总预算：10,000,000 美元
最关注的广告指标：CTR
```

```
ea74e6e1-98df-49d8-9953-059d7b4de3ba
```

```json
{ 
	"code": 0, 
	"status": "success", 
	"message": "", 
	"message_en": "", 
	"data": { 
		"id": "a1b2c3d4-e5f6-7890-abcd-000000000004", 
		"appName": "adswin_x", 
		"userId": "2949", 
		"state": { 
			"allocated": true, 
			"user:user_id": "2949", 
			"session_id": "a1b2c3d4-e5f6-7890-abcd-000000000004" 
		}, 
		"events": [], 
		"lastUpdateTime": 1773107459 
	} 
}
```

```
2026-04-17 18:03:53,762 INFO sqlalchemy.engine.Engine [cached since 6232s ago] {'pk_1': <AppNameEnum.adswin_x: 'adswin_x'>, 'pk_2': '2949'}

2026-04-17 18:10:39,711
```

```
 https://www.youtube.com/channel/UCTE4_3WBd1DhrlMrJOGA8UQ
 https://www.youtube.com/@mediastorm6801
 https://www.instagram.com/salmaasif1985/
```

```python
# ── AFC 诊断 monkey-patch ──────────────────────────────────────────────
# 在 ADK 的 LLM 调用前注入 AFC 配置诊断日志，排查 ads_agent 返回空字符串问题。
# 问题排查完成后应移除此 patch。

try:
    from google.adk.models import google_llm as _glmod

    _original_generate_content_async = _glmod.Gemini.generate_content_async

    async def _patched_generate_content_async(self, llm_request, stream=True):
        if llm_request.config:
            afc_cfg = llm_request.config.automatic_function_calling
            tools = llm_request.config.tools or []
            tools_count = len(tools)
            has_func_decls = any(
                hasattr(t, 'function_declarations') and t.function_declarations
                for t in tools
                if hasattr(t, 'function_declarations')
            )
            logger.info(
                'AFC DEBUG: disable=%s, max_remote_calls=%s, tools_count=%d, has_func_decls=%s',
                afc_cfg.disable if afc_cfg else None,
                afc_cfg.maximum_remote_calls if afc_cfg else None,
                tools_count,
                has_func_decls,
            )

        async for item in _original_generate_content_async(self, llm_request, stream=stream):
            yield item

    _glmod.Gemini.generate_content_async = _patched_generate_content_async
    logger.info("AFC 诊断 monkey-patch 已注入")
except Exception as e:
    logger.warning(f"AFC 诊断 monkey-patch 注入失败: {e}")

# ── AFC 诊断 monkey-patch END ──────────────────────────────────────────
```

```
1. adk 关于 skill 的支持（包括版本升级、多服务器部署、热加载、防注入等等）
2. adk 关于 memory 的支持 （memory service 的选取）
```
