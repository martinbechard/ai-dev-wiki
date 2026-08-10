---
title: "FastMCP 2.0 vs MCP Python SDK Server · Issue #1068 · modelcontextprotocol/python-sdk"
source: "https://github.com/modelcontextprotocol/python-sdk/issues/1068"
author:
  - "[[AaronLeon]]"
published: 2025-07-01
created: 2026-08-09
description: "Question HI all, I wanted to get clarity on the future of the Python SDK's server module. My current understanding is that MCP previously ad"
tags:
  - "clippings"
---
### Question

HI all, I wanted to get clarity on the future of the Python SDK's server module. My current understanding is that MCP previously adopted FastMCP into official Python SDK. Now that FastMCP 2.0 is out, what is the future of the Python SDK? Will they stay in sync or are they effectively forked? If they are forked, what is the level of maintainence and support for the Python SDK server?

### Additional Context

*No response*

---

## Comments

> **arjunaskykok** · 2025-07-02
>
> I'm not an Anthropic employee. But I have toyed around these two libraries. Here's my opinion:
>
> They have diverged and become totally separate projects. `python-sdk` is still being actively developed (you can check the commits). FastMCP 2 has "nicer" APIs (from UX perspective). It has documentation. The guy who developed it will launch a SaaS cloud to host MCP servers. So, he has an interest to maintain the FastMCP 2 library.
>
> But Anthropic is behind `python-sdk` and we can totally agree that Anthropic is a MUCH bigger name. They got resources to pour to this library.
>
> So, which one to choose? If you prefer big name, choose `python-sdk` but you have to dig into source code to figure out how to achieve certain things. If you prefer UX, choose FastMCP 2. They got better docs.
>
> Here's what I mean by UX:
>
> ```python
> # FastMCP 2
> client = Client(transport=StreamableHttpTransport("http://localhost:9000/mcp"),
>                 log_handler=log_handler)
>
> async def main():
>     async with client:
>         await client.call_tool("call_api_somewhere",
>                                progress_handler=progress_handler)
> ```
> ```python
> # python-sdk
> MCP_SERVER_URL = "http://127.0.0.1:9000/mcp/"
>
> async def run():
>     async with streamablehttp_client(MCP_SERVER_URL) as (read, write, _):
>         async with ClientSession(
>             read,
>             write,
>             logging_callback=log_handler
>         ) as session:
>             await session.initialize()
>
>             await session.call_tool("call_api_somewhere",
>                                     progress_callback=progress_handler)
> ```

> **davidshen84** · 2025-07-08
>
> Following up on [@arjunaskykok](https://github.com/arjunaskykok) 's comments. Are the two projects intending to diverge?
>
> On [https://github.com/jlowin/fastmcp](https://github.com/jlowin/fastmcp), it only says:
>
> > FastMCP 1.0 was incorporated into the [official MCP Python SDK](https://github.com/modelcontextprotocol/python-sdk) in 2024.
>
> So, I guess there's no plan/intention to incorporate v2? I'd hope either one of them make a clear statement that whether they will continue incorporate.

> **AaronLeon** · 2025-07-08
>
> Thanks [@arjunaskykok](https://github.com/arjunaskykok), all good points. I imagine the MCP Python SDK will of course have good parity with the evolving spec and that FastMCP may begin to include convenience features that are extraneous to the spec. I'll probably stick with the official SDK's Fast MCP 1.0 fork for now, but it would be good to get some insight from the Anthropic team on what the future is for the server module.

> **arjunaskykok** · 2025-07-08
>
> Lemme add some interesting things, [@AaronLeon](https://github.com/AaronLeon).
>
> Right now, we cannot send a non-string argument to a get prompt request with `python-sdk` because it violates specs. But using `FastMCP 2`, you can do that. So, you can say `python-sdk` is more orthodox while `FastMCP 2` is more liberal.
>
> Discussion:
> [modelcontextprotocol/modelcontextprotocol#879](https://github.com/modelcontextprotocol/modelcontextprotocol/discussions/879)
>
> Also, `FastMCP 2` is kinda more popular than `python-sdk`. In a tutorial article, the engineer used `FastMCP 2` to explain the concept of deploying an MCP server.
>
> [https://cloud.google.com/blog/topics/developers-practitioners/build-and-deploy-a-remote-mcp-server-to-google-cloud-run-in-under-10-minutes](https://cloud.google.com/blog/topics/developers-practitioners/build-and-deploy-a-remote-mcp-server-to-google-cloud-run-in-under-10-minutes)

> **tedivm** · 2025-07-08
>
> I have to say that for me, personally, I really regret starting a project with the `python-sdk` rather than `FastMCP v2`. There are features that work with FastMCP that absolutely fail with the `python-sdk` and the way FastMCP was just kind of shoved into `python-sdk` makes typing a bit of a mess (converting between FastMCP Tools and mcp\_types.Tool for example).
>
> If you look at the project pulse for both ([FastMCP Pulse](https://github.com/jlowin/fastmcp/pulse) versus [python-sdk](https://github.com/modelcontextprotocol/python-sdk/pulse)) you can see that FastMCP has almost three times as many closed pull requests over the last week and three times as many over the last month. Anthropic may be a bigger company, but they aren't moving nearly as quickly as FastMCP is.

> **codingjoe** · 2025-07-22
>
> Hi there 👋,
>
> I agree, the current situation is utterly confusing.
>
> For the next person googling this:
>
> **`fastmcp` is newer and simpler to work with.**
>
> Best
> Joe

> **dsp-ant** · 2025-09-19
>
> We talked with [@jlowin](https://github.com/jlowin) about this. We will work towards clarifying the situation in the 2.0 of the MCP SDK, but for now, this will remain. FastMCP v2 and the FastMCP inside the MCP SDK are sufficiently diverged. While this is unfortunate, we do not want to break people's code without sufficient heads up.
>
> So look out for the MCP SDK 2.0 hopefully coming end of the year which will likely rename fastmcp inside the SDK.

> **maxisbey** · 2025-12-08
>
> Closing as duplicate - consolidated into [#1732](https://github.com/modelcontextprotocol/python-sdk/issues/1732). The rename from FastMCP to MCPServer (or similar) will help clarify the distinction, and the issue now includes a goal to properly document the relationship between FastMCP v2 (external library) and the official SDK.