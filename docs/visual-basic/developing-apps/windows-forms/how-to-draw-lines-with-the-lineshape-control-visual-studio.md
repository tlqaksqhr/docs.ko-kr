---
title: '방법: LineShape 컨트롤로 선 그리기(Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- LineShape control [Visual Basic]
- lines, drawing
ms.assetid: 83e71b4e-aa76-4f9b-b547-8704309fd1e5
ms.openlocfilehash: 5e1a837578aab4b4609a58ffee46406b022b8f97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587347"
---
# <a name="how-to-draw-lines-with-the-lineshape-control-visual-studio"></a><span data-ttu-id="e48cb-102">방법: LineShape 컨트롤로 선 그리기(Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="e48cb-102">How to: Draw Lines with the LineShape Control (Visual Studio)</span></span>
<span data-ttu-id="e48cb-103">사용할 수 있습니다는 <xref:Microsoft.VisualBasic.PowerPacks.LineShape> 컨트롤을 디자인 타임 및 런타임에 폼 이나 컨테이너에서 가로, 세로 또는 대각선를 그립니다.</span><span class="sxs-lookup"><span data-stu-id="e48cb-103">You can use the <xref:Microsoft.VisualBasic.PowerPacks.LineShape> control to draw horizontal, vertical, or diagonal lines on a form or container, both at design time and at run time.</span></span>  
  
 <span data-ttu-id="e48cb-104">**참고** 컴퓨터 표시 될 수 있습니다 다른 이름 또는 위치가 시스템에 일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에에서 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e48cb-104">**Note** Your computer might show different names or locations for some of the Visual Studio user interface elements in the following instructions.</span></span> <span data-ttu-id="e48cb-105">이러한 요소는 사용하는 Visual Studio 버전 및 설정에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e48cb-105">The Visual Studio edition that you have and the settings that you use determine these elements.</span></span> <span data-ttu-id="e48cb-106">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e48cb-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-draw-a-line-at-design-time"></a><span data-ttu-id="e48cb-107">디자인 타임에 선을 그리려면</span><span class="sxs-lookup"><span data-stu-id="e48cb-107">To draw a line at design time</span></span>  
  
1.  <span data-ttu-id="e48cb-108">끌어는 <xref:Microsoft.VisualBasic.PowerPacks.LineShape> 에서 제어는 **Visual Basic PowerPacks** 탭에 **도구 상자** 폼 이나 컨테이너 컨트롤로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="e48cb-108">Drag the <xref:Microsoft.VisualBasic.PowerPacks.LineShape> control from the **Visual Basic PowerPacks** tab in the **Toolbox** drag to a form or container control.</span></span>  
  
2.  <span data-ttu-id="e48cb-109">크기 조정 끌어서 크기 및 줄 위치에 대 한 핸들을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e48cb-109">Drag the sizing and move handles to size and position the line.</span></span>  
  
     <span data-ttu-id="e48cb-110">크기 조정 하 고 변경 하 여 선을 배치할 수도 있습니다는 `X1`, `X2`, `Y1`, 및 `Y2` 속성에는 **속성** 창.</span><span class="sxs-lookup"><span data-stu-id="e48cb-110">You can also size and position the line by changing the `X1`, `X2`, `Y1`, and `Y2` properties in the **Properties** window.</span></span>  
  
3.  <span data-ttu-id="e48cb-111">에 **속성** 창, 필요에 따라 추가 속성을 설정 같은 `BorderStyle` 또는 `BorderColor` 줄의 모양을 변경 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="e48cb-111">In the **Properties** window, optionally set additional properties such as `BorderStyle` or `BorderColor` to change the appearance of the line.</span></span>  
  
### <a name="to-draw-a-line-at-run-time"></a><span data-ttu-id="e48cb-112">런타임 시 선을 그리려면</span><span class="sxs-lookup"><span data-stu-id="e48cb-112">To draw a line at run time</span></span>  
  
1.  <span data-ttu-id="e48cb-113">**프로젝트** 메뉴에서 **참조 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e48cb-113">On the **Project** menu, click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="e48cb-114">에 **참조 추가** 대화 상자에서 **Microsoft.VisualBasic.PowerPacks.VS**, 클릭 하 고 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="e48cb-114">In the **Add Reference** dialog box, select **Microsoft.VisualBasic.PowerPacks.VS**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="e48cb-115">에 **코드 편집기**, 추가 `Imports` 또는 `using` 모듈 맨 위에 있는 문:</span><span class="sxs-lookup"><span data-stu-id="e48cb-115">In the **Code Editor**, add an `Imports` or `using` statement at the top of the module:</span></span>  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  
  
4.  <span data-ttu-id="e48cb-116">`Event` 프로시저에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e48cb-116">Add the following code in an `Event` procedure:</span></span>  
  
     [!code-csharp[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksLine#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-lines-with-the-lineshape-control-visual-studio_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e48cb-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e48cb-117">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.LineShape>  
 [<span data-ttu-id="e48cb-118">Line 및 Shape 컨트롤 소개</span><span class="sxs-lookup"><span data-stu-id="e48cb-118">Introduction to the Line and Shape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)  
 [<span data-ttu-id="e48cb-119">방법: OvalShape 및 RectangleShape 컨트롤을 사용하여 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="e48cb-119">How to: Draw Shapes with the OvalShape and RectangleShape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)
