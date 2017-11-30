---
title: "방법: 설치 된.NET Framework 보안 업데이트 및 핫픽스를 결정 합니다."
description: "컴퓨터에 설치 된.NET Framework 보안 업데이트 및 핫픽스를 결정 하는 방법에 알아봅니다."
ms.date: 11/21/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- updates, determining for .NET Framework
- .NET Framework, determining updates
ms.assetid: 53c7b5f7-d47a-402a-b194-7244a696a88b
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c35705470a8e1b553eca2ca0c68d3b8b9b3f6fa6
ms.sourcegitcommit: a3ba258f7a8cab5c6d19a3743dd95e904ecebc44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/27/2017
---
# <a name="how-to-determine-which-net-framework-security-updates-and-hotfixes-are-installed"></a><span data-ttu-id="f0066-103">방법: 설치 된.NET Framework 보안 업데이트 및 핫픽스를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0066-103">How to: Determine which .NET Framework security updates and hotfixes are installed</span></span>

<span data-ttu-id="f0066-104">이 문서에서는.NET Framework 보안 업데이트 확인 하는 방법 및 핫픽스가 컴퓨터에 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0066-104">This article shows you how to find out which .NET Framework security updates and hotfixes are installed on a computer.</span></span>

> [!NOTE]
> <span data-ttu-id="f0066-105">이 문서에 표시 된 모든 기술 관리자 권한이 있는 계정이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0066-105">All the techniques shown in this article require an account with administrative privileges.</span></span>

## <a name="to-find-installed-updates-using-the-registry"></a><span data-ttu-id="f0066-106">찾을 레지스트리를 사용 하 여 업데이트 설치</span><span class="sxs-lookup"><span data-stu-id="f0066-106">To find installed updates using the registry</span></span>

<span data-ttu-id="f0066-107">설치 된 보안 업데이트와 핫픽스는 컴퓨터에 설치 된.NET Framework의 각 버전에 대 한 Windows 레지스트리에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0066-107">The installed security updates and hotfixes for each version of the .NET Framework installed on a computer are listed in the Windows registry.</span></span> <span data-ttu-id="f0066-108">레지스트리 편집기를 사용할 수 있습니다 (*regedit.exe*)이이 정보를 보려면 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="f0066-108">You can use the Registry Editor (*regedit.exe*) program to view this information.</span></span>

1. <span data-ttu-id="f0066-109">**regedit.exe** 프로그램을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f0066-109">Open the program **regedit.exe**.</span></span> <span data-ttu-id="f0066-110">Windows 8 이상 버전에서 마우스 오른쪽 단추로 클릭 **시작** ![Windows 로고](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo")을 선택한 후 **실행**합니다.</span><span class="sxs-lookup"><span data-stu-id="f0066-110">In Windows 8 and later versions, right-click **Start** ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo"), then select **Run**.</span></span> <span data-ttu-id="f0066-111">에 **열려** 상자에 입력 **regedit** 선택 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="f0066-111">In the **Open** box, enter **regedit** and select **OK**.</span></span>

2. <span data-ttu-id="f0066-112">레지스트리 편집기에서 다음 하위 키를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f0066-112">In the Registry Editor, open the following subkey:</span></span>

     `HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates`

     <span data-ttu-id="f0066-113">설치된 업데이트가 적용되는 .NET Framework 버전을 식별하는 하위 키 아래에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0066-113">The installed updates are listed under subkeys that identify the .NET Framework version they apply to.</span></span> <span data-ttu-id="f0066-114">각 업데이트는 KB(기술 자료) 번호로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0066-114">Each update is identified by a Knowledge Base (KB) number.</span></span>

<span data-ttu-id="f0066-115">레지스트리 편집기에서 .NET Framework 버전과 각 버전에 대해 설치된 업데이트는 서로 다른 하위 키에 저장되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0066-115">In the Registry Editor, the .NET Framework versions and installed updates for each version are stored in different subkeys.</span></span> <span data-ttu-id="f0066-116">설치 된 버전 번호를 검색 하는 방법에 대 한 정보를 참조 하십시오. [하는 방법: 설치 된.NET Framework 버전 결정](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f0066-116">For information about detecting the installed version numbers, see [How to: Determine which .NET Framework versions are installed](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span></span>

## <a name="to-find-installed-updates-by-querying-the-registry-in-code"></a><span data-ttu-id="f0066-117">코드로 레지스트리를에서 쿼리하여 설치 된 업데이트를 찾으려면</span><span class="sxs-lookup"><span data-stu-id="f0066-117">To find installed updates by querying the registry in code</span></span>

<span data-ttu-id="f0066-118">다음 예제에는.NET Framework 보안 업데이트와 컴퓨터에 설치 된 핫픽스를 프로그래밍 방식으로 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0066-118">The following example programmatically determines the .NET Framework security updates and hotfixes that are installed on a computer:</span></span>

[!code-csharp[ListUpdates](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs)]
[!code-vb[ListUpdates](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb)]

<span data-ttu-id="f0066-119">이 예제에서는 다음과 유사한 출력을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0066-119">The example produces an output that's similar to the following one:</span></span>

```console
Microsoft .NET Framework 4 Client Profile
  KB2468871
  KB2468871v2
  KB2478063
  KB2533523
  KB2544514
  KB2600211
  KB2600217
Microsoft .NET Framework 4 Extended
  KB2468871
  KB2468871v2
  KB2478063
  KB2533523
  KB2544514
  KB2600211
  KB2600217
```

## <a name="to-find-installed-updates-by-querying-the-registry-in-powershell"></a><span data-ttu-id="f0066-120">PowerShell에서 레지스트리를 쿼리하여 설치 된 업데이트를 찾으려면</span><span class="sxs-lookup"><span data-stu-id="f0066-120">To find installed updates by querying the registry in PowerShell</span></span>

<span data-ttu-id="f0066-121">다음 예제에서는.NET Framework 보안 업데이트 및 PowerShell을 사용 하는 컴퓨터에 설치 된 핫픽스를 확인 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f0066-121">The following example shows how to determine the .NET Framework security updates and hotfixes that are installed on a computer using PowerShell:</span></span>

```powershell
 Get-ChildItem "HKLM:SOFTWARE\Wow6432Node\Microsoft\Updates\*" -Recurse | Where-Object {$_.name -like
 "*.NET Framework*"}
```

<span data-ttu-id="f0066-122">이 예제에서는 다음과 유사한 출력을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0066-122">The example produces an output that's similar to the following one:</span></span>

```console
    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates\Microsoft .NET Framework 4 Client Profile


Name                           Property
----                           --------
KB2468871                      ThisVersionInstalled : Y
KB2468871v2                    ThisVersionInstalled : Y
KB2478063                      ThisVersionInstalled : Y
KB2533523                      ThisVersionInstalled : Y
KB2544514                      ThisVersionInstalled : Y
KB2600211                      ThisVersionInstalled : Y
KB2600217                      ThisVersionInstalled : Y


    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates\Microsoft .NET Framework 4 Extended


Name                           Property
----                           --------
KB2468871                      ThisVersionInstalled : Y
KB2468871v2                    ThisVersionInstalled : Y
KB2478063                      ThisVersionInstalled : Y
KB2533523                      ThisVersionInstalled : Y
KB2544514                      ThisVersionInstalled : Y
KB2600211                      ThisVersionInstalled : Y
KB2600217                      ThisVersionInstalled : Y
```

## <a name="see-also"></a><span data-ttu-id="f0066-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0066-123">See also</span></span>

[<span data-ttu-id="f0066-124">방법: 설치 된.NET Framework 버전 확인</span><span class="sxs-lookup"><span data-stu-id="f0066-124">How to: Determine which .NET Framework versions are installed</span></span>](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)  
[<span data-ttu-id="f0066-125">개발자를 위한.NET Framework를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0066-125">Install the .NET Framework for developers</span></span>](../../../docs/framework/install/guide-for-developers.md)  
[<span data-ttu-id="f0066-126">버전 및 종속성</span><span class="sxs-lookup"><span data-stu-id="f0066-126">Versions and dependencies</span></span>](../../../docs/framework/migration-guide/versions-and-dependencies.md)
