---
title: "방법: 도구 상자 항목 선택 대화 상자에 컨트롤 표시"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- global assembly cache [Windows Forms], Choose Toolbox Items dialog box
- AssemblyFoldersEx [Windows Forms], Choose Toolbox Items dialog box
- controls [Windows Forms], display in Choose Toolbox Items dialog box
- assembly folder registration [Windows Forms], Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box [Windows Forms], display control
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1323ffbd59a14d19d1161e0718fad083bcc37a89
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a><span data-ttu-id="97b0e-102">방법: 도구 상자 항목 선택 대화 상자에 컨트롤 표시</span><span class="sxs-lookup"><span data-stu-id="97b0e-102">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>
<span data-ttu-id="97b0e-103">개발 하 고 컨트롤을 배포 하면 이러한 컨트롤에 표시 되도록 할 수 있습니다는 **도구 상자 항목 선택** 마우스 오른쪽 단추로 클릭할 때 표시 되는 대화 상자는 **도구 상자** 선택  **항목 선택**합니다.</span><span class="sxs-lookup"><span data-stu-id="97b0e-103">As you develop and distribute controls, you may want those controls to appear in the **Choose Toolbox Items** dialog box, which is displayed when you right-click the **Toolbox** and select **Choose Items**.</span></span> <span data-ttu-id="97b0e-104">AssemblyFoldersEx 등록 절차를 사용 하 여이 대화 상자에 표시할 컨트롤을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97b0e-104">You can enable your control to appear in this dialog box by using the AssemblyFoldersEx registration procedure.</span></span>  
  
### <a name="to-display-your-control-in-the-choose-toolbox-items-dialog-box"></a><span data-ttu-id="97b0e-105">도구 상자 항목 선택 대화 상자에서 컨트롤을 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="97b0e-105">To display your control in the Choose Toolbox Items dialog box</span></span>  
  
-   <span data-ttu-id="97b0e-106">컨트롤 어셈블리를 전역 어셈블리 캐시에 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="97b0e-106">Install your control assembly to the global assembly cache.</span></span> <span data-ttu-id="97b0e-107">자세한 내용은 참조 [하는 방법: 전역 어셈블리 캐시에 어셈블리 설치](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)</span><span class="sxs-lookup"><span data-stu-id="97b0e-107">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)</span></span>  
  
     <span data-ttu-id="97b0e-108">또는</span><span class="sxs-lookup"><span data-stu-id="97b0e-108">-or-</span></span>  
  
-   <span data-ttu-id="97b0e-109">AssemblyFoldersEx 등록 절차를 사용 하 여 컨트롤 및 해당 연결 된 디자인 타임 어셈블리를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="97b0e-109">Register your control and its associated design-time assemblies by using the AssemblyFoldersEx registration procedure.</span></span> <span data-ttu-id="97b0e-110">AssemblyFoldersEx 공급 업체 원하는 프레임 워크의 각 버전에 대 한 경로 저장 하는 레지스트리 위치는입니다.</span><span class="sxs-lookup"><span data-stu-id="97b0e-110">AssemblyFoldersEx is a registry location where third-party vendors store paths for each version of the framework that they support.</span></span> <span data-ttu-id="97b0e-111">참조 어셈블리를 찾는이 레지스트리 위치에 디자인 타임 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="97b0e-111">Design-time resolution can look in this registry location to find reference assemblies.</span></span> <span data-ttu-id="97b0e-112">레지스트리 스크립트를 도구 상자에 표시할 컨트롤을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97b0e-112">The registry script can specify the controls you want to appear in the Toolbox.</span></span> <span data-ttu-id="97b0e-113">자세한 내용은 참조 [컨트롤 사용자 지정 및 디자인 타임 어셈블리 (Visual Studio 2013) 배포](http://msdn.microsoft.com/en-us/96158eb0-b691-4ae1-9e7b-3c65a1b798cb)합니다.</span><span class="sxs-lookup"><span data-stu-id="97b0e-113">For more information, see [Deploying a Custom Control and Design-time Assemblies (Visual Studio 2013)](http://msdn.microsoft.com/en-us/96158eb0-b691-4ae1-9e7b-3c65a1b798cb).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97b0e-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="97b0e-114">See Also</span></span>  
 [<span data-ttu-id="97b0e-115">도구 상자 항목 선택 대화 상자(Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="97b0e-115">Choose Toolbox Items Dialog Box (Visual Studio)</span></span>](http://msdn.microsoft.com/en-us/bd07835f-18a8-433e-bccc-7141f65263bb)  
 [<span data-ttu-id="97b0e-116">사용자 지정 컨트롤 및 디자인 타임 어셈블리 (Visual Studio 2013) 배포</span><span class="sxs-lookup"><span data-stu-id="97b0e-116">Deploying a Custom Control and Design-time Assemblies (Visual Studio 2013)</span></span>](http://msdn.microsoft.com/en-us/96158eb0-b691-4ae1-9e7b-3c65a1b798cb)  
 [<span data-ttu-id="97b0e-117">디자인 타임에 Windows Forms 컨트롤 개발</span><span class="sxs-lookup"><span data-stu-id="97b0e-117">Developing Windows Forms Controls at Design Time</span></span>](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)  
 [<span data-ttu-id="97b0e-118">방법: 전역 어셈블리 캐시에 어셈블리 설치</span><span class="sxs-lookup"><span data-stu-id="97b0e-118">How to: Install an Assembly into the Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)  
 [<span data-ttu-id="97b0e-119">연습: 도구 상자에 자동으로 사용자 지정 구성 요소 채우기</span><span class="sxs-lookup"><span data-stu-id="97b0e-119">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
