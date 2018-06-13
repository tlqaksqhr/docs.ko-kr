---
title: '방법: Windows Forms의 ToolStrip 컨트롤에 대한 사용자 지정 렌더러 만들기 및 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], custom rendering
- toolbars [Windows Forms], rendering
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], rendering
ms.assetid: 88a804ba-679f-4ba3-938a-0dc396199c5b
ms.openlocfilehash: 0b7a77a4a923065cba8c7ea366826f7b04126f11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527176"
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a><span data-ttu-id="2e732-102">방법: Windows Forms의 ToolStrip 컨트롤에 대한 사용자 지정 렌더러 만들기 및 설정</span><span class="sxs-lookup"><span data-stu-id="2e732-102">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>
<span data-ttu-id="2e732-103"><xref:System.Windows.Forms.ToolStrip> 컨트롤에 게 쉽게 지원 테마 및 스타일.</span><span class="sxs-lookup"><span data-stu-id="2e732-103"><xref:System.Windows.Forms.ToolStrip> controls give easy support to themes and styles.</span></span> <span data-ttu-id="2e732-104">설정 하 여 완전 한 사용자 지정 모양 및 동작 (모양 및 느낌)을 얻을 수 있습니다는 <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> 속성 또는 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> 속성을 사용자 지정 렌더러 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e732-104">You can achieve completely custom appearance and behavior (look and feel) by setting either the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property or the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to a custom renderer.</span></span>  
  
 <span data-ttu-id="2e732-105">각 작업자에 게 렌더러를 할당할 수 있습니다 <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip>, 또는 <xref:System.Windows.Forms.StatusStrip> 컨트롤 또는 있습니다 사용할 수는 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> 속성을 설정 하 여 모든 개체를 적용 하려면는 <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> 속성을 <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="2e732-105">You can assign renderers to each individual <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip>, or <xref:System.Windows.Forms.StatusStrip> control, or you can use the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> property to affect all objects by setting the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2e732-106"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A> 반환 <xref:System.Windows.Forms.ToolStripRenderMode.Custom> 경우에만 값을 <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> 않습니다 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="2e732-106"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A> returns <xref:System.Windows.Forms.ToolStripRenderMode.Custom> only if the value of <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> is not `null`.</span></span>  
  
### <a name="to-create-a-custom-renderer"></a><span data-ttu-id="2e732-107">사용자 지정 렌더러를 만들려면</span><span class="sxs-lookup"><span data-stu-id="2e732-107">To create a custom renderer</span></span>  
  
1.  <span data-ttu-id="2e732-108">확장 된 <xref:System.Windows.Forms.ToolStripRenderer> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="2e732-108">Extend the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span>  
  
2.  <span data-ttu-id="2e732-109">원하는 사용자 지정 렌더링을 구현 재정의 하 여 적절 한 *에...*</span><span class="sxs-lookup"><span data-stu-id="2e732-109">Implement desired custom rendering by overriding appropriate *On…*</span></span> <span data-ttu-id="2e732-110">멤버</span><span class="sxs-lookup"><span data-stu-id="2e732-110">members</span></span>  
  
    ```vb  
    Public Class RedTextRenderer  
        Inherits System.Windows.Forms.ToolStripRenderer  
        Protected Overrides Sub OnRenderItemText(ByVal e As _  
            ToolStripItemTextRenderEventArgs)   
            e.TextColor = Color.Red  
            e.TextFont = New Font("Helvetica", 7, FontStyle.Bold)  
            MyBase.OnRenderItemText(e)  
        End Sub  
    End Class  
    ```  
  
    ```csharp  
    public class RedTextRenderer : _  
        System.Windows.Forms.ToolStripRenderer  
    {  
        protected override void _  
            OnRenderItemText(ToolStripItemTextRenderEventArgs e)  
        {  
            e.TextColor = Color.Red;  
            e.TextFont = new Font("Helvetica", 7, FontStyle.Bold);  
           base.OnRenderItemText(e);  
        }  
    }  
    ```  
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a><span data-ttu-id="2e732-111">사용자 지정 렌더러 현재 렌더러를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="2e732-111">To set the custom renderer to be the current renderer</span></span>  
  
1.  <span data-ttu-id="2e732-112">하나에 대 한 사용자 지정 렌더러를 설정 하려면 <xref:System.Windows.Forms.ToolStrip>로 설정 된 <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> 속성을 사용자 지정 렌더러 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e732-112">To set the custom renderer for one <xref:System.Windows.Forms.ToolStrip>, set the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property to the custom renderer.</span></span>  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2.  <span data-ttu-id="2e732-113">모든 사용자 지정 렌더러를 설정 또는 <xref:System.Windows.Forms.ToolStrip> 응용 프로그램에 포함 된 클래스: 설정의 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> 속성을 설정 하 고는 사용자 지정 렌더러는 <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> 속성을 <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>합니다.</span><span class="sxs-lookup"><span data-stu-id="2e732-113">Or to set the custom renderer for all <xref:System.Windows.Forms.ToolStrip> classes contained in your application: Set the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to the custom renderer and set the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span></span>  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2e732-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2e732-114">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>  
 <xref:System.Windows.Forms.ToolStripRenderer>  
 <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>  
 [<span data-ttu-id="2e732-115">ToolStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="2e732-115">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [<span data-ttu-id="2e732-116">ToolStrip 컨트롤 아키텍처</span><span class="sxs-lookup"><span data-stu-id="2e732-116">ToolStrip Control Architecture</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [<span data-ttu-id="2e732-117">ToolStrip 기술 요약</span><span class="sxs-lookup"><span data-stu-id="2e732-117">ToolStrip Technology Summary</span></span>](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
