---
title: "방법: 펜 색 설정"
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
helpviewer_keywords:
- pens [Windows Forms], setting color
- colored pens
ms.assetid: a9df06f9-a6d5-4d9b-a2d1-583943540775
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 66527be5a70f9c7c60f4ca3836ee68b96872442f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-color-of-a-pen"></a><span data-ttu-id="34031-102">방법: 펜 색 설정</span><span class="sxs-lookup"><span data-stu-id="34031-102">How to: Set the Color of a Pen</span></span>
<span data-ttu-id="34031-103">기존의 색을 변경 하는이 예제 <xref:System.Drawing.Pen> 개체</span><span class="sxs-lookup"><span data-stu-id="34031-103">This example changes the color of a pre-existing <xref:System.Drawing.Pen> object</span></span>  
  
## <a name="example"></a><span data-ttu-id="34031-104">예</span><span class="sxs-lookup"><span data-stu-id="34031-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#9)]
 [!code-csharp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#9)]
 [!code-vb[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="34031-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="34031-105">Compiling the Code</span></span>  
 <span data-ttu-id="34031-106">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="34031-106">This example requires:</span></span>  
  
-   <span data-ttu-id="34031-107">A <xref:System.Drawing.Pen> 라는 개체 `myPen`합니다.</span><span class="sxs-lookup"><span data-stu-id="34031-107">A <xref:System.Drawing.Pen> object named `myPen`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="34031-108">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="34031-108">Robust Programming</span></span>  
 <span data-ttu-id="34031-109">호출 해야 <xref:System.Drawing.Pen.Dispose%2A> 시스템 리소스를 사용 하는 개체에 (같은 <xref:System.Drawing.Pen> 개체)을 사용 하 여 완료 한 후 합니다.</span><span class="sxs-lookup"><span data-stu-id="34031-109">You should call <xref:System.Drawing.Pen.Dispose%2A> on objects that consume system resources (such as <xref:System.Drawing.Pen> objects) after you are finished using them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34031-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="34031-110">See Also</span></span>  
 <xref:System.Drawing.Pen>  
 [<span data-ttu-id="34031-111">그래픽 프로그래밍 시작</span><span class="sxs-lookup"><span data-stu-id="34031-111">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="34031-112">방법: 펜 만들기</span><span class="sxs-lookup"><span data-stu-id="34031-112">How to: Create a Pen</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)  
 [<span data-ttu-id="34031-113">펜을 사용하여 선과 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="34031-113">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [<span data-ttu-id="34031-114">GDI+의 펜, 선 및 사각형</span><span class="sxs-lookup"><span data-stu-id="34031-114">Pens, Lines, and Rectangles in GDI+</span></span>](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
