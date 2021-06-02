# enterprice 企業系統
本目錄存放之前上班公司所做的 ERP 系統的重現。

### 權則聲明
本作品概念或許由之前上班的公司獲得或啟發，但是，概念沒有專利權。我的重現是在回想的印象基礎之上重新創作，用意只在於展示以我的智慧能力能怎麼樣做出同樣的作品。

## 基本配置
- 工具
  - .NET Core
  - Razor Pages
  - SignalR
  - Docker
  - docker-compose
  - skaffold

## 系統情境
相較於本系統，有個外站為大宗商務平台。外站提供限流式網路服務，即限制存取次數的 API ；藉由 API ，外站提供主流商務內容如上架商品、存貨更新、代營銷數據等資訊服務。

本系統為一套企業資源規劃系統，與外站介接資源，並滿足進、銷、存、管等四項主流功能。

## 架構
| 配置 | 功能 | 類型 | 技術工具 |
| ---- | ---- | ---- | -------- |
| 前端 | 庫存報告<br>銷售紀錄<br>採購規劃<br>管理資訊 | 網站服務 | [.NET 5.0 SDK 5.0.300](https://dotnet.microsoft.com/download/dotnet/5.0)<br>[C# 9.0](https://docs.microsoft.com/en-us/dotnet/csharp/)<br>[Razor Pages](https://docs.microsoft.com/en-us/aspnet/core/razor-pages/?view=aspnetcore-5.0&tabs=visual-studio)<br>[Docker](https://www.docker.com/get-started) |
| 外站 | 限流式網路服務 | API | [Spring Boot](https://spring.io/projects/spring-boot)<br>[Docker](https://www.docker.com/get-started) |
| 外來資訊端 | 外站資源介接 | 服務 | [ProtoBuf](https://developers.google.com/protocol-buffers)<br>[gRPC](https://grpc.io/docs/)<br>[Spring Boot](https://spring.io/projects/spring-boot)<br>[Docker](https://www.docker.com/get-started) |
| 後端 | 商業邏輯管控<br>系統模式 | 服務 | [Erlang](https://erlang.org/doc/search/)<br>[OTP](https://github.com/Erlang/OTP)<br>[`rpc`](https://erlang.org/doc/man/rpc.html)<br>[Docker](https://www.docker.com/get-started) |
