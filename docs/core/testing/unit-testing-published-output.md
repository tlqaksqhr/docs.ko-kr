---
title: "Dotnet vstest 게시 된 출력을 테스트"
description: "Dotnet vstest 명령 사용 하 여 게시 된 출력에서 테스트를 실행 하는 방법에 알아봅니다."
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 3965e4ca-75b8-4969-b3af-ca993c397a15
ms.openlocfilehash: 217787d41a9da6000941ded6caaa4f44d124644b
ms.sourcegitcommit: 8a4f8e6a7f1341764abcd188a332cc28d1e2d8ec
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="test-published-output-with-dotnet-vstest"></a><span data-ttu-id="1b8f5-103">Dotnet vstest 게시 된 출력을 테스트</span><span class="sxs-lookup"><span data-stu-id="1b8f5-103">Test published output with dotnet vstest</span></span>

<span data-ttu-id="1b8f5-104">이미 게시 된 출력에 사용 하 여 테스트를 실행할 수는 `dotnet vstest` 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="1b8f5-104">You can run tests on already published output by using the `dotnet vstest` command.</span></span> <span data-ttu-id="1b8f5-105">이 테스트 NUnit, xUnit 및 MSTest 등에 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b8f5-105">This will work on xUnit, MSTest, and NUnit tests.</span></span> <span data-ttu-id="1b8f5-106">게시 된 출력의 일부 였던 DLL 파일을 찾아 실행 하기만 하면 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b8f5-106">Simply locate the DLL file that was part of your published output and run:</span></span>
```
dotnet vstest <MyPublishedTests>.dll
```
<span data-ttu-id="1b8f5-107">여기서 `<MyPublishedTests>` 게시 된 테스트 프로젝트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1b8f5-107">where `<MyPublishedTests>` is the name of your published test project.</span></span>

### <a name="example-of-running-tests-on-a-published-dll"></a><span data-ttu-id="1b8f5-108">게시 된 DLL에 대 한 테스트 실행의 예</span><span class="sxs-lookup"><span data-stu-id="1b8f5-108">Example of running tests on a published DLL</span></span>

```
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE] <span data-ttu-id="1b8f5-109">참고: 응용 프로그램 대상으로 하는 프레임 워크 이외의 경우 `netcoreapp` 계속 실행할 수 있습니다는 `dotnet vstest` 명령을 실행 하 여 프레임 워크 플래그로 대상된 프레임 워크를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b8f5-109">Note: If your app is targeting a framework other than `netcoreapp` you can still run the `dotnet vstest` command by passing in the targeted framework with a framework flag.</span></span> <span data-ttu-id="1b8f5-110">예를 들어, `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1b8f5-110">For example, `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`.</span></span> <span data-ttu-id="1b8f5-111">Visual Studio 2017 업데이트 5에 원하는 프레임 워크를 자동으로 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b8f5-111">In Visual Studio 2017 Update 5 the desired framework is automatically detected.</span></span>

### <a name="related-topics"></a><span data-ttu-id="1b8f5-112">관련 항목</span><span class="sxs-lookup"><span data-stu-id="1b8f5-112">Related topics</span></span>
- [<span data-ttu-id="1b8f5-113">Dotnet 테스트, xUnit와 유닛 테스트</span><span class="sxs-lookup"><span data-stu-id="1b8f5-113">Unit Testing with dotnet test and xUnit</span></span>](unit-testing-with-dotnet-test.md)
- [<span data-ttu-id="1b8f5-114">MSTest dotnet 테스트와 단위 테스트</span><span class="sxs-lookup"><span data-stu-id="1b8f5-114">Unit Testing with dotnet test and MSTest</span></span>](unit-testing-with-mstest.md)
