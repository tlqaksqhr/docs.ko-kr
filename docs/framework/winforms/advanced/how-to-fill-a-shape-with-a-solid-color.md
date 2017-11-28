---
title: "방법: 단색으로 도형 채우기"
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
- colors [Windows Forms], adding to shapes
- shapes [Windows Forms], filling
ms.assetid: 06088b31-bac9-4ef3-9ebe-06c2c764d6df
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: eb3e160392a903083386d9942f8e2cfe31ee89a4
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-fill-a-shape-with-a-solid-color"></a><span data-ttu-id="4a4aa-102">방법: 단색으로 도형 채우기</span><span class="sxs-lookup"><span data-stu-id="4a4aa-102">How to: Fill a Shape with a Solid Color</span></span>
<span data-ttu-id="4a4aa-103">만들기를 단색으로 도형 채우기는 <xref:System.Drawing.SolidBrush> 개체를 다음 전달할 <xref:System.Drawing.SolidBrush> 개체의 채우기 메서드 중 하나에 대 한 인수로 <xref:System.Drawing.Graphics> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4a4aa-103">To fill a shape with a solid color, create a <xref:System.Drawing.SolidBrush> object, and then pass that <xref:System.Drawing.SolidBrush> object as an argument to one of the fill methods of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="4a4aa-104">다음 예제에서는 빨간색으로 타원을 채우는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4a4aa-104">The following example shows how to fill an ellipse with the color red.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a4aa-105">예제</span><span class="sxs-lookup"><span data-stu-id="4a4aa-105">Example</span></span>  
 <span data-ttu-id="4a4aa-106">다음 코드에서는 <xref:System.Drawing.SolidBrush.%23ctor%2A> 생성자는 <xref:System.Drawing.Color> 인수로 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4a4aa-106">In the following code, the <xref:System.Drawing.SolidBrush.%23ctor%2A> constructor takes a <xref:System.Drawing.Color> object as its only argument.</span></span> <span data-ttu-id="4a4aa-107">사용 되는 값은 <xref:System.Drawing.Color.FromArgb%2A> 메서드 색의 알파, 빨간색, 녹색 및 파랑 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4a4aa-107">The values used by the <xref:System.Drawing.Color.FromArgb%2A> method represent the alpha, red, green, and blue components of the color.</span></span> <span data-ttu-id="4a4aa-108">이러한 값을 각각 0-255 사이에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4aa-108">Each of these values must be in the range 0 through 255.</span></span> <span data-ttu-id="4a4aa-109">첫 번째 255 나타내며 색은 완전히 불투명 한 두 번째 255 빨강 구성 요소의 농도가 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4a4aa-109">The first 255 indicates that the color is fully opaque, and the second 255 indicates that the red component is at full intensity.</span></span> <span data-ttu-id="4a4aa-110">두 개의 0 있는지 녹색 및 파랑 구성 요소 둘 다가 0의 강도 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4a4aa-110">The two zeros indicate that the green and blue components both have an intensity of 0.</span></span>  
  
 <span data-ttu-id="4a4aa-111">4 개의 숫자 (0, 0, 100, 60)에 전달 되는 <xref:System.Drawing.Graphics.FillEllipse%2A> 메서드는 타원에 대 한 경계 사각형의 크기와 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4aa-111">The four numbers (0, 0, 100, 60) passed to the <xref:System.Drawing.Graphics.FillEllipse%2A> method specify the location and size of the bounding rectangle for the ellipse.</span></span> <span data-ttu-id="4a4aa-112">사각형의 왼쪽 위 모퉁이 (0, 0), 100, 너비 및 높이 60입니다.</span><span class="sxs-lookup"><span data-stu-id="4a4aa-112">The rectangle has an upper-left corner of (0, 0), a width of 100, and a height of 60.</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingABrush#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4a4aa-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="4a4aa-113">Compiling the Code</span></span>  
 <span data-ttu-id="4a4aa-114">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4a4aa-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a4aa-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4a4aa-115">See Also</span></span>  
 [<span data-ttu-id="4a4aa-116">브러시를 사용하여 도형 채우기</span><span class="sxs-lookup"><span data-stu-id="4a4aa-116">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
