---
title: '방법: 빗살 무늬로 도형 채우기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- patterns [Windows Forms], adding to shapes
- shapes [Windows Forms], filling with patterns
- brushes [Windows Forms], using hatch brushes
ms.assetid: 9c8300ff-187b-404f-af1f-ebd499f5b16f
ms.openlocfilehash: 5b6b5b61b83e5be05999099f2cc6b9e715ca35c7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521744"
---
# <a name="how-to-fill-a-shape-with-a-hatch-pattern"></a><span data-ttu-id="dc96e-102">방법: 빗살 무늬로 도형 채우기</span><span class="sxs-lookup"><span data-stu-id="dc96e-102">How to: Fill a Shape with a Hatch Pattern</span></span>
<span data-ttu-id="dc96e-103">빗살 무늬 두 가지 색에서 만들어진: 배경색과 배경 위에 패턴을 형성 하는 줄 하나에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc96e-103">A hatch pattern is made from two colors: one for the background and one for the lines that form the pattern over the background.</span></span> <span data-ttu-id="dc96e-104">빗살 무늬로 닫힌된 셰이프를 채울를 사용 하 여 한 <xref:System.Drawing.Drawing2D.HatchBrush> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="dc96e-104">To fill a closed shape with a hatch pattern, use a <xref:System.Drawing.Drawing2D.HatchBrush> object.</span></span> <span data-ttu-id="dc96e-105">다음 예제에는 빗살 무늬로 타원을 채우는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dc96e-105">The following example demonstrates how to fill an ellipse with a hatch pattern:</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc96e-106">예제</span><span class="sxs-lookup"><span data-stu-id="dc96e-106">Example</span></span>  
 <span data-ttu-id="dc96e-107"><xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> 생성자에는 세 가지 인수: 해치 스타일, 해치 줄의 색 및 배경의 색입니다.</span><span class="sxs-lookup"><span data-stu-id="dc96e-107">The <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> constructor takes three arguments: the hatch style, the color of the hatch line, and the color of the background.</span></span> <span data-ttu-id="dc96e-108">해치 스타일 인수로 사용할 수 있는 모든 값의 <xref:System.Drawing.Drawing2D.HatchStyle> 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="dc96e-108">The hatch style argument can be any value from the <xref:System.Drawing.Drawing2D.HatchStyle> enumeration.</span></span> <span data-ttu-id="dc96e-109">에 50 개 이상의 요소가 <xref:System.Drawing.Drawing2D.HatchStyle> 열거형; 몇 가지 요소는 다음 목록에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc96e-109">There are more than fifty elements in the <xref:System.Drawing.Drawing2D.HatchStyle> enumeration; a few of those elements are shown in the following list:</span></span>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Vertical>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.BackwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Cross>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.DiagonalCross>  
  
 <span data-ttu-id="dc96e-110">다음 그림에서는 채워진된 타원을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dc96e-110">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="dc96e-111">![패턴 해치](../../../../docs/framework/winforms/advanced/media/hatch1.png "hatch1")</span><span class="sxs-lookup"><span data-stu-id="dc96e-111">![Hatch Pattern](../../../../docs/framework/winforms/advanced/media/hatch1.png "hatch1")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dc96e-112">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="dc96e-112">Compiling the Code</span></span>  
 <span data-ttu-id="dc96e-113">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs> 이벤트 처리기의 매개 변수인 `e`<xref:System.Windows.Forms.Control.Paint>가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="dc96e-113">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc96e-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc96e-114">See Also</span></span>  
 [<span data-ttu-id="dc96e-115">브러시를 사용하여 도형 채우기</span><span class="sxs-lookup"><span data-stu-id="dc96e-115">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
