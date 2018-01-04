---
title: "방법: 색 매핑 변경 테이블 사용"
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
- color tables [Windows Forms], remapping colors with
- custom colors [Windows Forms], creating with color remap table
- color remap tables [Windows Forms], using
ms.assetid: 977df1ce-8665-42d4-9fb1-ef7f0ff63419
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6e208aa9c98c1ca19baee83760cfd0f75972ecfa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-color-remap-table"></a><span data-ttu-id="3d6f2-102">방법: 색 매핑 변경 테이블 사용</span><span class="sxs-lookup"><span data-stu-id="3d6f2-102">How to: Use a Color Remap Table</span></span>
<span data-ttu-id="3d6f2-103">다시 매핑하는 색 다시 매핑 테이블에 따라 이미지의 색을 변환의 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="3d6f2-103">Remapping is the process of converting the colors in an image according to a color remap table.</span></span> <span data-ttu-id="3d6f2-104">색 매핑 변경 테이블은 배열을 <xref:System.Drawing.Imaging.ColorMap> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3d6f2-104">The color remap table is an array of <xref:System.Drawing.Imaging.ColorMap> objects.</span></span> <span data-ttu-id="3d6f2-105">각 <xref:System.Drawing.Imaging.ColorMap> 배열의 개체에는 <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> 속성 및 <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="3d6f2-105">Each <xref:System.Drawing.Imaging.ColorMap> object in the array has an <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> property and a <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> property.</span></span>  
  
 <span data-ttu-id="3d6f2-106">때 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 에서는 각 픽셀 이미지의 이미지를 그릴 이전 색 배열 비교 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d6f2-106">When [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] draws an image, each pixel of the image is compared to the array of old colors.</span></span> <span data-ttu-id="3d6f2-107">픽셀의 색이 이전 색과 일치 하면 해당 새 색으로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d6f2-107">If a pixel's color matches an old color, its color is changed to the corresponding new color.</span></span> <span data-ttu-id="3d6f2-108">렌더링에만 변경 되는 색-이미지 자체의 색상 값 (에 저장 된는 <xref:System.Drawing.Image> 또는 <xref:System.Drawing.Bitmap> 개체)은 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3d6f2-108">The colors are changed only for rendering — the color values of the image itself (stored in an <xref:System.Drawing.Image> or <xref:System.Drawing.Bitmap> object) are not changed.</span></span>  
  
 <span data-ttu-id="3d6f2-109">배열을 초기화할 매핑이 변경된 된 이미지를 그리려면 <xref:System.Drawing.Imaging.ColorMap> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3d6f2-109">To draw a remapped image, initialize an array of <xref:System.Drawing.Imaging.ColorMap> objects.</span></span> <span data-ttu-id="3d6f2-110">해당 배열을 전달는 <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> 의 메서드는 <xref:System.Drawing.Imaging.ImageAttributes> 개체를 전달 합니다는 <xref:System.Drawing.Imaging.ImageAttributes> 개체는 <xref:System.Drawing.Graphics.DrawImage%2A> 의 메서드는 <xref:System.Drawing.Graphics> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3d6f2-110">Pass that array to the <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> method of an <xref:System.Drawing.Imaging.ImageAttributes> object, and then pass the <xref:System.Drawing.Imaging.ImageAttributes> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d6f2-111">예</span><span class="sxs-lookup"><span data-stu-id="3d6f2-111">Example</span></span>  
 <span data-ttu-id="3d6f2-112">다음 예제에서는 <xref:System.Drawing.Image> RemapInput.bmp 파일에서 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3d6f2-112">The following example creates an <xref:System.Drawing.Image> object from the file RemapInput.bmp.</span></span> <span data-ttu-id="3d6f2-113">단일 구성 되는 색 다시 매핑 테이블을 만들고 <xref:System.Drawing.Imaging.ColorMap> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3d6f2-113">The code creates a color remap table that consists of a single <xref:System.Drawing.Imaging.ColorMap> object.</span></span> <span data-ttu-id="3d6f2-114"><xref:System.Drawing.Imaging.ColorMap.OldColor%2A> 의 속성은 `ColorRemap` 개체는 빨간색, 및 <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> 속성은 파란색입니다.</span><span class="sxs-lookup"><span data-stu-id="3d6f2-114">The <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> property of the `ColorRemap` object is red, and the <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> property is blue.</span></span> <span data-ttu-id="3d6f2-115">이미지가 그려지는 한 번 다시 매핑 없이 및 한 번 다시 매핑입니다.</span><span class="sxs-lookup"><span data-stu-id="3d6f2-115">The image is drawn once without remapping and once with remapping.</span></span> <span data-ttu-id="3d6f2-116">매핑 모든 빨간색 픽셀 파란색을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6f2-116">The remapping process changes all the red pixels to blue.</span></span>  
  
 <span data-ttu-id="3d6f2-117">다음 그림에서는 오른쪽의 왼쪽에 원본 이미지와 매핑이 변경된 된 이미지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3d6f2-117">The following illustration shows the original image on the left and the remapped image on the right.</span></span>  
  
 <span data-ttu-id="3d6f2-118">![색 다시 매핑](../../../../docs/framework/winforms/advanced/media/colortrans7.png "colortrans7")</span><span class="sxs-lookup"><span data-stu-id="3d6f2-118">![Color ReMap](../../../../docs/framework/winforms/advanced/media/colortrans7.png "colortrans7")</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.RecoloringImages#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3d6f2-119">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="3d6f2-119">Compiling the Code</span></span>  
 <span data-ttu-id="3d6f2-120">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs> 이벤트 처리기의 매개 변수인 `e`<xref:System.Windows.Forms.Control.Paint>가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3d6f2-120">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d6f2-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d6f2-121">See Also</span></span>  
 [<span data-ttu-id="3d6f2-122">이미지 다시 칠하기</span><span class="sxs-lookup"><span data-stu-id="3d6f2-122">Recoloring Images</span></span>](../../../../docs/framework/winforms/advanced/recoloring-images.md)  
 [<span data-ttu-id="3d6f2-123">이미지, 비트맵 및 메타파일</span><span class="sxs-lookup"><span data-stu-id="3d6f2-123">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
