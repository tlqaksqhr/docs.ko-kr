---
title: "방법: 도형 간 탭 이동 사용(Visual Studio)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Line control [Visual Basic], implementing tabbing
- Shape control [Visual Basic], implementing tabbing
ms.assetid: 09731b34-3900-4fcb-a9df-ce5280328433
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0b1e8b0378e65becd80324491632ecd8dbffdbbf
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-enable-tabbing-between-shapes-visual-studio"></a><span data-ttu-id="0404a-102">방법: 도형 간 탭 이동 사용(Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="0404a-102">How to: Enable Tabbing Between Shapes (Visual Studio)</span></span>
<span data-ttu-id="0404a-103">Line 및 shape 컨트롤 `TabStop` 또는 `TabIndex` 있지만 속성을 계속 사용할 수 있습니다 그중에서 탭 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0404a-103">Line and shape controls do not have `TabStop` or `TabIndex` properties, but you can still enable tabbing among them.</span></span> <span data-ttu-id="0404a-104">다음 예제에서는 도형; 간에 탭은 CTRL과 탭 키를 누르면 단추 사이만 TAB 키를 누를 tab 합니다.</span><span class="sxs-lookup"><span data-stu-id="0404a-104">In the following example, pressing both the CTRL and the TAB keys will tab between shapes; pressing only the TAB key will tab between the buttons.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0404a-105">일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0404a-105">Your computer might show different names or locations for some of the Visual Studio user interface elements in the following instructions.</span></span> <span data-ttu-id="0404a-106">이러한 요소는 사용하는 Visual Studio 버전 및 설정에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0404a-106">The Visual Studio edition that you have and the settings that you use determine these elements.</span></span> <span data-ttu-id="0404a-107">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0404a-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="to-enable-tabbing-among-shapes"></a><span data-ttu-id="0404a-108">도형 간 탭 이동 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="0404a-108">To enable tabbing among shapes</span></span>  
  
1.  <span data-ttu-id="0404a-109">세 개의 끌어 <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> 컨트롤과 두 개의 <xref:System.Windows.Forms.Button> 에서 제어는 **도구 상자** 폼에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0404a-109">Drag three <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> controls and two <xref:System.Windows.Forms.Button> controls from the **Toolbox** to a form.</span></span>  
  
2.  <span data-ttu-id="0404a-110">에 **코드 편집기**, 추가 `Imports` 또는 `using` 모듈 맨 위에 있는 문:</span><span class="sxs-lookup"><span data-stu-id="0404a-110">In the **Code Editor**, add an `Imports` or `using` statement at the top of the module:</span></span>  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  

3.  <span data-ttu-id="0404a-111">이벤트 프로시저에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0404a-111">Add the following code in an event procedure:</span></span>  
  
[!code-csharp[VbPowerPacksTabbing#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-enable-tabbing-between-shapes-visual-studio_1.cs)]
[!code-vb[VbPowerPacksTabbing#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-enable-tabbing-between-shapes-visual-studio_1.vb)]  
  
4.  <span data-ttu-id="0404a-112">다음 코드에 추가 `Button1_PreviewKeyDown` 이벤트 프로시저:</span><span class="sxs-lookup"><span data-stu-id="0404a-112">Add the following code in the `Button1_PreviewKeyDown` event procedure:</span></span>  
  
[!code-csharp[VbPowerPacksTabbing#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-enable-tabbing-between-shapes-visual-studio_2.cs)]
[!code-vb[VbPowerPacksTabbing#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-enable-tabbing-between-shapes-visual-studio_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="0404a-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0404a-113">See Also</span></span>  
 [<span data-ttu-id="0404a-114">방법: OvalShape 및 RectangleShape 컨트롤을 사용하여 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="0404a-114">How to: Draw Shapes with the OvalShape and RectangleShape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)  
 [<span data-ttu-id="0404a-115">방법: LineShape 컨트롤로 선 그리기</span><span class="sxs-lookup"><span data-stu-id="0404a-115">How to: Draw Lines with the LineShape Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)  
 [<span data-ttu-id="0404a-116">Line 및 Shape 컨트롤 소개</span><span class="sxs-lookup"><span data-stu-id="0404a-116">Introduction to the Line and Shape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)
