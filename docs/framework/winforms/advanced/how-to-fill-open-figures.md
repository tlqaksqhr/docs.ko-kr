---
title: "방법: 열린 그림 채우기"
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
- open figures [Windows Forms], filling
- figures [Windows Forms], filling
ms.assetid: 5a36b0e4-f1f4-46c0-a85a-22ae98491950
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7a8a2d5a13cac97063bf2a04969928c859a5954d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-fill-open-figures"></a><span data-ttu-id="94fd7-102">방법: 열린 그림 채우기</span><span class="sxs-lookup"><span data-stu-id="94fd7-102">How to: Fill Open Figures</span></span>
<span data-ttu-id="94fd7-103">전달 하 여 경로 채울 수는 <xref:System.Drawing.Drawing2D.GraphicsPath> 개체는 <xref:System.Drawing.Graphics.FillPath%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="94fd7-103">You can fill a path by passing a <xref:System.Drawing.Drawing2D.GraphicsPath> object to the <xref:System.Drawing.Graphics.FillPath%2A> method.</span></span> <span data-ttu-id="94fd7-104"><xref:System.Drawing.Graphics.FillPath%2A> 메서드는 현재 경로 대해 설정 된 채우기 모드 (대체 또는 굴곡)에 따라 경로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="94fd7-104">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the path according to the fill mode (alternate or winding) currently set for the path.</span></span> <span data-ttu-id="94fd7-105">경로 열린 그림이, 경로 해당 종료 된 경우에 따라 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="94fd7-105">If the path has any open figures, the path is filled as if those figures were closed.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="94fd7-106">시작 점으로 끝점에서 직선 그리기 하 여 그림을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="94fd7-106"> closes a figure by drawing a straight line from its ending point to its starting point.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94fd7-107">예제</span><span class="sxs-lookup"><span data-stu-id="94fd7-107">Example</span></span>  
 <span data-ttu-id="94fd7-108">다음 예제에는 하나의 열린 그림 (호) 및 하나의 폐쇄형된 도형 (: 타원)에 포함 된 경로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="94fd7-108">The following example creates a path that has one open figure (an arc) and one closed figure (an ellipse).</span></span> <span data-ttu-id="94fd7-109"><xref:System.Drawing.Graphics.FillPath%2A> 채워지는 기본 채우기 모드, 즉에 따라 경로 <xref:System.Drawing.Drawing2D.FillMode.Alternate>합니다.</span><span class="sxs-lookup"><span data-stu-id="94fd7-109">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the path according to the default fill mode, which is <xref:System.Drawing.Drawing2D.FillMode.Alternate>.</span></span>  
  
 <span data-ttu-id="94fd7-110">다음 그림에서는 예제 코드의 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="94fd7-110">The following illustration shows the output of the example code.</span></span> <span data-ttu-id="94fd7-111">경로가 입력 됩니다 (에 따라 <xref:System.Drawing.Drawing2D.FillMode.Alternate>) 열린 그림을 시작 점으로 끝점에서 직선으로 종료 된 경우에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="94fd7-111">Note that the path is filled (according to <xref:System.Drawing.Drawing2D.FillMode.Alternate>) as if the open figure were closed by a straight line from its ending point to its starting point.</span></span>  
  
 <span data-ttu-id="94fd7-112">![열린 경로 채우기](../../../../docs/framework/winforms/advanced/media/fillopenpath.png "FillOpenPath")</span><span class="sxs-lookup"><span data-stu-id="94fd7-112">![Fill Open Path](../../../../docs/framework/winforms/advanced/media/fillopenpath.png "FillOpenPath")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="94fd7-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="94fd7-113">Compiling the Code</span></span>  
 <span data-ttu-id="94fd7-114">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="94fd7-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94fd7-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="94fd7-115">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.GraphicsPath>  
 [<span data-ttu-id="94fd7-116">GDI+의 그래픽 경로</span><span class="sxs-lookup"><span data-stu-id="94fd7-116">Graphics Paths in GDI+</span></span>](../../../../docs/framework/winforms/advanced/graphics-paths-in-gdi.md)
