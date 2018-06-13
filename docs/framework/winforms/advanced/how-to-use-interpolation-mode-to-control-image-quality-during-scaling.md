---
title: '방법: 배율 조정 시 보간 모드를 사용하여 이미지 품질 관리'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interpolation mode [Windows Forms], controlling image quality
- images [Windows Forms], scaling
- images [Windows Forms], controlling quality
ms.assetid: fde9bccf-8aa5-4b0d-ba4b-788740627b02
ms.openlocfilehash: 72a9cb3a19f0d449dcb376a65f1734b79ed61ab9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522361"
---
# <a name="how-to-use-interpolation-mode-to-control-image-quality-during-scaling"></a><span data-ttu-id="3922b-102">방법: 배율 조정 시 보간 모드를 사용하여 이미지 품질 관리</span><span class="sxs-lookup"><span data-stu-id="3922b-102">How to: Use Interpolation Mode to Control Image Quality During Scaling</span></span>
<span data-ttu-id="3922b-103">보간 모드는 <xref:System.Drawing.Graphics> 방식에 영향을 미칩니다 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 이미지 크기를 조절 (까지 확장 및 축소) 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922b-103">The interpolation mode of a <xref:System.Drawing.Graphics> object influences the way [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] scales (stretches and shrinks) images.</span></span> <span data-ttu-id="3922b-104"><xref:System.Drawing.Drawing2D.InterpolationMode> 열거형 다음 목록에 표시 되는 다음과 같은 몇 가지 보간 모드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922b-104">The <xref:System.Drawing.Drawing2D.InterpolationMode> enumeration defines several interpolation modes, some of which are shown in the following list:</span></span>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.Bilinear>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBilinear>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.Bicubic>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic>  
  
 <span data-ttu-id="3922b-105">이미지를 확대 하려면 원본 이미지의 각 픽셀의 더 큰 이미지 픽셀 그룹에 매핑해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922b-105">To stretch an image, each pixel in the original image must be mapped to a group of pixels in the larger image.</span></span> <span data-ttu-id="3922b-106">이미지를 축소 하려면 원본 이미지의 픽셀의 그룹을 더 작은 이미지에 단일 픽셀에 매핑해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922b-106">To shrink an image, groups of pixels in the original image must be mapped to single pixels in the smaller image.</span></span> <span data-ttu-id="3922b-107">이러한 매핑을 수행 하는 알고리즘의 효율성 크기 조정 된 이미지의 품질을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922b-107">The effectiveness of the algorithms that perform these mappings determines the quality of a scaled image.</span></span> <span data-ttu-id="3922b-108">더 높은 품질의 크기 조정 된 이미지를 생성 하는 알고리즘은 처리 시간이 더 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922b-108">Algorithms that produce higher-quality scaled images tend to require more processing time.</span></span> <span data-ttu-id="3922b-109">앞의 목록에 <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor> 는 가장 낮은 수준의 모드 및 <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic> 최고 품질 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="3922b-109">In the preceding list, <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor> is the lowest-quality mode and <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic> is the highest-quality mode.</span></span>  
  
 <span data-ttu-id="3922b-110">보간 모드를 설정 하려면의 멤버 중 하나를 할당 된 <xref:System.Drawing.Drawing2D.InterpolationMode> 열거형을는 <xref:System.Drawing.Graphics.InterpolationMode%2A> 속성의는 <xref:System.Drawing.Graphics> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3922b-110">To set the interpolation mode, assign one of the members of the <xref:System.Drawing.Drawing2D.InterpolationMode> enumeration to the <xref:System.Drawing.Graphics.InterpolationMode%2A> property of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3922b-111">예제</span><span class="sxs-lookup"><span data-stu-id="3922b-111">Example</span></span>  
 <span data-ttu-id="3922b-112">다음 예제에서는 이미지를 그립니다 하 고 세 가지 서로 다른 보간 모드를 사용 하 여 이미지를 감소 합니다.</span><span class="sxs-lookup"><span data-stu-id="3922b-112">The following example draws an image and then shrinks the image with three different interpolation modes.</span></span>  
  
 <span data-ttu-id="3922b-113">다음 그림에서는 원본 이미지와 세 개의 더 작은 이미지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3922b-113">The following illustration shows the original image and the three smaller images.</span></span>  
  
 <span data-ttu-id="3922b-114">![다양 한 보간 설정 이미지](../../../../docs/framework/winforms/advanced/media/csgrapes1.png "csgrapes1")</span><span class="sxs-lookup"><span data-stu-id="3922b-114">![Image with Varied Interpolation Settings](../../../../docs/framework/winforms/advanced/media/csgrapes1.png "csgrapes1")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#81](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#81)]
 [!code-vb[System.Drawing.WorkingWithImages#81](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#81)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3922b-115">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="3922b-115">Compiling the Code</span></span>  
 <span data-ttu-id="3922b-116">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3922b-116">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3922b-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3922b-117">See Also</span></span>  
 [<span data-ttu-id="3922b-118">이미지, 비트맵 및 메타파일</span><span class="sxs-lookup"><span data-stu-id="3922b-118">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="3922b-119">이미지, 비트맵, 아이콘 및 메타파일 사용</span><span class="sxs-lookup"><span data-stu-id="3922b-119">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
