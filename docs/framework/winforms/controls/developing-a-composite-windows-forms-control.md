---
title: "Windows Forms 복합 컨트롤 개발"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom controls [Windows Forms], composite controls
- composite controls [Windows Forms]
- composite controls [Windows Forms], Windows Forms
- controls [Windows Forms], composite
ms.assetid: d086f2a3-baa3-4e09-b40c-a5bb3cfc51a6
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: da180f888031aace892efc770184be53e9341047
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="developing-a-composite-windows-forms-control"></a><span data-ttu-id="9ca3a-102">Windows Forms 복합 컨트롤 개발</span><span class="sxs-lookup"><span data-stu-id="9ca3a-102">Developing a Composite Windows Forms Control</span></span>
<span data-ttu-id="9ca3a-103">다른 Windows Forms 컨트롤을 결합하여 복합 Windows Forms 컨트롤을 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3a-103">You can develop a composite Windows Forms control by combining other Windows Forms controls.</span></span> <span data-ttu-id="9ca3a-104">파생 되는 복합 컨트롤 <xref:System.Web.UI.UserControl> 사용자 컨트롤 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3a-104">Composite controls that derive from <xref:System.Web.UI.UserControl> are called user controls.</span></span> <span data-ttu-id="9ca3a-105">기본 클래스 <xref:System.Windows.Forms.UserControl>은 자식 컨트롤에 대한 키보드 라우팅을 제공하므로 자식 컨트롤이 포커스를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3a-105">The base class, <xref:System.Windows.Forms.UserControl>, provides keyboard routing for the child controls, thus ensuring that child controls can receive focus.</span></span> <span data-ttu-id="9ca3a-106">사용자 정의 컨트롤의 예제를 보려면는 <xref:System.Windows.Forms.UserControl> 샘플 [하는 방법: Windows Forms 컨트롤에서 특성 적용](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3a-106">For an example of a user control, see the <xref:System.Windows.Forms.UserControl> sample in [How to: Apply Attributes in Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md).</span></span>  
  
 <span data-ttu-id="9ca3a-107">[!INCLUDE[vsprvsext](../../../../includes/vsprvsext-md.md)]의 Windows Forms 디자이너에서는 사용자 컨트롤 작성에 대한 다양한 디자인 타임 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca3a-107">The Windows Forms designer in [!INCLUDE[vsprvsext](../../../../includes/vsprvsext-md.md)] provides rich design-time support for authoring user controls.</span></span>  
  
-   <span data-ttu-id="9ca3a-108">[방법: 도구 상자 항목 선택 대화 상자에 컨트롤 표시](http://msdn.microsoft.com/library/9yxtkx75\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9ca3a-108">[How to: Display a Control in the Choose Toolbox Items Dialog Box](http://msdn.microsoft.com/library/9yxtkx75\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9ca3a-109">[연습: DesignerSerializationVisibilityAttribute를 사용하여 표준 형식의 컬렉션 직렬화](http://msdn.microsoft.com/library/ms171731\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9ca3a-109">[Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute](http://msdn.microsoft.com/library/ms171731\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9ca3a-110">[연습: Visual C#을 사용하여 Windows Forms 컨트롤에서 상속](http://msdn.microsoft.com/en-us/09476da0-8d4c-4a4c-b969-649519dfb438))</span><span class="sxs-lookup"><span data-stu-id="9ca3a-110">[Walkthrough: Inheriting from a Windows Forms Control with Visual C#](http://msdn.microsoft.com/en-us/09476da0-8d4c-4a4c-b969-649519dfb438))</span></span>  
  
-   <span data-ttu-id="9ca3a-111">[방법: 컨트롤에 대한 도구 상자 비트맵 제공](http://msdn.microsoft.com/library/4wk1wc0a\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9ca3a-111">[How to: Provide a Toolbox Bitmap for a Control](http://msdn.microsoft.com/library/4wk1wc0a\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9ca3a-112">[방법: 기존 Windows Forms 컨트롤에서 상속](http://msdn.microsoft.com/library/7h62478z\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9ca3a-112">[How to: Inherit from Existing Windows Forms Controls](http://msdn.microsoft.com/library/7h62478z\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9ca3a-113">[연습: 디자인 타임에 사용자 지정 Windows Forms 컨트롤 디버깅](http://msdn.microsoft.com/library/5ytx0z24\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9ca3a-113">[Walkthrough: Debugging Custom Windows Forms Controls at Design Time](http://msdn.microsoft.com/library/5ytx0z24\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9ca3a-114">[방법: Control 클래스에서 상속](http://msdn.microsoft.com/library/skcysbt2\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9ca3a-114">[How to: Inherit from the Control Class](http://msdn.microsoft.com/library/skcysbt2\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9ca3a-115">[방법: UserControl의 런타임 동작 테스트](http://msdn.microsoft.com/library/ms171738\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9ca3a-115">[How to: Test the Run-Time Behavior of a UserControl](http://msdn.microsoft.com/library/ms171738\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9ca3a-116">[방법: 디자인 타임에 컨트롤을 양식의 가장자리에 맞춤](http://msdn.microsoft.com/library/1fxyb15b\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9ca3a-116">[How to: Align a Control to the Edges of Forms at Design Time](http://msdn.microsoft.com/library/1fxyb15b\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9ca3a-117">[방법: UserControl 클래스에서 상속](http://msdn.microsoft.com/library/00ctb4z0\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9ca3a-117">[How to: Inherit from the UserControl Class](http://msdn.microsoft.com/library/00ctb4z0\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9ca3a-118">[방법: Windows Forms 컨트롤 작성](http://msdn.microsoft.com/library/bs3yhkh7\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9ca3a-118">[How to: Author Controls for Windows Forms](http://msdn.microsoft.com/library/bs3yhkh7\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9ca3a-119">[방법: 복합 컨트롤 작성](http://msdn.microsoft.com/library/3sf86w5h\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9ca3a-119">[How to: Author Composite Controls](http://msdn.microsoft.com/library/3sf86w5h\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9ca3a-120">[연습: Visual Basic에서 복합 컨트롤 제작](http://msdn.microsoft.com/library/c316f119\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9ca3a-120">[Walkthrough: Authoring a Composite Control with Visual Basic](http://msdn.microsoft.com/library/c316f119\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9ca3a-121">[연습: Visual C#에서 복합 컨트롤 제작](http://msdn.microsoft.com/en-us/f88481a8-c746-4a36-9479-374ce5f2e91f))</span><span class="sxs-lookup"><span data-stu-id="9ca3a-121">[Walkthrough: Authoring a Composite Control with Visual C#](http://msdn.microsoft.com/en-us/f88481a8-c746-4a36-9479-374ce5f2e91f))</span></span>  
  
-   <span data-ttu-id="9ca3a-122">[연습: Visual Basic을 사용하여 Windows Forms 컨트롤에서 상속](http://msdn.microsoft.com/library/w2a8y03d\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9ca3a-122">[Walkthrough: Inheriting from a Windows Forms Control with Visual Basic](http://msdn.microsoft.com/library/w2a8y03d\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9ca3a-123">[방법: 디자인 타임 기능을 활용하는 Windows Forms 컨트롤 만들기](http://msdn.microsoft.com/library/307hck25\(v=vs.110\))</span><span class="sxs-lookup"><span data-stu-id="9ca3a-123">[How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](http://msdn.microsoft.com/library/307hck25\(v=vs.110\))</span></span>  
  
-   <span data-ttu-id="9ca3a-124">[방법: 디자인 타임 기능을 활용하는 Windows Forms 컨트롤 만들기](http://msdn.microsoft.com/library/307hck25\(v=vs.120\))</span><span class="sxs-lookup"><span data-stu-id="9ca3a-124">[How to: Create a Windows Forms Control That Takes Advantage of Design-Time Features](http://msdn.microsoft.com/library/307hck25\(v=vs.120\))</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ca3a-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9ca3a-125">See Also</span></span>  
 [<span data-ttu-id="9ca3a-126">방법: Windows Forms 컨트롤에서 특성 적용</span><span class="sxs-lookup"><span data-stu-id="9ca3a-126">How to: Apply Attributes in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-apply-attributes-in-windows-forms-controls.md)  
 [<span data-ttu-id="9ca3a-127">.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발</span><span class="sxs-lookup"><span data-stu-id="9ca3a-127">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [<span data-ttu-id="9ca3a-128">사용자 지정 컨트롤의 종류</span><span class="sxs-lookup"><span data-stu-id="9ca3a-128">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
