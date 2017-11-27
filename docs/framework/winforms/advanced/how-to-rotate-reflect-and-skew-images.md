---
title: "방법: 이미지 회전, 반사 및 기울이기"
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
- images [Windows Forms], reflecting
- images [Windows Forms], rotating
- images [Windows Forms], skewing
ms.assetid: a3bf97eb-63ed-425a-ba07-dcc65efb567c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: eaa6286731d196dad387e1648644ca3e8103da03
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-rotate-reflect-and-skew-images"></a><span data-ttu-id="4e828-102">방법: 이미지 회전, 반사 및 기울이기</span><span class="sxs-lookup"><span data-stu-id="4e828-102">How to: Rotate, Reflect, and Skew Images</span></span>
<span data-ttu-id="4e828-103">있습니다 수 회전, 반사 및 기울이기 이미지 원본 이미지의 왼쪽 위, 오른쪽 위 및 왼쪽 아래 모퉁이 대 한 대상 지점을 지정 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e828-103">You can rotate, reflect, and skew an image by specifying destination points for the upper-left, upper-right, and lower-left corners of the original image.</span></span> <span data-ttu-id="4e828-104">세 개의 대상 지점 평행 사변형에 원본 사각형이 이미지 매핑되는 3x3 유사 변형을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e828-104">The three destination points determine an affine transformation that maps the original rectangular image to a parallelogram.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e828-105">예제</span><span class="sxs-lookup"><span data-stu-id="4e828-105">Example</span></span>  
 <span data-ttu-id="4e828-106">예를 들어, 원본 이미지는 왼쪽 위 모퉁이에 있는 사각형 (0, 0)에서 오른쪽 위 모서리 (100, 0) 및 왼쪽 아래 모퉁이에 (0, 50).</span><span class="sxs-lookup"><span data-stu-id="4e828-106">For example, suppose the original image is a rectangle with upper-left corner at (0, 0), upper-right corner at (100, 0), and lower-left corner at (0, 50).</span></span> <span data-ttu-id="4e828-107">이제 이러한 매핑 한다고 가정 3 개를 가리킵니다 대상 점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4e828-107">Now suppose you map those three points to destination points as follows.</span></span>  
  
|<span data-ttu-id="4e828-108">원래 지점</span><span class="sxs-lookup"><span data-stu-id="4e828-108">Original point</span></span>|<span data-ttu-id="4e828-109">대상 지점</span><span class="sxs-lookup"><span data-stu-id="4e828-109">Destination point</span></span>|  
|--------------------|-----------------------|  
|<span data-ttu-id="4e828-110">왼쪽 위 (0, 0)</span><span class="sxs-lookup"><span data-stu-id="4e828-110">Upper-left (0, 0)</span></span>|<span data-ttu-id="4e828-111">(200, 20)</span><span class="sxs-lookup"><span data-stu-id="4e828-111">(200, 20)</span></span>|  
|<span data-ttu-id="4e828-112">오른쪽 위 (100, 0)</span><span class="sxs-lookup"><span data-stu-id="4e828-112">Upper-right (100, 0)</span></span>|<span data-ttu-id="4e828-113">(110, 100)</span><span class="sxs-lookup"><span data-stu-id="4e828-113">(110, 100)</span></span>|  
|<span data-ttu-id="4e828-114">왼쪽 아래 (0, 50)</span><span class="sxs-lookup"><span data-stu-id="4e828-114">Lower-left (0, 50)</span></span>|<span data-ttu-id="4e828-115">(250, 30)</span><span class="sxs-lookup"><span data-stu-id="4e828-115">(250, 30)</span></span>|  
  
 <span data-ttu-id="4e828-116">다음은 원본 이미지와 평행 사변형에 매핑되는 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="4e828-116">The following illustration shows the original image and the image mapped to the parallelogram.</span></span> <span data-ttu-id="4e828-117">원본 이미지 왜곡, 반영, 회전, 되었으며 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e828-117">The original image has been skewed, reflected, rotated, and translated.</span></span> <span data-ttu-id="4e828-118">통해 실행 되는 줄에 매핑된 원본 이미지의 위쪽 가장자리를 따라 x 축 (200, 20) 및 (110, 100).</span><span class="sxs-lookup"><span data-stu-id="4e828-118">The x-axis along the top edge of the original image is mapped to the line that runs through (200, 20) and (110, 100).</span></span> <span data-ttu-id="4e828-119">통해 실행 되는 줄에 매핑된 원본 이미지의 왼쪽된 가장자리를 따라 y 축 (200, 20) 및 (250, 30).</span><span class="sxs-lookup"><span data-stu-id="4e828-119">The y-axis along the left edge of the original image is mapped to the line that runs through (200, 20) and (250, 30).</span></span>  
  
 <span data-ttu-id="4e828-120">![줄무늬](../../../../docs/framework/winforms/advanced/media/stripes1.gif "Stripes1")</span><span class="sxs-lookup"><span data-stu-id="4e828-120">![Stripes](../../../../docs/framework/winforms/advanced/media/stripes1.gif "Stripes1")</span></span>  
  
 <span data-ttu-id="4e828-121">다음 그림과 비슷한 변환을 사진 이미지에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e828-121">The following illustration shows a similar transformation applied to a photographic image.</span></span>  
  
 <span data-ttu-id="4e828-122">![오르기 변환](../../../../docs/framework/winforms/advanced/media/transformedclimber.png "TransformedClimber")</span><span class="sxs-lookup"><span data-stu-id="4e828-122">![Transformed Climber](../../../../docs/framework/winforms/advanced/media/transformedclimber.png "TransformedClimber")</span></span>  
  
 <span data-ttu-id="4e828-123">다음 그림과 비슷한 변환을 메타 파일에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e828-123">The following illustration shows a similar transformation applied to a metafile.</span></span>  
  
 <span data-ttu-id="4e828-124">![메타 파일 변환](../../../../docs/framework/winforms/advanced/media/transformedmetafile.png "TransformedMetafile")</span><span class="sxs-lookup"><span data-stu-id="4e828-124">![Transformed Metafile](../../../../docs/framework/winforms/advanced/media/transformedmetafile.png "TransformedMetafile")</span></span>  
  
 <span data-ttu-id="4e828-125">다음 예에서는 첫 번째 그림에 표시 된 이미지를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e828-125">The following example produces the images shown in the first illustration.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4e828-126">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="4e828-126">Compiling the Code</span></span>  
 <span data-ttu-id="4e828-127">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs> 이벤트 처리기의 매개 변수인 `e`<xref:System.Windows.Forms.Control.Paint>가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4e828-127">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="4e828-128">대체 해야 `Stripes.bmp` 은 시스템에서 사용할 수 있는 이미지의 경로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e828-128">Make sure to replace `Stripes.bmp` with the path to an image that is valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e828-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e828-129">See Also</span></span>  
 [<span data-ttu-id="4e828-130">이미지, 비트맵, 아이콘 및 메타파일 사용</span><span class="sxs-lookup"><span data-stu-id="4e828-130">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
