---
title: "방법: Windows Forms에 컨트롤 배치"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Location
- Location.Y
- Location.X
helpviewer_keywords:
- controls [Windows Forms]
- controls [Windows Forms], moving
- snaplines
- controls [Windows Forms], positioning
ms.assetid: 4693977e-34a4-4f19-8221-68c3120c2b2b
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9ff1096e6397f4422e0fbf6400a87041cfac6470
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-position-controls-on-windows-forms"></a><span data-ttu-id="cec1a-102">방법: Windows Forms에 컨트롤 배치</span><span class="sxs-lookup"><span data-stu-id="cec1a-102">How to: Position Controls on Windows Forms</span></span>
<span data-ttu-id="cec1a-103">컨트롤의 위치, Windows Forms 디자이너를 사용 하거나 지정 된 <xref:System.Windows.Forms.Control.Location%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="cec1a-103">To position controls, use the Windows Forms Designer, or specify the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cec1a-104">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cec1a-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="cec1a-105">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cec1a-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="cec1a-106">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cec1a-106">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a><span data-ttu-id="cec1a-107">Windows Forms 디자이너의 디자인 화면에 컨트롤을 배치 하려면</span><span class="sxs-lookup"><span data-stu-id="cec1a-107">To position a control on the design surface of the Windows Forms Designer</span></span>  
  
-   <span data-ttu-id="cec1a-108">컨트롤을 마우스로 적절 한 위치로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="cec1a-108">Drag the control to the appropriate location with the mouse.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cec1a-109">컨트롤을 선택 하 고 화살표가 포함 된 키 보다 정확 하 게 배치 하기 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="cec1a-109">Select the control and move it with the ARROW keys to position it more precisely.</span></span> <span data-ttu-id="cec1a-110">또한 *맞춤선* 정확 하 게 폼에 컨트롤을 배치 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cec1a-110">Also, *snaplines* assist you in placing controls precisely on your form.</span></span> <span data-ttu-id="cec1a-111">자세한 내용은 참조 [연습: 맞춤선 Windows Forms에서 사용 하 여 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cec1a-111">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>  
  
### <a name="to-position-a-control-using-the-properties-window"></a><span data-ttu-id="cec1a-112">속성 창을 사용 하 여 컨트롤을 배치 하기</span><span class="sxs-lookup"><span data-stu-id="cec1a-112">To position a control using the Properties window</span></span>  
  
1.  <span data-ttu-id="cec1a-113">컨트롤의 위치를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="cec1a-113">Click the control you want to position.</span></span>  
  
2.  <span data-ttu-id="cec1a-114">**속성** 창에 대 한 유형 값의 <xref:System.Windows.Forms.Control.Location%2A> 해당 컨테이너 내에서 컨트롤을 배치 하는 쉼표로 구분 된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="cec1a-114">In the **Properties** window, type values for the <xref:System.Windows.Forms.Control.Location%2A> property, separated by a comma, to position the control within its container.</span></span>  
  
     <span data-ttu-id="cec1a-115">첫 번째 번호 (X)은; 컨테이너의 왼쪽된 테두리 거리 두 번째 숫자 (Y)는 거리 (픽셀) 컨테이너 영역의 위쪽 테두리 합니다.</span><span class="sxs-lookup"><span data-stu-id="cec1a-115">The first number (X) is the distance from the left border of the container; the second number (Y) is the distance from the upper border of the container area, measured in pixels.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cec1a-116">확장할 수 있습니다는 <xref:System.Windows.Forms.Control.Location%2A> 속성 입력을 **X** 및 **Y** 값을 개별적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="cec1a-116">You can expand the <xref:System.Windows.Forms.Control.Location%2A> property to type the **X** and **Y** values individually.</span></span>  
  
### <a name="to-position-a-control-programmatically"></a><span data-ttu-id="cec1a-117">컨트롤을 프로그래밍 방식으로 배치 하려면</span><span class="sxs-lookup"><span data-stu-id="cec1a-117">To position a control programmatically</span></span>  
  
1.  <span data-ttu-id="cec1a-118">설정의 <xref:System.Windows.Forms.Control.Location%2A> 컨트롤의 속성을 <xref:System.Drawing.Point>합니다.</span><span class="sxs-lookup"><span data-stu-id="cec1a-118">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the control to a <xref:System.Drawing.Point>.</span></span>  
  
    ```vb  
    Button1.Location = New Point(100, 100)  
    ```  
  
    ```csharp  
    button1.Location = new Point(100, 100);  
    ```  
  
    ```cpp  
    button1->Location = Point(100, 100);  
    ```  
  
2.  <span data-ttu-id="cec1a-119">X 좌표는 컨트롤의 위치를 변경 사용 하 여 <xref:System.Windows.Forms.Control.Left%2A> 하위 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="cec1a-119">Change the X coordinate of the control's location using the <xref:System.Windows.Forms.Control.Left%2A> subproperty.</span></span>  
  
    ```vb  
    Button1.Left = 300  
    ```  
  
    ```csharp  
    button1.Left = 300;  
    ```  
  
    ```cpp  
    button1->Left = 300;  
    ```  
  
### <a name="to-increment-a-controls-location-programmatically"></a><span data-ttu-id="cec1a-120">컨트롤의 위치를 프로그래밍 방식으로 증가</span><span class="sxs-lookup"><span data-stu-id="cec1a-120">To increment a control's location programmatically</span></span>  
  
1.  <span data-ttu-id="cec1a-121">설정의 <xref:System.Windows.Forms.Control.Left%2A> 하위 속성 컨트롤의 X 좌표를 늘립니다.</span><span class="sxs-lookup"><span data-stu-id="cec1a-121">Set the <xref:System.Windows.Forms.Control.Left%2A> subproperty to increment the X coordinate of the control.</span></span>  
  
    ```vb  
    Button1.Left += 200  
    ```  
  
    ```csharp  
    button1.Left += 200;  
    ```  
  
    ```cpp  
    button1->Left += 200;  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="cec1a-122">사용 하 여 <xref:System.Windows.Forms.Control.Location%2A> 속성을 설정 하는 컨트롤의 X 및 Y 위치를 동시에 합니다.</span><span class="sxs-lookup"><span data-stu-id="cec1a-122">Use the <xref:System.Windows.Forms.Control.Location%2A> property to set a control's X and Y positions simultaneously.</span></span> <span data-ttu-id="cec1a-123">위치를 개별적으로 설정 하는 컨트롤을 사용 하 여 <xref:System.Windows.Forms.Control.Left%2A> (**X**) 또는 <xref:System.Windows.Forms.Control.Top%2A> (**Y**) 하위 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="cec1a-123">To set a position individually, use the control's <xref:System.Windows.Forms.Control.Left%2A> (**X**) or <xref:System.Windows.Forms.Control.Top%2A> (**Y**) subproperty.</span></span> <span data-ttu-id="cec1a-124">암시적으로의 X 및 Y 좌표를 설정 하지 마십시오는 <xref:System.Drawing.Point> 이 구조는 단추의 좌표의 복사본을 포함 하기 때문에 단추의 위치를 나타내는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="cec1a-124">Do not try to implicitly set the X and Y coordinates of the <xref:System.Drawing.Point> structure that represents the button's location, because this structure contains a copy of the button's coordinates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cec1a-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cec1a-125">See Also</span></span>  
 [<span data-ttu-id="cec1a-126">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="cec1a-126">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="cec1a-127">연습: Windows Forms에서 맞춤선을 사용하여 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="cec1a-127">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [<span data-ttu-id="cec1a-128">연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="cec1a-128">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [<span data-ttu-id="cec1a-129">연습: FlowLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="cec1a-129">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [<span data-ttu-id="cec1a-130">Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="cec1a-130">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="cec1a-131">개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공</span><span class="sxs-lookup"><span data-stu-id="cec1a-131">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="cec1a-132">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="cec1a-132">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="cec1a-133">기능별 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="cec1a-133">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)  
 [<span data-ttu-id="cec1a-134">방법: Windows Forms의 화면 위치 설정</span><span class="sxs-lookup"><span data-stu-id="cec1a-134">How to: Set the Screen Location of Windows Forms</span></span>](http://msdn.microsoft.com/en-us/cb023ab7-dea7-4284-9aa6-8c03c59b60c6)
