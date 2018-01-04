---
title: "방법: 펜을 사용하여 선 그리기"
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
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
ms.assetid: 0828c331-a438-4bdd-a4d6-3ef1e59e8795
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 156d7acbbf3f863e89ae2a5c303b2cf4140b3592
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-pen-to-draw-lines"></a><span data-ttu-id="a3249-102">방법: 펜을 사용하여 선 그리기</span><span class="sxs-lookup"><span data-stu-id="a3249-102">How to: Use a Pen to Draw Lines</span></span>
<span data-ttu-id="a3249-103">필요한 줄을 그리려면는 <xref:System.Drawing.Graphics> 개체 및 <xref:System.Drawing.Pen> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a3249-103">To draw lines, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="a3249-104"><xref:System.Drawing.Graphics> 개체를 제공는 <xref:System.Drawing.Graphics.DrawLine%2A> 메서드, 및 <xref:System.Drawing.Pen> 개체 선의 색 및 너비와 같은 기능을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3249-104">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawLine%2A> method, and the <xref:System.Drawing.Pen> object stores features of the line, such as color and width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3249-105">예</span><span class="sxs-lookup"><span data-stu-id="a3249-105">Example</span></span>  
 <span data-ttu-id="a3249-106">다음 예제에서 선을 그립니다 (20, 10)에 (300, 100).</span><span class="sxs-lookup"><span data-stu-id="a3249-106">The following example draws a line from (20, 10) to (300, 100).</span></span> <span data-ttu-id="a3249-107">첫 번째 문은 사용 하 여는 <xref:System.Drawing.Pen.%23ctor%2A> 클래스 생성자 검정 펜을 만들려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3249-107">The first statement uses the <xref:System.Drawing.Pen.%23ctor%2A> class constructor to create a black pen.</span></span> <span data-ttu-id="a3249-108">에 전달 되는 하나의 인수는 <xref:System.Drawing.Pen.%23ctor%2A> 생성자는 한 <xref:System.Drawing.Color> 사용 하 여 만든 개체는 <xref:System.Drawing.Color.FromArgb%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="a3249-108">The one argument passed to the <xref:System.Drawing.Pen.%23ctor%2A> constructor is a <xref:System.Drawing.Color> object created with the <xref:System.Drawing.Color.FromArgb%2A> method.</span></span> <span data-ttu-id="a3249-109">만드는 데 사용 되는 값은 <xref:System.Drawing.Color> 개체-(255, 0, 0, 0)-색의 알파, 빨간색, 녹색 및 파랑 구성 요소에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3249-109">The values used to create the <xref:System.Drawing.Color> object — (255, 0, 0, 0) — correspond to the alpha, red, green, and blue components of the color.</span></span> <span data-ttu-id="a3249-110">이러한 값에는 불투명 한 검정색 펜을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a3249-110">These values define an opaque black pen.</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a3249-111">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="a3249-111">Compiling the Code</span></span>  
 <span data-ttu-id="a3249-112">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs> 이벤트 처리기의 매개 변수인 `e`<xref:System.Windows.Forms.Control.Paint>가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a3249-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3249-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a3249-113">See Also</span></span>  
 <xref:System.Drawing.Pen>  
 [<span data-ttu-id="a3249-114">펜을 사용하여 선과 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="a3249-114">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [<span data-ttu-id="a3249-115">GDI+의 펜, 선 및 사각형</span><span class="sxs-lookup"><span data-stu-id="a3249-115">Pens, Lines, and Rectangles in GDI+</span></span>](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
