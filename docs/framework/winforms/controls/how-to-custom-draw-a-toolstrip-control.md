---
title: "방법: ToolStrip 컨트롤 그리기 사용자 지정"
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
helpviewer_keywords:
- toolbars [Windows Forms], custom drawing
- drawing [Windows Forms], owner
- ProfessionalColorTable class [Windows Forms], overriding
- examples [Windows Forms], toolbars
- drawing [Windows Forms], custom
- toolbars [Windows Forms], changing colors
- ToolStrip control [Windows Forms], drawing
- ToolStrip control [Windows Forms], changing colors
- custom drawing
- owner drawing
ms.assetid: 94e7d7bd-a752-441c-b5b3-7acf98881163
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: abb9891fb8e4dde1e94f2d8786ece299ff6579d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-custom-draw-a-toolstrip-control"></a><span data-ttu-id="5060b-102">방법: ToolStrip 컨트롤 그리기 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="5060b-102">How to: Custom Draw a ToolStrip Control</span></span>
<span data-ttu-id="5060b-103"><xref:System.Windows.Forms.ToolStrip> 컨트롤에는 다음과 같은 연결된 렌더링(그리기) 클래스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5060b-103">The <xref:System.Windows.Forms.ToolStrip> controls have the following associated rendering (painting) classes:</span></span>  
  
-   <span data-ttu-id="5060b-104"><xref:System.Windows.Forms.ToolStripSystemRenderer>는 운영 체제의 모양 및 스타일을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5060b-104"><xref:System.Windows.Forms.ToolStripSystemRenderer> provides the appearance and style of your operating system.</span></span>  
  
-   <span data-ttu-id="5060b-105"><xref:System.Windows.Forms.ToolStripProfessionalRenderer>는 Microsoft Office의 모양 및 스타일을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5060b-105"><xref:System.Windows.Forms.ToolStripProfessionalRenderer> provides the appearance and style of Microsoft Office.</span></span>  
  
-   <span data-ttu-id="5060b-106"><xref:System.Windows.Forms.ToolStripRenderer>는 다른 두 렌더링 클래스에 대한 추상 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="5060b-106"><xref:System.Windows.Forms.ToolStripRenderer> is the abstract base class for the other two rendering classes.</span></span>  
  
 <span data-ttu-id="5060b-107"><xref:System.Windows.Forms.ToolStrip>에 대한 사용자 지정 그리기(소유자 그리기라고도 함)를 수행하기 위해 렌더러 클래스 중 하나를 재정의하고 렌더링 논리의 한 측면을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5060b-107">To custom draw (also known as owner draw) a <xref:System.Windows.Forms.ToolStrip>, you can override one of the renderer classes and change an aspect of the rendering logic.</span></span>  
  
 <span data-ttu-id="5060b-108">다음 절차에서는 사용자 지정 그리기의 다양한 측면을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5060b-108">The following procedures describe various aspects of custom drawing.</span></span>  
  
### <a name="to-switch-between-the-provided-renderers"></a><span data-ttu-id="5060b-109">제공된 렌더러 간에 전환하려면</span><span class="sxs-lookup"><span data-stu-id="5060b-109">To switch between the provided renderers</span></span>  
  
-   <span data-ttu-id="5060b-110"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A> 속성을 원하는 <xref:System.Windows.Forms.ToolStripRenderMode> 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5060b-110">Set the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> property to the <xref:System.Windows.Forms.ToolStripRenderMode> value you want.</span></span>  
  
     <span data-ttu-id="5060b-111"><xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>에서는 정적 <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>가 응용 프로그램에 대한 렌더러를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="5060b-111">With <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>, the static <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> determines the renderer for your application.</span></span> <span data-ttu-id="5060b-112"><xref:System.Windows.Forms.ToolStripRenderMode>의 다른 값은 <xref:System.Windows.Forms.ToolStripRenderMode.Custom>, <xref:System.Windows.Forms.ToolStripRenderMode.Professional> 및 <xref:System.Windows.Forms.ToolStripRenderMode.System>입니다.</span><span class="sxs-lookup"><span data-stu-id="5060b-112">The other values of <xref:System.Windows.Forms.ToolStripRenderMode> are <xref:System.Windows.Forms.ToolStripRenderMode.Custom>, <xref:System.Windows.Forms.ToolStripRenderMode.Professional>, and <xref:System.Windows.Forms.ToolStripRenderMode.System>.</span></span>  
  
### <a name="to-change-the-microsoft-officestyle-borders-to-straight"></a><span data-ttu-id="5060b-113">Microsoft Office 스타일 테두리를 직선으로 변경하려면</span><span class="sxs-lookup"><span data-stu-id="5060b-113">To change the Microsoft Office–style borders to straight</span></span>  
  
-   <span data-ttu-id="5060b-114"><xref:System.Windows.Forms.ToolStripProfessionalRenderer.OnRenderToolStripBorder%2A?displayProperty=nameWithType>를 재정의하지만 기본 클래스를 호출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5060b-114">Override <xref:System.Windows.Forms.ToolStripProfessionalRenderer.OnRenderToolStripBorder%2A?displayProperty=nameWithType>, but do not call the base class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5060b-115"><xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripSystemRenderer> 및 <xref:System.Windows.Forms.ToolStripProfessionalRenderer>에 대한 이 메서드의 버전이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5060b-115">There is a version of this method for <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripSystemRenderer>, and <xref:System.Windows.Forms.ToolStripProfessionalRenderer>.</span></span>  
  
### <a name="to-change-the-professionalcolortable"></a><span data-ttu-id="5060b-116">ProfessionalColorTable을 변경하려면</span><span class="sxs-lookup"><span data-stu-id="5060b-116">To change the ProfessionalColorTable</span></span>  
  
-   <span data-ttu-id="5060b-117"><xref:System.Windows.Forms.ProfessionalColorTable>을 재정의하고 원하는 색을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="5060b-117">Override <xref:System.Windows.Forms.ProfessionalColorTable> and change the colors you want.</span></span>  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As _  
    System.EventArgs) Handles Me.Load  
        Dim t As MyColorTable = New MyColorTable  
        ToolStrip1.Renderer = New ToolStripProfessionalRenderer(t)  
    End Sub  
  
    Class MyColorTable   
    Inherits ProfessionalColorTable  
  
    Public Overrides ReadOnly Property ButtonPressedGradientBegin() As Color  
        Get  
            Return Color.Red  
        End Get  
    End Property  
  
    Public Overrides ReadOnly Property ButtonPressedGradientMiddle() _  
    As System.Drawing.Color  
        Get  
            Return Color.Blue  
        End Get  
            End Property  
  
    Public Overrides ReadOnly Property ButtonPressedGradientEnd() _  
    As System.Drawing.Color  
        Get  
            Return Color.Green  
        End Get  
    End Property  
  
    Public Overrides ReadOnly Property ButtonSelectedGradientBegin() _  
    As Color  
        Get  
            Return Color.Yellow  
        End Get  
    End Property  
  
    Public Overrides ReadOnly Property ButtonSelectedGradientMiddle() As System.Drawing.Color  
        Get  
            Return Color.Orange  
        End Get  
    End Property  
  
    Public Overrides ReadOnly Property ButtonSelectedGradientEnd() _  
    As System.Drawing.Color  
        Get  
            Return Color.Violet  
        End Get  
    End Property  
    End Class  
    ```  
  
### <a name="to-change-the-rendering-for-all-toolstrip-controls-in-your-application"></a><span data-ttu-id="5060b-118">응용 프로그램의 모든 ToolStrip 컨트롤에 대한 렌더링을 변경하려면</span><span class="sxs-lookup"><span data-stu-id="5060b-118">To change the rendering for all ToolStrip controls in your application</span></span>  
  
1.  <span data-ttu-id="5060b-119"><xref:System.Windows.Forms.ToolStripManager.RenderMode%2A?displayProperty=nameWithType> 속성을 사용하여 제공된 렌더러 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5060b-119">Use the <xref:System.Windows.Forms.ToolStripManager.RenderMode%2A?displayProperty=nameWithType> property to choose one of the provided renderers.</span></span>  
  
2.  <span data-ttu-id="5060b-120"><xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType>를 사용하여 사용자 지정 렌더러를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="5060b-120">Use <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> to assign a custom renderer.</span></span>  
  
3.  <span data-ttu-id="5060b-121"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType>가 기본값인 <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>로 설정되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5060b-121">Ensure that <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> is set to the default value of <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span></span>  
  
### <a name="to-turn-off-the-microsoft-office-colors-for-the-entire-application"></a><span data-ttu-id="5060b-122">전체 응용 프로그램에 대해 Microsoft Office 색을 해제하려면</span><span class="sxs-lookup"><span data-stu-id="5060b-122">To turn off the Microsoft Office colors for the entire application</span></span>  
  
-   <span data-ttu-id="5060b-123"><xref:System.Windows.Forms.ToolStripManager.VisualStylesEnabled%2A?displayProperty=nameWithType>를 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5060b-123">Set <xref:System.Windows.Forms.ToolStripManager.VisualStylesEnabled%2A?displayProperty=nameWithType> to `false`.</span></span>  
  
### <a name="to-turn-off-the-microsoft-office-colors-for-one-toolstrip-control"></a><span data-ttu-id="5060b-124">하나의 ToolStrip 컨트롤에 대해 Microsoft Office 색을 해제하려면</span><span class="sxs-lookup"><span data-stu-id="5060b-124">To turn off the Microsoft Office colors for one ToolStrip control</span></span>  
  
-   <span data-ttu-id="5060b-125">다음 코드 예제와 유사한 코드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5060b-125">Use code similar to the following code example.</span></span>  
  
    ```vb  
    Dim colorTable As ProfessionalColorTable()  
    colorTable.UseSystemColors = True  
    Dim toolStrip.Renderer As ToolStripProfessionalRenderer(colorTable)  
    ```  
  
    ```csharp  
    ProfessionalColorTable colorTable = new ProfessionalColorTable();  
    colorTable.UseSystemColors = true;  
    toolStrip.Renderer = new ToolStripProfessionalRenderer(colorTable);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5060b-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5060b-126">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripSystemRenderer>  
 <xref:System.Windows.Forms.ToolStripProfessionalRenderer>  
 <xref:System.Windows.Forms.ToolStripRenderer>  
 [<span data-ttu-id="5060b-127">소유자 그리기 지원이 기본 제공되는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="5060b-127">Controls with Built-In Owner-Drawing Support</span></span>](../../../../docs/framework/winforms/controls/controls-with-built-in-owner-drawing-support.md)  
 [<span data-ttu-id="5060b-128">방법: Windows Forms의 ToolStrip 컨트롤에 대한 사용자 지정 렌더러를 설정하고 만들기</span><span class="sxs-lookup"><span data-stu-id="5060b-128">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>](../../../../docs/framework/winforms/controls/create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)  
 [<span data-ttu-id="5060b-129">ToolStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="5060b-129">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
