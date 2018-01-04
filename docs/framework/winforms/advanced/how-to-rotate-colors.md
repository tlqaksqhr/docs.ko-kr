---
title: "방법: 색 회전"
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
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 81b022011bd5613b8e956aa83482d2836508a4f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-rotate-colors"></a><span data-ttu-id="b3e69-102">방법: 색 회전</span><span class="sxs-lookup"><span data-stu-id="b3e69-102">How to: Rotate Colors</span></span>
<span data-ttu-id="b3e69-103">4 차원 색 공간에서 회전 시각화 하기 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="b3e69-103">Rotation in a four-dimensional color space is difficult to visualize.</span></span> <span data-ttu-id="b3e69-104">동의 고정 색상 구성 요소 중 하나를 유지 하는 것으로 회전 시각화할 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3e69-104">We can make it easier to visualize rotation by agreeing to keep one of the color components fixed.</span></span> <span data-ttu-id="b3e69-105">1 자리 알파 구성 요소 (완전히 불투명 함)을 유지 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e69-105">Suppose we agree to keep the alpha component fixed at 1 (fully opaque).</span></span> <span data-ttu-id="b3e69-106">다음 다음 그림에 나와 있는 것 처럼 빨간색, 녹색 및 파란색 축이 있는 3 차원 색 공간을 시각화할 수 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b3e69-106">Then we can visualize a three-dimensional color space with red, green, and blue axes as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="b3e69-107">![다시 칠하기](../../../../docs/framework/winforms/advanced/media/recoloring03.gif "recoloring03")</span><span class="sxs-lookup"><span data-stu-id="b3e69-107">![Recoloring](../../../../docs/framework/winforms/advanced/media/recoloring03.gif "recoloring03")</span></span>  
  
 <span data-ttu-id="b3e69-108">색 3 차원 공간에서 지점으로 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3e69-108">A color can be thought of as a point in 3-D space.</span></span> <span data-ttu-id="b3e69-109">예를 들어 공간에서 지점 (1, 0, 0) 빨강을 나타내고 녹색 공간에서 지점 (0, 1, 0)을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b3e69-109">For example, the point (1, 0, 0) in space represents the color red, and the point (0, 1, 0) in space represents the color green.</span></span>  
  
 <span data-ttu-id="b3e69-110">다음 그림은 빨강-녹색 평면에서 60도의 각도 통해 (1, 0, 0) 색 회전 하는 의미를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b3e69-110">The following illustration shows what it means to rotate the color (1, 0, 0) through an angle of 60 degrees in the Red-Green plane.</span></span> <span data-ttu-id="b3e69-111">빨간색-녹색 평면과 평면 병렬로 회전 파란색 축을 중심으로 회전으로 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3e69-111">Rotation in a plane parallel to the Red-Green plane can be thought of as rotation about the blue axis.</span></span>  
  
 <span data-ttu-id="b3e69-112">![다시 칠하기](../../../../docs/framework/winforms/advanced/media/recoloring04.gif "recoloring04")</span><span class="sxs-lookup"><span data-stu-id="b3e69-112">![Recoloring](../../../../docs/framework/winforms/advanced/media/recoloring04.gif "recoloring04")</span></span>  
  
 <span data-ttu-id="b3e69-113">다음 그림에는 각각 세 개의 좌표 축 (빨강, 녹색, 파랑)을 중심으로 회전에 색 매트릭스를 초기화 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b3e69-113">The following illustration shows how to initialize a color matrix to perform rotations about each of the three coordinate axes (red, green, blue).</span></span>  
  
 <span data-ttu-id="b3e69-114">![다시 칠하기](../../../../docs/framework/winforms/advanced/media/recoloring05.gif "recoloring05")</span><span class="sxs-lookup"><span data-stu-id="b3e69-114">![Recoloring](../../../../docs/framework/winforms/advanced/media/recoloring05.gif "recoloring05")</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3e69-115">예</span><span class="sxs-lookup"><span data-stu-id="b3e69-115">Example</span></span>  
 <span data-ttu-id="b3e69-116">다음 예제에서는 (1, 0, 0.6) 모두 같은 색 이므로 파란색 축에 대 한 60도 회전을 적용 하는 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e69-116">The following example takes an image that is all one color (1, 0, 0.6) and applies a 60-degree rotation about the blue axis.</span></span> <span data-ttu-id="b3e69-117">회전 각도 빨간색-녹색 평면과 평행 하는 평면에 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="b3e69-117">The angle of the rotation is swept out in a plane that is parallel to the red-green plane.</span></span>  
  
 <span data-ttu-id="b3e69-118">다음 그림에서는 왼쪽 및 오른쪽에 있는 색 회전 이미지에 원본 이미지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b3e69-118">The following illustration shows the original image on the left and the color-rotated image on the right.</span></span>  
  
 <span data-ttu-id="b3e69-119">![색 회전](../../../../docs/framework/winforms/advanced/media/colortrans5.png "colortrans5")</span><span class="sxs-lookup"><span data-stu-id="b3e69-119">![Rotate Colors](../../../../docs/framework/winforms/advanced/media/colortrans5.png "colortrans5")</span></span>  
  
 <span data-ttu-id="b3e69-120">다음 그림에서는 다음 코드에서 수행 되는 색 회전의 시각화를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b3e69-120">The following illustration shows a visualization of the color rotation performed in the following code.</span></span>  
  
 <span data-ttu-id="b3e69-121">![다시 칠하기](../../../../docs/framework/winforms/advanced/media/recoloring06.gif "recoloring06")</span><span class="sxs-lookup"><span data-stu-id="b3e69-121">![Recoloring](../../../../docs/framework/winforms/advanced/media/recoloring06.gif "recoloring06")</span></span>  
  
 [!code-csharp[System.Drawing.RotateColors#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b3e69-122">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="b3e69-122">Compiling the Code</span></span>  
 <span data-ttu-id="b3e69-123">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs> 이벤트 처리기의 매개 변수인 `e`<xref:System.Windows.Forms.Control.Paint>가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e69-123">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="b3e69-124">대체 `RotationInput.bmp` 있는 이미지 파일 이름 및 경로 시스템에서 사용할 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e69-124">Replace `RotationInput.bmp` with an image file name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3e69-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b3e69-125">See Also</span></span>  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [<span data-ttu-id="b3e69-126">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="b3e69-126">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="b3e69-127">이미지 다시 칠하기</span><span class="sxs-lookup"><span data-stu-id="b3e69-127">Recoloring Images</span></span>](../../../../docs/framework/winforms/advanced/recoloring-images.md)
