---
title: ".NET Core CLI 테스트 통신 프로토콜 | Microsoft 문서"
description: ".NET Core CLI 테스트 통신 프로토콜"
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 88cba792-3640-41de-b55d-00f575e9d5e2
translationtype: Human Translation
ms.sourcegitcommit: 2ad428dcda9ef213a8487c35a48b33929259abba
ms.openlocfilehash: 3315c8b0d2033643d81a7b14f31d6e8aed6a15b1

---

#<a name="net-core-cli-test-communication-protocol"></a>.NET Core CLI 테스트 통신 프로토콜

> [!WARNING]
> 이 항목은 .NET Core Tools Preview 2에 적용됩니다. Visual Studio 2017 RC - .NET Core Tools Preview 4 설명서의 경우 [.NET Core 명령줄 인터페이스 도구(Tooling Preview 4)](../preview3/tools/index.md) 섹션을 참조하세요.

## <a name="introduction"></a>소개
포트를 dotnet 테스트로 전달할 때마다 디자인 타임에서 명령이 실행됩니다. 즉, `dotnet test`는 TCP를 사용하여 해당 포트에 연결한 후 설정된 메시지 집합을 해당 포트에 연결된 다른 것과 교환합니다. 이 경우 Runner 역시 `dotnet test`가 통신에 사용할 새 포트를 수신합니다. Runner 역시 `dotnet test`와의 통신에 TCP를 사용하는 이유는, 디자인 모드에서는 결과를 콘솔에만 출력하는 것으로 충분하지 않기 때문입니다. 명령은 또한 테스트 실행 결과를 포함하는 어댑터 구조 메시지를 전송해야 합니다.

### <a name="communication-protocol-at-design-time"></a>디자인 타임의 통신 프로토콜

1. 디자인 타임 동안 `dotnet test`는 시작할 때 포트에 연결되므로, 어댑터는 해당 포트에서 수신 대기해야 하며 그러지 않으면 `dotnet test`가 실패합니다. 이와 같이 하는 이유는 `dotnet test`가 실행되어 Runner에 대한 포트를 가져오려고 시도하기 전에 어댑터가 바인딩하고 수신 대기하여 필요한 모든 포트를 예약할 수 있도록 하려는 것입니다.
2. `dotnet test`는 시작되면 TestSession.Connected 메시지를 어댑터에 전송하여, 메시지를 수신할 준비가 되었음을 나타냅니다.
3. 선택적인 [버전 검사](https://github.com/dotnet/cli/blob/rel/1.0.0-preview2/src/Microsoft.Extensions.Testing.Abstractions/Messages/ProtocolVersionMessage.cs) 메시지를 프로토콜의 어댑터 버전과 함께 전송할 수 있습니다. `dotnet test`는 지원하는 프로토콜의 버전을 다시 전송합니다.

모든 메시지는 [Message.cs](https://github.com/dotnet/cli/blob/rel/1.0.0-preview2/src/Microsoft.Extensions.Testing.Abstractions/Messages/Message.cs)에 설명된 형식입니다. 각 메시지의 페이로드 형식은 프로토콜의 설명에서 정보를 직렬화/역직렬화하는 데 사용되는 클래스에 대한 링크에 설명되어 있습니다.

#### <a name="test-execution"></a>테스트 실행
![테스트 실행](./media/test-protocol/dotnet-test-execute.png)

1. 선택적인 버전 확인 후 어댑터는 내부에서 실행할 [테스트](https://github.com/dotnet/cli/blob/rel/1.0.0-preview2/src/Microsoft.Extensions.Testing.Abstractions/Messages/RunTestsMessage.cs)와 함께 TestExecution.GetTestRunnerProcessStartInfo를 보냅니다. `dotnet test`는 어댑터가 Runner를 시작하기 위해 사용할 수 있는 [TestStartInfo](https://github.com/dotnet/cli/blob/rel/1.0.0-preview2/src/dotnet/commands/dotnet-test/TestStartInfo.cs) 페이로드에 파일 이름과 인수를 포함하여 다시 전송합니다. 과거에는 실행할 테스트의 목록을 인수의 일부로 전송했지만, 일부 테스트 프로젝트에서 명령줄 크기 제한을 실제로 초과했습니다.
  1. 인수의 일부로서 Runner가 연결해야 할 포트를 전송합니다. 그리고 계속 진행하여 테스트를 실행하는 대신 테스트 실행을 위해 Runner가 포트에 연결되어 명령을 기다려야 함을 나타내는 --wait-command 플래그도 전송합니다.
2. 이 시점에서 어댑터가 Runner를 시작(그리고 선택한 경우 디버깅을 위해 Runner에 연결)할 수 있습니다.
3. Runner는 시작되면, 명령을 수신할 준비가 되었음을 나타내는 TestRunner.WaitCommand 메시지를 `dotnet test`에 전송합니다. 그러면 `dotnet test`는 실행할 [테스트](https://github.com/dotnet/cli/blob/rel/1.0.0-preview2/src/Microsoft.Extensions.Testing.Abstractions/Messages/RunTestsMessage.cs) 목록과 함께 TestRunner.Execute를 전송합니다. 여기서는 위에서 설명한 명령줄 크기 제한이 무시됩니다.
4. 그런 다음 Runner는 내부에 포함된 [테스트](https://github.com/dotnet/cli/blob/rel/1.0.0-preview2/src/Microsoft.Extensions.Testing.Abstractions/Test.cs)정보로 시작될 때 각 테스트에 대한 TestExecution.TestStarted를 `dotnet test`에 전송하고 dotnet test는 이를 어댑터에 전달합니다.
5. 또한 Runner는 테스트의 [개별 결과](https://github.com/dotnet/cli/blob/rel/1.0.0-preview2/src/Microsoft.Extensions.Testing.Abstractions/TestResult.cs)와 함께 각 테스트에 대한 TestExecution.TestResult를 `dotnet test`에 전송하고 dotnet test는 이를 어댑터에 전달합니다.
6. 모든 테스트가 끝나면 Runner는 TestRunner.Completed 메시지를 `dotnet test`에 전송합니다. 그러면 dotnet test는 이를 TestExecution.Completed로 어댑터에 전송합니다.
7. 어댑터는 작업이 완료되면 `dotnet test`가 종료되도록 하는 TestSession.Terminate를 `dotnet test`에 전송합니다.

#### <a name="test-discovery"></a>테스트 검색
![테스트 검색](./media/test-protocol/dotnet-test-discover.png)

1. 선택 사항인 버전 확인 후 어댑터는 TestDiscovery.Start 메시지를 전송합니다. 이 경우 어댑터를 프로세스에 연결할 필요가 없으므로 `dotnet test`는 Runner 자체를 시작합니다. 또한 Runner에 전달할 긴 인수 목록이 없으므로 Runner에 전달하기 위한 --wait-command 플래그가 없습니다. `dotnet test`는 Runner에 --list 인수만 전달합니다. 즉, Runner는 테스트를 실행하지 않고 단지 나열만 합니다.
2. 그러면 Runner는 발견하는 각 [테스트](https://github.com/dotnet/cli/blob/rel/1.0.0-preview2/src/Microsoft.Extensions.Testing.Abstractions/Test.cs)에 대해 TestDiscovery.TestFound를 `dotnet test`전송하고 dotnet test는 이를 어댑터에 전달합니다.
3. 모든 테스트가 검색되면 Runner는 TestRunner.Completed 메시지를 `dotnet test`에 전송합니다. 그러면 dotnet test는 이를 TestDiscovery.Completed로 어댑터에 전송합니다.
4. 어댑터는 작업이 완료되면 `dotnet test`가 종료되도록 하는 TestSession.Terminate를 `dotnet test`에 전송합니다.



<!--HONumber=Jan17_HO3-->


