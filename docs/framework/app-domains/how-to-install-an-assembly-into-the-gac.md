---
title: "방법: 전역 어셈블리 캐시에 어셈블리 설치"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- global assembly cache, installing assemblies
- Global Assembly Cache tool
ms.assetid: a7e6f091-d02c-49ba-b736-7295cb0eb743
caps.latest.revision: "24"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 98dd4d1e75fc37820a1b1f4eccfa48f978772687
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a><span data-ttu-id="53af1-102">방법: 전역 어셈블리 캐시에 어셈블리 설치</span><span class="sxs-lookup"><span data-stu-id="53af1-102">How to: Install an Assembly into the Global Assembly Cache</span></span>
<span data-ttu-id="53af1-103">강력한 이름의 어셈블리를 전역 어셈블리 캐시(GAC)에 설치하는 방법은 두 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="53af1-103">There are two ways to install a strong-named assembly into the global assembly cache (GAC):</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="53af1-104">강력한 이름의 어셈블리만 GAC에 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53af1-104">Only strong-named assemblies can be installed into the GAC.</span></span> <span data-ttu-id="53af1-105">강력한 이름의 어셈블리를 만드는 방법에 대한 자세한 내용은 [방법: 강력한 이름으로 어셈블리 서명](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="53af1-105">For information about how to create a strong-named assembly, see [How to: Sign an Assembly with a Strong Name](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
-   <span data-ttu-id="53af1-106">[Windows Installer](http://msdn.microsoft.com/library/windows/desktop/cc185688.aspx) 사용.</span><span class="sxs-lookup"><span data-stu-id="53af1-106">Using [Windows Installer](http://msdn.microsoft.com/library/windows/desktop/cc185688.aspx).</span></span>  
  
     <span data-ttu-id="53af1-107">이렇게 하려면 Visual Studio 2012 및 Visual Studio 2013에서 InstallShield Limited Edition 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="53af1-107">You do this in Visual Studio 2012 and Visual Studio 2013 by creating an InstallShield Limited Edition Project.</span></span>  
  
     <span data-ttu-id="53af1-108">전역 어셈블리 캐시에 어셈블리를 추가하는 가장 일반적인 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="53af1-108">This is the recommended and most common way to add assemblies to the global assembly cache.</span></span> <span data-ttu-id="53af1-109">설치 관리자는 전역 어셈블리 캐시에서 어셈블리 참조 횟수를 제공하며, 다른 여러 가지 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="53af1-109">The installer provides reference counting of assemblies in the global assembly cache, plus other benefits.</span></span>  
  
-   <span data-ttu-id="53af1-110">[전역 어셈블리 캐시 도구(Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) 사용.</span><span class="sxs-lookup"><span data-stu-id="53af1-110">Using the [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md).</span></span>  
  
     <span data-ttu-id="53af1-111">Gacutil.exe를 사용하여 전역 어셈블리 캐시에 강력한 이름의 어셈블리를 추가하고 전역 어셈블리 캐시의 콘텐츠를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53af1-111">You can use Gacutil.exe to add strong-named assemblies to the global assembly cache and to view the contents of the global assembly cache.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="53af1-112">Gacutil.exe는 개발 용도로만 사용되며, 전역 어셈블리 캐시에 프로덕션 어셈블리를 설치하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="53af1-112">Gacutil.exe is only for development purposes and should not be used to install production assemblies into the global assembly cache.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="53af1-113">이전 버전의 .NET Framework에서는 Shfusion.dll Windows 셸 확장을 통해 파일 탐색기로 어셈블리를 끌어서 설치할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="53af1-113">In earlier versions of the .NET Framework, the Shfusion.dll Windows shell extension enabled you to install assemblies by dragging them in File Explorer.</span></span> <span data-ttu-id="53af1-114">[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]부터는 Shfusion.dll이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="53af1-114">Beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Shfusion.dll is obsolete.</span></span>  
  
### <a name="to-use-the-global-assembly-cache-tool-gacutilexe"></a><span data-ttu-id="53af1-115">전역 어셈블리 캐시 도구(Gacutil.exe)를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="53af1-115">To use the Global Assembly Cache tool (Gacutil.exe)</span></span>  
  
1.  <span data-ttu-id="53af1-116">명령 프롬프트에 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="53af1-116">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="53af1-117">**gacutil -i** \<*assembly name*></span><span class="sxs-lookup"><span data-stu-id="53af1-117">**gacutil -i** \<*assembly name*></span></span>  
  
     <span data-ttu-id="53af1-118">이 명령에서 *assembly name*은 전역 어셈블리 캐시에 설치할 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="53af1-118">In this command, *assembly name* is the name of the assembly to install in the global assembly cache.</span></span>  
  
 <span data-ttu-id="53af1-119">다음 예제는 파일 이름이 `hello.dll`인 어셈블리를 전역 어셈블리 캐시에 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="53af1-119">The following example installs an assembly with the file name `hello.dll` into the global assembly cache.</span></span>  
  
```  
gacutil -i hello.dll  
```  
  
 <span data-ttu-id="53af1-120">자세한 내용은 [전역 어셈블리 캐시 도구(Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="53af1-120">For more information, see [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md).</span></span>  
  
### <a name="to-use-an-installshield-limited-edition-project"></a><span data-ttu-id="53af1-121">InstallShield Limited Edition 프로젝트를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="53af1-121">To use an InstallShield Limited Edition Project</span></span>  
  
1.  <span data-ttu-id="53af1-122">솔루션에 대한 바로 가기 메뉴를 열고 **추가**, **새 프로젝트**를 차례로 선택하여 솔루션에 설치 및 배포 패키지를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="53af1-122">Add a setup and deployment package to your solution by opening the shortcut menu for your solution, and then choosing **Add**, **New Project**.</span></span>  
  
2.  <span data-ttu-id="53af1-123">**새 프로젝트 추가** 대화 상자의 **Installed** 폴더에서 **기타 프로젝트 형식**, **설치 및 배포**, **InstallShield Limited Edition**을 차례로 선택하고 프로젝트 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="53af1-123">In the **Add New Project** dialog box, in the **Installed** folder, choose **Other Project Types**,  **Setup and Deployment**, **InstallShield Limited Edition**, and give your project a name.</span></span> <span data-ttu-id="53af1-124">(메시지가 나타나면 InstallShield를 다운로드, 설치 및 활성화합니다.)</span><span class="sxs-lookup"><span data-stu-id="53af1-124">(If prompted, download, install, and activate InstallShield.)</span></span>  
  
3.  <span data-ttu-id="53af1-125">**솔루션 탐색기**에서 프로젝트 도우미를 사용하거나 **솔루션 탐색기**에서 번호가 매겨진 단계의 하위 단계를 선택하여 설치 및 배포 프로젝트의 일반 구성을 수행합니다. GAC에 어셈블리를 추가하지 않을 경우 수행하는 대로 설치를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="53af1-125">Perform the general configuration of your setup and deployment project either by using the Project Assistant in **Solution Explorer**, or by choosing the substeps of the numbered steps in the **Solution Explorer**.Configure your setup as you would if you were not adding assemblies to the GAC.</span></span>  
  
4.  <span data-ttu-id="53af1-126">GAC에 어셈블리를 추가하는 프로세스를 시작하려면 **솔루션 탐색기**의 **응용 프로그램 데이터 지정** 단계에서 **파일**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="53af1-126">To begin the process of adding an assembly to the GAC, choose **Files**, which is under the **Specify Application Data** step in **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="53af1-127">**대상 컴퓨터의 폴더** 창에서 **대상 컴퓨터**에 대한 바로 가기 메뉴를 열고 **미리 정의된 폴더 표시**, **[GlobalAssemblyCache]**를 차례로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="53af1-127">In the **Destination computer's folders** pane, open the shortcut menu for **Destination Computer**, and then choose **Show Predefined Folder**, **[GlobalAssemblyCache]**.</span></span>  
  
6.  <span data-ttu-id="53af1-128">전역 어셈블리 캐시에 설치하려는 어셈블리를 포함한 솔루션의 각 프로젝트에 대해 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="53af1-128">For each project in the solution that contains an assembly that you want to install in the global assembly cache:</span></span>  
  
    1.  <span data-ttu-id="53af1-129">**원본 컴퓨터의 폴더** 창에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="53af1-129">In the **Source computer's folders** pane, choose the project.</span></span>  
  
    2.  <span data-ttu-id="53af1-130">**대상 컴퓨터의 폴더** 창에서 **[GlobalAssemblyCache]**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="53af1-130">In the **Destination computer's folders** pane, choose **[GlobalAssemblyCache]**.</span></span>  
  
    3.  <span data-ttu-id="53af1-131">**원본 컴퓨터의 파일** 창에서 *<project_name>***의 기본 출력**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="53af1-131">In the **Source computer's files** pane, choose **Primary output from** *<project_name>*.</span></span>  
  
    4.  <span data-ttu-id="53af1-132">c 단계에서 파일을 **대상 컴퓨터의 파일** 창으로 끌거나 파일의 바로 가기 메뉴에서 **복사** 및 **붙여넣기** 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="53af1-132">Drag the file in step c to the **Destination computer's files** pane (or use the **Copy** and **Paste** commands from the file's shortcut menu).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53af1-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="53af1-133">See Also</span></span>  
 [<span data-ttu-id="53af1-134">어셈블리 및 전역 어셈블리 캐시 사용</span><span class="sxs-lookup"><span data-stu-id="53af1-134">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [<span data-ttu-id="53af1-135">방법: 전역 어셈블리 캐시에서 어셈블리 제거</span><span class="sxs-lookup"><span data-stu-id="53af1-135">How to: Remove an Assembly from the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/how-to-remove-an-assembly-from-the-gac.md)  
 [<span data-ttu-id="53af1-136">Gacutil.exe(전역 어셈블리 캐시 도구)</span><span class="sxs-lookup"><span data-stu-id="53af1-136">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../../../docs/framework/tools/gacutil-exe-gac-tool.md)  
 [<span data-ttu-id="53af1-137">방법: 강력한 이름으로 어셈블리 서명</span><span class="sxs-lookup"><span data-stu-id="53af1-137">How to: Sign an Assembly with a Strong Name</span></span>](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)  
 [<span data-ttu-id="53af1-138">Windows Installer 배포</span><span class="sxs-lookup"><span data-stu-id="53af1-138">Windows Installer Deployment</span></span>](http://msdn.microsoft.com/library/121be21b-b916-43e2-8f10-8b080516d2a0)
