---
title: Windows 8에서 .NET Framework 2.0 대상 지정
description: 'F #을 사용 하는 경우에 이전 버전의.NET Framework를 대상으로 하는 방법을 알아봅니다.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 7c9bd8087da94a476105729b6f5b050fc66629a2
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="targeting-older-versions-of-net"></a><span data-ttu-id="b6f1f-103">이전 버전의 .NET 대상 지정</span><span class="sxs-lookup"><span data-stu-id="b6f1f-103">Targeting Older Versions of .NET</span></span>

> [!NOTE]
<span data-ttu-id="b6f1f-104">이 문서는 최신 Visual Studio와 함께 최신 상태로 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1f-104">This article is not up to date with the latest Visual Studio.</span></span>  <span data-ttu-id="b6f1f-105">업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1f-105">It will be updated.</span></span>

<span data-ttu-id="b6f1f-106">3.0 또는 3.5 F #에서 Visual Studio Windows 8.1 설치 된 경우 프로젝트는.NET Framework 2.0 대상으로 하려는 경우 다음과 같은 오류가 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1f-106">The following error might appear if you try to target the .NET Framework 2.0, 3.0, or 3.5 in an F# project when Visual Studio is installed on Windows 8.1:</span></span> 

```
This project requires the 2.0 F# runtime, but that runtime is not installed.
```

<span data-ttu-id="b6f1f-107">이 오류 조건 중 다음과 같은 상황에서 발생할 것으로 알려져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1f-107">This error is known to occur under the following combination of conditions:</span></span>


- <span data-ttu-id="b6f1f-108">Windows 8.1 Visual Studio를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1f-108">You installed Visual Studio on Windows 8.1.</span></span>
<br />

- <span data-ttu-id="b6f1f-109">Visual Studio를 설치 하기 전에.NET Framework 3.5를 사용 하도록 설정 하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1f-109">You didn’t enable the .NET Framework 3.5 before you installed Visual Studio.</span></span>
<br />

- <span data-ttu-id="b6f1f-110">프로젝트가는.NET Framework 2.0, 3.0 또는 3.5를 대상 으로합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1f-110">Your project targets the .NET Framework 2.0, 3.0, or 3.5.</span></span>
<br />

<span data-ttu-id="b6f1f-111">Visual Studio를 설치할 때 설치 된.NET Framework 버전을 검색 하 고.NET Framework 3.5 설치 되었고 사용 하는 경우에 F # Runtime 2.0을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1f-111">When you install Visual Studio, it detects the installed versions of the .NET Framework and installs the F# 2.0 Runtime only if the .NET Framework 3.5 is installed and enabled.</span></span>


## <a name="resolving-the-error"></a><span data-ttu-id="b6f1f-112">오류 해결</span><span class="sxs-lookup"><span data-stu-id="b6f1f-112">Resolving the Error</span></span>
<span data-ttu-id="b6f1f-113">이 오류를 해결 하려면 최신 버전의.NET Framework를 대상 중 하나를 할 수 있습니다 또는 Windows 8.1.NET Framework 3.5를 사용 하도록 설정 하 고 다음을 사용한 Visual Studio에 대 한 설치 프로그램을 실행 하 여 F # 2.0 런타임을 설치할 수 있습니다는 **복구** 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1f-113">To resolve this error, you can either target a newer version of the .NET Framework, or you can enable the .NET Framework 3.5 on Windows 8.1 and then install the F# 2.0 runtime by running the setup program for Visual Studio with the **Repair** option.</span></span>


#### <a name="to-enable-the-net-framework-35-on-windows-81"></a><span data-ttu-id="b6f1f-114">Windows 8.1.NET Framework 3.5를 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="b6f1f-114">To enable the .NET Framework 3.5 on Windows 8.1</span></span>

1. <span data-ttu-id="b6f1f-115">에 **시작** 화면에서 입력 하기 시작 **제어판**합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1f-115">On the **Start** screen, start to enter **Control Panel**.</span></span>
<br />  <span data-ttu-id="b6f1f-116">해당 이름을 입력 하면는 **제어판** 아이콘 아래에 표시는 **앱** 제목입니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1f-116">As you enter that name, the **Control Panel** icon appears under the **Apps** heading.</span></span>
<br />

2. <span data-ttu-id="b6f1f-117">선택 된 **제어판** 아이콘을 선택는 **프로그램** 아이콘을 선택한 후는 **Windows 기능 설정 또는 해제** 링크 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1f-117">Choose the **Control Panel** icon, choose the **Programs** icon, and then choose the **Turn Windows features on or off** link.</span></span>
<br />

3. <span data-ttu-id="b6f1f-118">다음 사항을 확인는 **.NET Framework 3.5 (.NET 2.0 및 3.0 포함)** 확인란을 선택한 다음 선택는 **확인** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1f-118">Make sure that the **.NET Framework 3.5 (includes .NET 2.0 and 3.0)** check box is selected, and then choose the **OK** button.</span></span>
<br />  <span data-ttu-id="b6f1f-119">.NET Framework의 선택적 구성 요소에 대 한 모든 자식 노드에 대 한 확인란을 선택 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1f-119">You don’t need to select the check boxes for any child nodes for optional components of the .NET Framework.</span></span>
<br />  <span data-ttu-id="b6f1f-120">.NET Framework 3.5은 이미 되지 않은 경우에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1f-120">The .NET Framework 3.5 is enabled if it wasn't already.</span></span>
<br />


#### <a name="to-install-the-f-20-runtime"></a><span data-ttu-id="b6f1f-121">F # 2.0 런타임을 설치 하려면</span><span class="sxs-lookup"><span data-stu-id="b6f1f-121">To install the F# 2.0 runtime</span></span>

1. <span data-ttu-id="b6f1f-122">제어판에서 선택 된 **프로그램** 링크를 선택한 다음 선택는 **프로그램 및 기능** 링크 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1f-122">In the Control Panel, choose the **Programs** link, and then choose the **Programs and Features** link.</span></span>
<br />

2. <span data-ttu-id="b6f1f-123">설치 된 프로그램 목록에서 설치 하 고 다음을 선택 하는 Visual Studio의 버전을 선택 된 **변경** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1f-123">In the list of installed programs, choose the edition of Visual Studio that you installed, and then choose the **Change** button.</span></span>
<br />

3. <span data-ttu-id="b6f1f-124">설치 프로그램이 시작 된 후 선택 된 **복구** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1f-124">After setup starts, choose the **Repair** button.</span></span>
<br />  <span data-ttu-id="b6f1f-125">자세한 내용은 참조 [Visual Studio 설치](https://msdn.microsoft.com/library/e2h7fzkw.aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="b6f1f-125">For more information, see [Installing Visual Studio](https://msdn.microsoft.com/library/e2h7fzkw.aspx).</span></span>
<br />
## <a name="see-also"></a><span data-ttu-id="b6f1f-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b6f1f-126">See Also</span></span>
[<span data-ttu-id="b6f1f-127">Visual F#</span><span class="sxs-lookup"><span data-stu-id="b6f1f-127">Visual F#</span></span>](../index.md)
