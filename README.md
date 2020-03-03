# interest

Interest，一个优雅的用于测试 WebSocket 应用的工具框架，旨在帮助开发者快速测试多端互动场景。

## 设计哲学

通过设计良好 WebSocket 服务端作为测试框架的指导者，每一端分别通过 puppeteer 开启浏览器实例收集信息。使用 ava 进行断言测试。

WebSocket -> As Director Server -> (ReceiveEvents | SendEvents)

Puppeteer -> As Client -> ConnectDirectorServer -> (ReceiveEvents | SendEvents)

## 关于互动应用

应用需遵循数据驱动的哲学。互动路线：

批量同步：DeltaModel -> GlobalAction -> Queue -> ReplaceModel -> UpdateView

动作同步：SemanticActionData -> Action(data) -> Queue -> UpdateModel -> UpdateView

行为撤销：ReverseAction -> ReplaceModel -> UpdateView
