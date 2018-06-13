---
title: WPF 컨트롤 사용
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
ms.openlocfilehash: 8dcf79d449a8f8443774b133904e819dfd925288
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526606"
---
# <a name="using-wpf-controls"></a><span data-ttu-id="5295a-102">WPF 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="5295a-102">Using WPF Controls</span></span>
<span data-ttu-id="5295a-103">Windows Forms 기반 응용 프로그램에서 Windows Presentation Foundation (WPF) 컨트롤을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5295a-103">You can use Windows Presentation Foundation (WPF) controls in your Windows Forms-based applications.</span></span> <span data-ttu-id="5295a-104">이러한 옵션은 두 가지 서로 다른 뷰 기술, 상호 운용 되 원활 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="5295a-104">Although these are two different view technologies, they interoperate smoothly.</span></span>  
  
 <span data-ttu-id="5295a-105">Windows Forms 디자이너에는 Windows Presentation Foundation 컨트롤을 호스팅하기 위한 시각적 디자인 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5295a-105">The Windows Forms Designer provides a visual design environment for hosting Windows Presentation Foundation controls.</span></span> <span data-ttu-id="5295a-106">라고 하는 특수 Windows Forms 컨트롤에서 WPF 컨트롤 호스트 <xref:System.Windows.Forms.Integration.ElementHost>합니다.</span><span class="sxs-lookup"><span data-stu-id="5295a-106">A WPF control is hosted by a special Windows Forms control that is named <xref:System.Windows.Forms.Integration.ElementHost>.</span></span> <span data-ttu-id="5295a-107">이 컨트롤을는 WPF 컨트롤을 폼의 레이아웃에 관여 하 고 키보드 및 마우스 메시지를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5295a-107">This control enables the WPF control to participate in the form's layout and to receive keyboard and mouse messages.</span></span> <span data-ttu-id="5295a-108">디자인 타임에 정렬할 수 있습니다는 <xref:System.Windows.Forms.Integration.ElementHost> 방법과 마찬가지로 Windows Forms 컨트롤을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="5295a-108">At design time, you can arrange the <xref:System.Windows.Forms.Integration.ElementHost> control just as you would any Windows Forms control.</span></span>  
  
 <span data-ttu-id="5295a-109">WPF 기반 응용 프로그램에서 Windows Forms 컨트롤을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5295a-109">You can also use Windows Forms controls in your WPF-based applications.</span></span> <span data-ttu-id="5295a-110">자세한 내용은 참조 [WPF 디자이너](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)합니다.</span><span class="sxs-lookup"><span data-stu-id="5295a-110">For more information, see [WPF Designer](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5295a-111">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="5295a-111">In This Section</span></span>  
 [<span data-ttu-id="5295a-112">방법: 디자인 타임에 ElementHost 컨트롤 복사하여 붙여넣기</span><span class="sxs-lookup"><span data-stu-id="5295a-112">How to: Copy and Paste an ElementHost Control at Design Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-copy-and-paste-an-elementhost-control-at-design-time.md)  
 <span data-ttu-id="5295a-113">Windows Form에 Windows Presentation Foundation 컨트롤을 복사 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5295a-113">Shows how to copy a Windows Presentation Foundation control on a Windows Form.</span></span>  
  
 [<span data-ttu-id="5295a-114">연습: 디자인 타임에 Windows Forms에서 WPF 콘텐츠 정렬</span><span class="sxs-lookup"><span data-stu-id="5295a-114">Walkthrough: Arranging WPF Content on Windows Forms at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-arranging-wpf-content-on-windows-forms-at-design-time.md)  
 <span data-ttu-id="5295a-115">Windows Presentation Foundation 컨트롤을 정렬 하려면 기준 위치 지정 및 맞춤선과 같은 Windows Forms 레이아웃 기능을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5295a-115">Shows how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation controls.</span></span>  
  
 [<span data-ttu-id="5295a-116">연습: 디자인 타임에 호스팅된 WPF 요소의 속성 변경</span><span class="sxs-lookup"><span data-stu-id="5295a-116">Walkthrough: Changing Properties of a Hosted WPF Element at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-changing-properties-of-a-hosted-wpf-element-at-design-time.md)  
 <span data-ttu-id="5295a-117">Windows Forms 디자이너 간의 워크플로 표시 및 [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] WPF 컨트롤에 속성을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="5295a-117">Shows the workflow between the Windows Forms Designer and the [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)] for changing properties on WPF controls.</span></span>  
  
 [<span data-ttu-id="5295a-118">연습: 디자인 타임에 Windows Forms에서 새 WPF 콘텐츠 만들기</span><span class="sxs-lookup"><span data-stu-id="5295a-118">Walkthrough: Creating New WPF Content on Windows Forms at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)  
 <span data-ttu-id="5295a-119">Windows Forms 기반 응용 프로그램에서 사용 하기 위해 Windows Presentation Foundation 컨트롤을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5295a-119">Shows how to create a Windows Presentation Foundation control for use in your Windows Forms-based applications.</span></span>  
  
 [<span data-ttu-id="5295a-120">연습: ElementHost 컨트롤을 복사하여 다른 Windows Forms에 붙여넣기</span><span class="sxs-lookup"><span data-stu-id="5295a-120">Walkthrough: Copying and Pasting an ElementHost Control into Separate Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/copy--paste-an-elementhost-control-into-forms.md)  
 <span data-ttu-id="5295a-121">하나의 Windows Form에서 Windows Presentation Foundation 컨트롤 복사 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5295a-121">Shows how to copy a Windows Presentation Foundation control from one Windows Form to another.</span></span>  
  
 [<span data-ttu-id="5295a-122">연습: 디자인 타임에 Windows Forms에서 WPF 콘텐츠 할당</span><span class="sxs-lookup"><span data-stu-id="5295a-122">Walkthrough: Assigning WPF Content on Windows Forms at Design Time</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-assigning-wpf-content-on-windows-forms-at-design-time.md)  
 <span data-ttu-id="5295a-123">폼에 표시 하려는 Windows Presentation Foundation 컨트롤 종류를 선택 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5295a-123">Shows how to select the Windows Presentation Foundation control types you want to display on your form.</span></span>  
  
 [<span data-ttu-id="5295a-124">연습: WPF 콘텐츠 스타일 지정</span><span class="sxs-lookup"><span data-stu-id="5295a-124">Walkthrough: Styling WPF Content</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md)  
 <span data-ttu-id="5295a-125">Windows Forms 디자이너 간의 워크플로 보여 줍니다. 및 [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] Windows Presentation Foundation 컨트롤에 스타일을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5295a-125">Shows the workflow between the Windows Forms Designer and the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)] for applying styles to Windows Presentation Foundation controls.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5295a-126">참조</span><span class="sxs-lookup"><span data-stu-id="5295a-126">Reference</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <span data-ttu-id="5295a-127">Windows Forms 기반 응용 프로그램에서 호스트 Windows Presentation Foundation 컨트롤에 사용할 수 있는 클래스를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5295a-127">Describes a class which you can use to host Windows Presentation Foundation controls in your Windows Forms-based applications.</span></span>  
  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 <span data-ttu-id="5295a-128">Windows Presentation Foundation 기반 응용 프로그램 호스트 Windows Forms 컨트롤에 사용할 수 있는 클래스를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5295a-128">Describes a class which you can use to host Windows Forms controls in your Windows Presentation Foundation-based application.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5295a-129">관련 단원</span><span class="sxs-lookup"><span data-stu-id="5295a-129">Related Sections</span></span>  
 [<span data-ttu-id="5295a-130">마이그레이션 및 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="5295a-130">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 <span data-ttu-id="5295a-131">Windows Presentation Foundation 및 Windows Forms 기술 간의 상호 운용성에 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5295a-131">Describes interoperation between the Windows Presentation Foundation and Windows Forms technologies.</span></span>  
  
 [<span data-ttu-id="5295a-132">WPF 디자이너</span><span class="sxs-lookup"><span data-stu-id="5295a-132">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 <span data-ttu-id="5295a-133">Visual Studio에서 Windows Presentation Foundation 컨트롤을 디자인 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5295a-133">Describes how to design Windows Presentation Foundation controls in Visual Studio.</span></span>
