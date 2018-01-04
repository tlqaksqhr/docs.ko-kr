---
title: "방법: 이미지 질감으로 도형 채우기"
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
- images [Windows Forms], using with brushes
- bitmaps [Windows Forms], using texture
- shapes [Windows Forms], filling with images
ms.assetid: 508da5a6-2433-4d2b-9680-eaeae4e96e3b
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7b5ef87762b08daa973237e7b3da1068640e08bd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-fill-a-shape-with-an-image-texture"></a><span data-ttu-id="5865d-102">방법: 이미지 질감으로 도형 채우기</span><span class="sxs-lookup"><span data-stu-id="5865d-102">How to: Fill a Shape with an Image Texture</span></span>
<span data-ttu-id="5865d-103">사용 하 여 질감으로 닫힌된 셰이프를 채울 수 있습니다는 <xref:System.Drawing.Image> 클래스 및 <xref:System.Drawing.TextureBrush> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="5865d-103">You can fill a closed shape with a texture by using the <xref:System.Drawing.Image> class and the <xref:System.Drawing.TextureBrush> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5865d-104">예</span><span class="sxs-lookup"><span data-stu-id="5865d-104">Example</span></span>  
 <span data-ttu-id="5865d-105">다음 예제에서는 이미지와 함께 타원을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="5865d-105">The following example fills an ellipse with an image.</span></span> <span data-ttu-id="5865d-106">코드를 생성 한 <xref:System.Drawing.Image> 개체를 다음의 주소를 전달 <xref:System.Drawing.Image> 개체에 대 한 인수로 <xref:System.Drawing.TextureBrush.%23ctor%2A> 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="5865d-106">The code constructs an <xref:System.Drawing.Image> object, and then passes the address of that <xref:System.Drawing.Image> object as an argument to a <xref:System.Drawing.TextureBrush.%23ctor%2A> constructor.</span></span> <span data-ttu-id="5865d-107">세 번째 문은 이미지, 크기를 조정 하 고 네 번째 문에서 조정 된 이미지의 반복된 복사본을 사용 하 여 타원을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="5865d-107">The third statement scales the image, and the fourth statement fills the ellipse with repeated copies of the scaled image.</span></span>  
  
 <span data-ttu-id="5865d-108">다음 코드에서는 <xref:System.Drawing.TextureBrush.Transform%2A> 속성을 그리기 전에 이미지에 적용 하는 변환에 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="5865d-108">In the following code, the <xref:System.Drawing.TextureBrush.Transform%2A> property contains the transformation that is applied to the image before it is drawn.</span></span> <span data-ttu-id="5865d-109">원본 이미지에는의 640 픽셀 너비와 높이는 480 픽셀을 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5865d-109">Assume that the original image has a width of 640 pixels and a height of 480 pixels.</span></span> <span data-ttu-id="5865d-110">이미지를 75 × 75 가로 및 세로 크기 조정 값을 설정 하 여 축소 하는 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5865d-110">The transform shrinks the image to 75×75 by setting the horizontal and vertical scaling values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5865d-111">다음 예제에서는 이미지 크기 × 75, 75 이며 타원 크기는 150 × 250 합니다.</span><span class="sxs-lookup"><span data-stu-id="5865d-111">In the following example, the image size is 75×75, and the ellipse size is 150×250.</span></span> <span data-ttu-id="5865d-112">채울 타원 보다 작은 이미지 이므로 타원 이미지와 바둑판식으로 배열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5865d-112">Because the image is smaller than the ellipse it is filling, the ellipse is tiled with the image.</span></span> <span data-ttu-id="5865d-113">이미지 가로 및 세로로 도형의 경계까지 반복 되도록 의미를 바둑판식으로 배열에 도달 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5865d-113">Tiling means that the image is repeated horizontally and vertically until the boundary of the shape is reached.</span></span> <span data-ttu-id="5865d-114">바둑판식 배열에 대 한 자세한 내용은 참조 [하는 방법: 도형에 이미지를 바둑판식으로 배열](../../../../docs/framework/winforms/advanced/how-to-tile-a-shape-with-an-image.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5865d-114">For more information about tiling, see [How to: Tile a Shape with an Image](../../../../docs/framework/winforms/advanced/how-to-tile-a-shape-with-an-image.md).</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5865d-115">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="5865d-115">Compiling the Code</span></span>  
 <span data-ttu-id="5865d-116">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5865d-116">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5865d-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5865d-117">See Also</span></span>  
 [<span data-ttu-id="5865d-118">브러시를 사용하여 도형 채우기</span><span class="sxs-lookup"><span data-stu-id="5865d-118">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
