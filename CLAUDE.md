# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository status

This repository currently contains no source code — only tooling configuration (`.editorconfig`, `.gitignore`, `.mcp.json`). When code is added, update this file with build/test commands and the architecture overview.

## Tooling signals

The configuration files indicate this will be a **.NET / Visual Studio** project:

- `.gitignore` is the standard GitHub Visual Studio template (covers C#, F#, VB, ASP.NET, MSBuild, NuGet, ReSharper, NCrunch, etc.).
- `.editorconfig` enforces detailed C# / .NET coding conventions: 4-space indent, CRLF line endings, no final newline, language-keyword preferences (e.g. `int` over `Int32`), `this.`-qualification for properties/events but not fields/methods, and `for_non_interface_members` accessibility modifiers. Respect these when adding C# code.
- `.mcp.json` configures four MCP servers available to Claude Code in this repo:
  - **aspire** — .NET Aspire CLI agent (suggests the project will use .NET Aspire for distributed app orchestration).
  - **msdocs** — Microsoft Learn docs search/fetch.
  - **dxdocs** — DevExpress docs (suggests DevExpress UI components will be used).
  - **azure-devops-burning-box** — Azure DevOps integration scoped to the `burningbox` organization (work items, repos, pipelines, wiki, test plans). Source-of-truth for issue tracking and PRs lives in Azure DevOps, not GitHub.

## Working in this repo before code lands

- Don't invent build/test commands — there is no solution file yet. Ask the user which project type to scaffold (Aspire AppHost? ASP.NET? WinForms/WPF with DevExpress?) before generating boilerplate.
- When the first project is added, update this file with the actual `dotnet` build/test/run commands and a real architecture section.
- Azure DevOps work items and PRs are reachable via the `azure-devops-burning-box` MCP tools rather than `gh`.
