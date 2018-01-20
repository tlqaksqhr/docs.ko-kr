---
title: "방법: Windows Forms에 ActiveX 컨트롤 추가"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 940dd21fc48c23ce623280aab2c487db5810057c
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a><span data-ttu-id="8d248-102">방법: Windows Forms에 ActiveX 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="8d248-102">How to: Add ActiveX Controls to Windows Forms</span></span>
<span data-ttu-id="8d248-103">Windows Forms 컨트롤 호스트에 Windows Forms 디자이너가 최적화 하는 동안에 Windows Forms에서 ActiveX 컨트롤을 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d248-103">While the Windows Forms Designer is optimized to host Windows Forms controls, you can also put ActiveX controls on Windows Forms.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="8d248-104">ActiveX 컨트롤에 추가 되는 경우 Windows Forms에 대 한 성능 제한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d248-104">There are performance limitations for Windows Forms when ActiveX controls are added to them.</span></span>  
  
 <span data-ttu-id="8d248-105">ActiveX 컨트롤을 폼에 추가 하기 전에 도구 상자에 추가 해야.</span><span class="sxs-lookup"><span data-stu-id="8d248-105">Before you add ActiveX controls to your form, you must add them to the Toolbox.</span></span> <span data-ttu-id="8d248-106">자세한 내용은 참조 [COM 구성 요소, 사용자 지정 도구 상자 대화 상자](http://msdn.microsoft.com/library/171333f3-f207-4e02-bbdc-17862556212c)합니다.</span><span class="sxs-lookup"><span data-stu-id="8d248-106">For more information, see [COM Components, Customize Toolbox Dialog Box](http://msdn.microsoft.com/library/171333f3-f207-4e02-bbdc-17862556212c).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8d248-107">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d248-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="8d248-108">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8d248-108">To change your settings, click **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="8d248-109">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8d248-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-an-activex-control-to-your-windows-form"></a><span data-ttu-id="8d248-110">ActiveX 컨트롤을 Windows Form을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="8d248-110">To add an ActiveX control to your Windows Form</span></span>  
  
-   <span data-ttu-id="8d248-111">도구 상자에 컨트롤을 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d248-111">Double-click the control on the Toolbox.</span></span>  
  
     [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]<span data-ttu-id="8d248-112">컨트롤에 대 한 모든 참조는 프로젝트에에서 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d248-112"> adds all references to the control in your project.</span></span> <span data-ttu-id="8d248-113">Windows Forms에서 ActiveX 컨트롤을 사용 하는 경우 유의 해야 할 사항에 대 한 자세한 내용은 참조 [Windows Form에서 ActiveX 컨트롤을 호스팅할 때의 고려 사항](../../../../docs/framework/winforms/controls/considerations-when-hosting-an-activex-control-on-a-windows-form.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8d248-113">For more information about things to keep in mind when using ActiveX controls on Windows Forms, see [Considerations When Hosting an ActiveX Control on a Windows Form](../../../../docs/framework/winforms/controls/considerations-when-hosting-an-activex-control-on-a-windows-form.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8d248-114">Windows Forms ActiveX 컨트롤 가져오기 (AxImp.exe) ActiveX 동적 연결 라이브러리를 가져오는에 예상 보다 다른 종류의 이벤트 인수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8d248-114">The Windows Forms ActiveX Control Importer (AxImp.exe) creates event arguments of a different type than expected upon importation of ActiveX dynamic link libraries.</span></span> <span data-ttu-id="8d248-115">AxImp.exe에서 만든 인수는 다음과 같은: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`때 `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` 가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d248-115">The arguments created by AxImp.exe are similar to the following: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, when `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` is expected.</span></span> <span data-ttu-id="8d248-116">주의이 불일치로 하지 않는 코드는 정상적으로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d248-116">Be aware that this irregularity does not prevent code from functioning normally.</span></span> <span data-ttu-id="8d248-117">자세한 내용은 참조 [Windows Forms ActiveX 컨트롤 가져오기 (Aximp.exe)](../../../../docs/framework/tools/aximp-exe-windows-forms-activex-control-importer.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8d248-117">For details, see [Windows Forms ActiveX Control Importer (Aximp.exe)](../../../../docs/framework/tools/aximp-exe-windows-forms-activex-control-importer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d248-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8d248-118">See Also</span></span>  
 [<span data-ttu-id="8d248-119">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="8d248-119">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="8d248-120">여러 언어 및 라이브러리에서 사용되는 컨트롤 및 프로그래밍 가능한 개체 비교</span><span class="sxs-lookup"><span data-stu-id="8d248-120">Controls and Programmable Objects Compared in Various Languages and Libraries</span></span>](http://msdn.microsoft.com/library/021f2a1b-8247-4348-a5ad-e1d9ab23004b)  
 [<span data-ttu-id="8d248-121">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="8d248-121">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [<span data-ttu-id="8d248-122">Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="8d248-122">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="8d248-123">개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공</span><span class="sxs-lookup"><span data-stu-id="8d248-123">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="8d248-124">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="8d248-124">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="8d248-125">기능별 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="8d248-125">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
