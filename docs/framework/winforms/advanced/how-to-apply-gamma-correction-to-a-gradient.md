---
title: "방법: 그라데이션에 감마 보정 적용"
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
- gradient brushes [Windows Forms], gamma correction
- gradients [Windows Forms], gamma correction
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2721a45381f2d0befe82d6d0db2630f3eae08d51
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a><span data-ttu-id="b3c41-102">방법: 그라데이션에 감마 보정 적용</span><span class="sxs-lookup"><span data-stu-id="b3c41-102">How to: Apply Gamma Correction to a Gradient</span></span>
<span data-ttu-id="b3c41-103">브러시의 설정 하 여 선형 그라데이션 브러시에 대 한 감마 보정을 사용 하도록 설정할 수 있습니다 <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c41-103">You can enable gamma correction for a linear gradient brush by setting the brush's <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `true`.</span></span> <span data-ttu-id="b3c41-104">감마 보정을 사용 하지 않도록 설정 하 여 수는 <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> 속성을 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c41-104">You can disable gamma correction by setting the <xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A> property to `false`.</span></span> <span data-ttu-id="b3c41-105">감마 보정은 기본적으로 비활성화 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3c41-105">Gamma correction is disabled by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3c41-106">예제</span><span class="sxs-lookup"><span data-stu-id="b3c41-106">Example</span></span>  
 <span data-ttu-id="b3c41-107">선형 그라데이션 브러시를 만들고 해당 브러시를 사용 하 여 두 개의 사각형에 맞게는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="b3c41-107">The example creates a linear gradient brush and uses that brush to fill two rectangles.</span></span> <span data-ttu-id="b3c41-108">첫 번째 사각형 감마 보정 하지 않고 채워지고 두 번째 사각형 감마 보정 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="b3c41-108">The first rectangle is filled without gamma correction, and the second rectangle is filled with gamma correction.</span></span>  
  
 <span data-ttu-id="b3c41-109">다음 그림에서는 두 개의 채워진된 사각형을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b3c41-109">The following illustration shows the two filled rectangles.</span></span> <span data-ttu-id="b3c41-110">감마 보정 없는 위쪽 사각형 중간에 어두운 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="b3c41-110">The top rectangle, which does not have gamma correction, appears dark in the middle.</span></span> <span data-ttu-id="b3c41-111">감마 보정 있는 아래 사각형 농도가 좀 더 균일에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="b3c41-111">The bottom rectangle, which has gamma correction, appears to have more uniform intensity.</span></span>  
  
 <span data-ttu-id="b3c41-112">![그라데이션](../../../../docs/framework/winforms/advanced/media/gammagradient1.png "gammagradient1")</span><span class="sxs-lookup"><span data-stu-id="b3c41-112">![Gradient](../../../../docs/framework/winforms/advanced/media/gammagradient1.png "gammagradient1")</span></span>  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b3c41-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="b3c41-113">Compiling the Code</span></span>  
 <span data-ttu-id="b3c41-114">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b3c41-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3c41-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b3c41-115">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush>  
 [<span data-ttu-id="b3c41-116">그라데이션 브러시를 사용하여 도형 채우기</span><span class="sxs-lookup"><span data-stu-id="b3c41-116">Using a Gradient Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-gradient-brush-to-fill-shapes.md)
