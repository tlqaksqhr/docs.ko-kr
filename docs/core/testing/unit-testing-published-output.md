---
title: "dotnet vstest로 게시된 출력 테스트"
description: "dotnet vstest 명령을 사용하여 게시된 출력에 대해 테스트를 실행하는 방법을 알아봅니다."
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.topic: article
ms.prod: .net-core
ms.openlocfilehash: 6651d41d4d60194aec035107e3a65df6a5f70a51
ms.sourcegitcommit: 4a96a0fe9f87de70291245d71b76c7d1b15127ae
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/17/2017
---
# <a name="test-published-output-with-dotnet-vstest"></a><span data-ttu-id="bd174-103">dotnet vstest로 게시된 출력 테스트</span><span class="sxs-lookup"><span data-stu-id="bd174-103">Test published output with dotnet vstest</span></span>

<span data-ttu-id="bd174-104">`dotnet vstest` 명령을 사용하여 이미 게시된 출력에 대해 테스트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd174-104">You can run tests on already published output by using the `dotnet vstest` command.</span></span> <span data-ttu-id="bd174-105">이는 xUnit, MSTest 및 NUnit 테스트에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="bd174-105">This will work on xUnit, MSTest, and NUnit tests.</span></span> <span data-ttu-id="bd174-106">게시된 출력의 일부인 DLL 파일을 찾아 실행하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd174-106">Simply locate the DLL file that was part of your published output and run:</span></span>

```
dotnet vstest <MyPublishedTests>.dll
```

<span data-ttu-id="bd174-107">여기서 `<MyPublishedTests>`는 게시된 테스트 프로젝트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bd174-107">where `<MyPublishedTests>` is the name of your published test project.</span></span>

## <a name="example-of-running-tests-on-a-published-dll"></a><span data-ttu-id="bd174-108">게시된 DLL에 대한 테스트 실행의 예</span><span class="sxs-lookup"><span data-stu-id="bd174-108">Example of running tests on a published DLL</span></span>

```
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE]
> <span data-ttu-id="bd174-109">참고: 앱이 `netcoreapp` 이외의 프레임워크를 대상으로 하는 경우 프레임워크 플래그를 사용하여 대상 프레임워크를 전달함으로써 `dotnet vstest` 명령을 계속 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd174-109">Note: If your app is targeting a framework other than `netcoreapp` you can still run the `dotnet vstest` command by passing in the targeted framework with a framework flag.</span></span> <span data-ttu-id="bd174-110">예를 들어, `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="bd174-110">For example, `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`.</span></span> <span data-ttu-id="bd174-111">Visual Studio 2017 업데이트 5에서는 필요한 프레임워크가 자동으로 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd174-111">In Visual Studio 2017 Update 5 the desired framework is automatically detected.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd174-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd174-112">See also</span></span>
 [<span data-ttu-id="bd174-113">dotnet 테스트 및 xUnit을 사용한 단위 테스트</span><span class="sxs-lookup"><span data-stu-id="bd174-113">Unit Testing with dotnet test and xUnit</span></span>](unit-testing-with-dotnet-test.md)  
 [<span data-ttu-id="bd174-114">dotnet 테스트 및 MSTest를 사용한 단위 테스트</span><span class="sxs-lookup"><span data-stu-id="bd174-114">Unit Testing with dotnet test and MSTest</span></span>](unit-testing-with-mstest.md)  
