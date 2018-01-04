---
title: "방법: WPF 응용 프로그램에 시작 화면 추가"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WPF [WPF], splash screen
- startup window [WPF]
- SplashScreen class [WPF]
- splash screen [WPF]
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1ed9669479a3854c843716a1aeb37f7701ea7d7b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-a-splash-screen-to-a-wpf-application"></a><span data-ttu-id="e89ba-102">방법: WPF 응용 프로그램에 시작 화면 추가</span><span class="sxs-lookup"><span data-stu-id="e89ba-102">How to: Add a Splash Screen to a WPF Application</span></span>
<span data-ttu-id="e89ba-103">이 항목에서는 시작 창에 추가 하는 방법을 보여 줍니다. 또는 *시작 화면*, Windows Presentation Foundation (WPF) 응용 프로그램에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e89ba-103">This topic shows how to add a startup window, or *splash screen*, to a Windows Presentation Foundation (WPF) application.</span></span>  
  
### <a name="to-add-an-existing-image-as-a-splash-screen"></a><span data-ttu-id="e89ba-104">시작 화면으로 기존 이미지를 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="e89ba-104">To add an existing image as a splash screen</span></span>  
  
1.  <span data-ttu-id="e89ba-105">만들기 또는 시작 화면에 대 한 사용 하려는 이미지를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e89ba-105">Create or find an image that you want to use for the splash screen.</span></span> <span data-ttu-id="e89ba-106">Windows Imaging 구성 요소 (WIC)에서 지원 되는 모든 이미지 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e89ba-106">You can use any image format that is supported by the Windows Imaging Component (WIC).</span></span> <span data-ttu-id="e89ba-107">예를 들어, BMP, GIF, JPEG, PNG 또는 TIFF 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e89ba-107">For example, you can use the BMP, GIF, JPEG, PNG, or TIFF format.</span></span>  
  
2.  <span data-ttu-id="e89ba-108">WPF 응용 프로그램 프로젝트에 이미지 파일을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e89ba-108">Add the image file to the WPF Application project.</span></span> <span data-ttu-id="e89ba-109">자세한 내용은 참조 [NIB: 방법: 프로젝트에 기존 항목 추가](http://msdn.microsoft.com/en-us/15f4cfb7-78ab-457f-9f14-099a25a6a2d3)합니다.</span><span class="sxs-lookup"><span data-stu-id="e89ba-109">For more information, see [NIB:How to: Add Existing Items to a Project](http://msdn.microsoft.com/en-us/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).</span></span>  
  
3.  <span data-ttu-id="e89ba-110">솔루션 탐색기에서 이미지를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e89ba-110">In Solution Explorer, select the image.</span></span>  
  
4.  <span data-ttu-id="e89ba-111">속성 창에서 드롭다운 화살표를 클릭는 **빌드 작업** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="e89ba-111">In the Properties window, click the drop-down arrow for the **Build Action** property.</span></span>  
  
5.  <span data-ttu-id="e89ba-112">선택 **SplashScreen** 드롭 다운 목록에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="e89ba-112">Select **SplashScreen** from the drop-down list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e89ba-113">표시 되지 않으면는 **SplashScreen** 옵션을 사용 하 고 있는지 확인 해야 [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] SP1 이상.</span><span class="sxs-lookup"><span data-stu-id="e89ba-113">If you do not see the **SplashScreen** option, be sure to check that you are using [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] SP1 or later.</span></span>  
  
6.  <span data-ttu-id="e89ba-114">F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e89ba-114">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="e89ba-115">시작 화면 이미지 화면 중앙에 표시 되 고 주 응용 프로그램 창이 표시 되 면 사라집니다.</span><span class="sxs-lookup"><span data-stu-id="e89ba-115">The splash screen image appears in the center of the screen, and then fades when the main application window appears.</span></span>  
  
### <a name="to-remove-the-splash-screen-from-an-application"></a><span data-ttu-id="e89ba-116">응용 프로그램에서 시작 화면을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="e89ba-116">To remove the splash screen from an application</span></span>  
  
1.  <span data-ttu-id="e89ba-117">솔루션 탐색기에서 시작 화면 이미지를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e89ba-117">In Solution Explorer, select the splash screen image.</span></span>  
  
2.  <span data-ttu-id="e89ba-118">속성 창에서 설정 된 **빌드 작업** 를 **None**합니다.</span><span class="sxs-lookup"><span data-stu-id="e89ba-118">In the Properties window, set the **Build Action** to **None**.</span></span>  
  
### <a name="to-remove-the-splash-screen-from-an-application"></a><span data-ttu-id="e89ba-119">응용 프로그램에서 시작 화면을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="e89ba-119">To remove the splash screen from an application</span></span>  
  
-   <span data-ttu-id="e89ba-120">솔루션 탐색기에서 시작 화면 이미지를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="e89ba-120">In Solution Explorer, delete the splash screen image.</span></span>  
  
-   <span data-ttu-id="e89ba-121">시작 화면 이미지를 프로젝트에서 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="e89ba-121">Exclude the splash screen image from the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e89ba-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e89ba-122">See Also</span></span>  
 <xref:System.Windows.SplashScreen>  
 [<span data-ttu-id="e89ba-123">NIB: 방법: 프로젝트에 기존 항목 추가</span><span class="sxs-lookup"><span data-stu-id="e89ba-123">NIB:How to: Add Existing Items to a Project</span></span>](http://msdn.microsoft.com/en-us/15f4cfb7-78ab-457f-9f14-099a25a6a2d3)
