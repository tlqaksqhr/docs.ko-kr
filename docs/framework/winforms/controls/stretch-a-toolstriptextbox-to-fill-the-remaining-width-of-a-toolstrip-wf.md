---
title: '방법: ToolStripTextBox를 늘려 ToolStrip의 나머지 너비 채우기(Windows Forms)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text boxes [Windows Forms], stretching in ToolStrip control [Windows Forms]
- ToolStrip control [Windows Forms], stretching a text box
ms.assetid: 0e610fbf-85fe-414c-900c-9704a5dd5cc6
ms.openlocfilehash: bd58cbd109b8e3dd04c6a284dc6926e95830fb61
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537722"
---
# <a name="how-to-stretch-a-toolstriptextbox-to-fill-the-remaining-width-of-a-toolstrip-windows-forms"></a><span data-ttu-id="bf78f-102">방법: ToolStripTextBox를 늘려 ToolStrip의 나머지 너비 채우기(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="bf78f-102">How to: Stretch a ToolStripTextBox to Fill the Remaining Width of a ToolStrip (Windows Forms)</span></span>
<span data-ttu-id="bf78f-103">설정 하는 경우는 <xref:System.Windows.Forms.ToolStrip.Stretch%2A> 속성의는 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 `true`, 해당 컨테이너를 끝까지 채웁니다 컨트롤과 해당 컨테이너 크기를 조정할 때의 크기를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf78f-103">When you set the <xref:System.Windows.Forms.ToolStrip.Stretch%2A> property of a <xref:System.Windows.Forms.ToolStrip> control to `true`, the control fills its container from end to end, and resizes when its container resizes.</span></span> <span data-ttu-id="bf78f-104">이 구성에서는 하면 유용할 수와 같은 컨트롤에서 항목을 스트레치 하는 <xref:System.Windows.Forms.ToolStripTextBox>, 사용 가능한 공간 및 컨트롤 크기를 조정할 때의 크기를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf78f-104">In this configuration, you may find it useful to stretch an item in the control, such as a <xref:System.Windows.Forms.ToolStripTextBox>, to fill the available space and to resize when the control resizes.</span></span> <span data-ttu-id="bf78f-105">이러한 늘이기, 예를 들어 경우 유용 모양 및 동작 Microsoft® Internet Explorer의 주소 표시줄 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf78f-105">This stretching is useful, for example, if you want to achieve appearance and behavior similar to the address bar in Microsoft® Internet Explorer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf78f-106">예제</span><span class="sxs-lookup"><span data-stu-id="bf78f-106">Example</span></span>  
 <span data-ttu-id="bf78f-107">파생 된 클래스를 제공 하는 다음 코드 예제에서는 <xref:System.Windows.Forms.ToolStripTextBox> 호출 `ToolStripSpringTextBox`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf78f-107">The following code example provides a class derived from <xref:System.Windows.Forms.ToolStripTextBox> called `ToolStripSpringTextBox`.</span></span> <span data-ttu-id="bf78f-108">이 클래스는 재정의 <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> 부모의 사용 가능한 너비를 계산 하는 메서드 <xref:System.Windows.Forms.ToolStrip> 후 다른 모든 항목의 결합 된 너비를 뺀 값을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf78f-108">This class overrides the <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A> method to calculate the available width of the parent <xref:System.Windows.Forms.ToolStrip> control after the combined width of all other items has been subtracted.</span></span> <span data-ttu-id="bf78f-109">이 코드 예제도 제공 합니다. 한 <xref:System.Windows.Forms.Form> 클래스 및 `Program` 클래스 새 동작을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bf78f-109">This code example also provides a <xref:System.Windows.Forms.Form> class and a `Program` class to demonstrate the new behavior.</span></span>  
  
 [!code-csharp[ToolStripSpringTextBox#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripSpringTextBox/cs/ToolStripSpringTextBox.cs#00)]
 [!code-vb[ToolStripSpringTextBox#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripSpringTextBox/vb/ToolStripSpringTextBox.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bf78f-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="bf78f-110">Compiling the Code</span></span>  
 <span data-ttu-id="bf78f-111">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bf78f-111">This example requires:</span></span>  
  
-   <span data-ttu-id="bf78f-112">System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="bf78f-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf78f-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bf78f-113">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStrip.Stretch%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripTextBox>  
 <xref:System.Windows.Forms.ToolStripTextBox.GetPreferredSize%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="bf78f-114">ToolStrip 컨트롤 아키텍처</span><span class="sxs-lookup"><span data-stu-id="bf78f-114">ToolStrip Control Architecture</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [<span data-ttu-id="bf78f-115">방법: StatusStrip에서 대화형으로 Spring 속성 사용</span><span class="sxs-lookup"><span data-stu-id="bf78f-115">How to: Use the Spring Property Interactively in a StatusStrip</span></span>](../../../../docs/framework/winforms/controls/how-to-use-the-spring-property-interactively-in-a-statusstrip.md)
