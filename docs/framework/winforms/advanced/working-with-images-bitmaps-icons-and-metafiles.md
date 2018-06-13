---
title: 이미지, 비트맵, 아이콘 및 메타파일 사용
ms.date: 03/30/2017
helpviewer_keywords:
- metafiles [Windows Forms], working with
- examples [Windows Forms], bitmaps
- examples [Windows Forms], images
- bitmaps [Windows Forms], working with
- images [Windows Forms], working with
- examples [Windows Forms], metafiles
ms.assetid: a626d701-bd99-4fd8-b92f-7b8f794e042b
ms.openlocfilehash: 6d2f0a2f4acebaac59f2d8180f2de4ccb88b2965
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526838"
---
# <a name="working-with-images-bitmaps-icons-and-metafiles"></a><span data-ttu-id="5e0c0-102">이미지, 비트맵, 아이콘 및 메타파일 사용</span><span class="sxs-lookup"><span data-stu-id="5e0c0-102">Working with Images, Bitmaps, Icons, and Metafiles</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="5e0c0-103">는 래스터 이미지 작업을 위한 `Bitmap` 클래스와 벡터 이미지 작업을 위한 `Metafile` 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0c0-103"> provides the `Bitmap` class for working with raster images and the `Metafile` class for working with vector images.</span></span> <span data-ttu-id="5e0c0-104">`Bitmap` 및 `Metafile` 클래스는 둘 다 `Image` 클래스에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e0c0-104">The `Bitmap` and the `Metafile` classes both inherit from the `Image` class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5e0c0-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="5e0c0-105">In This Section</span></span>  
 [<span data-ttu-id="5e0c0-106">방법: 화면에 기존 비트맵 그리기</span><span class="sxs-lookup"><span data-stu-id="5e0c0-106">How to: Draw an Existing Bitmap to the Screen</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-an-existing-bitmap-to-the-screen.md)  
 <span data-ttu-id="5e0c0-107">비트맵을 로드하고 그리는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0c0-107">Describes how to load and draw bitmaps.</span></span>  
  
 [<span data-ttu-id="5e0c0-108">방법: 메타파일 로드 및 표시</span><span class="sxs-lookup"><span data-stu-id="5e0c0-108">How to: Load and Display Metafiles</span></span>](../../../../docs/framework/winforms/advanced/how-to-load-and-display-metafiles.md)  
 <span data-ttu-id="5e0c0-109">메타파일을 로드하고 그리는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0c0-109">Shows how to load and draw metafiles.</span></span>  
  
 [<span data-ttu-id="5e0c0-110">GDI+에서 이미지 자르기 및 배율 조정</span><span class="sxs-lookup"><span data-stu-id="5e0c0-110">Cropping and Scaling Images in GDI+</span></span>](../../../../docs/framework/winforms/advanced/cropping-and-scaling-images-in-gdi.md)  
 <span data-ttu-id="5e0c0-111">벡터 및 래스터 이미지를 자르고 크기를 조정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0c0-111">Explains how to crop and scale vector and raster images.</span></span>  
  
 [<span data-ttu-id="5e0c0-112">방법: 이미지 회전, 리플렉션 및 기울이기</span><span class="sxs-lookup"><span data-stu-id="5e0c0-112">How to: Rotate, Reflect, and Skew Images</span></span>](../../../../docs/framework/winforms/advanced/how-to-rotate-reflect-and-skew-images.md)  
 <span data-ttu-id="5e0c0-113">회전, 반사 및 왜곡된 이미지를 그리는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0c0-113">Describes how to draw rotated, reflected and skewed images.</span></span>  
  
 [<span data-ttu-id="5e0c0-114">방법: 배율 조정 시 보간 모드를 사용하여 이미지 품질 관리</span><span class="sxs-lookup"><span data-stu-id="5e0c0-114">How to: Use Interpolation Mode to Control Image Quality During Scaling</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-interpolation-mode-to-control-image-quality-during-scaling.md)  
 <span data-ttu-id="5e0c0-115"><xref:System.Drawing.Drawing2D.InterpolationMode> 열거형을 사용하여 이미지 품질을 변경하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5e0c0-115">Shows how to use the <xref:System.Drawing.Drawing2D.InterpolationMode> enumeration to change image quality.</span></span>  
  
 [<span data-ttu-id="5e0c0-116">방법: 축소판 이미지 만들기</span><span class="sxs-lookup"><span data-stu-id="5e0c0-116">How to: Create Thumbnail Images</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-thumbnail-images.md)  
 <span data-ttu-id="5e0c0-117">축소판 이미지를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0c0-117">Describes how to create thumbnail images.</span></span>  
  
 [<span data-ttu-id="5e0c0-118">방법: 자동 크기 조정 없이 성능 향상</span><span class="sxs-lookup"><span data-stu-id="5e0c0-118">How to: Improve Performance by Avoiding Automatic Scaling</span></span>](../../../../docs/framework/winforms/advanced/how-to-improve-performance-by-avoiding-automatic-scaling.md)  
 <span data-ttu-id="5e0c0-119">자동 크기 조정 없이 이미지를 그리는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0c0-119">Explains how to draw an image without automatic scaling.</span></span>  
  
 [<span data-ttu-id="5e0c0-120">방법: 이미지 메타데이터 읽기</span><span class="sxs-lookup"><span data-stu-id="5e0c0-120">How to: Read Image Metadata</span></span>](../../../../docs/framework/winforms/advanced/how-to-read-image-metadata.md)  
 <span data-ttu-id="5e0c0-121">이미지에서 메타데이터를 읽는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0c0-121">Describes how to read metadata from an image.</span></span>  
  
 [<span data-ttu-id="5e0c0-122">방법: 런타임에 비트맵 만들기</span><span class="sxs-lookup"><span data-stu-id="5e0c0-122">How to: Create a Bitmap at Run Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-bitmap-at-run-time.md)  
 <span data-ttu-id="5e0c0-123">런타임에 비트맵을 그리는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5e0c0-123">Shows how to draw a bitmap at runtime.</span></span>  
  
 [<span data-ttu-id="5e0c0-124">방법: Windows Forms에서 파일과 연결된 아이콘 추출</span><span class="sxs-lookup"><span data-stu-id="5e0c0-124">How to: Extract the Icon Associated with a File in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-extract-the-icon-associated-with-a-file-in-windows-forms.md)  
 <span data-ttu-id="5e0c0-125">파일의 포함된 리소스인 아이콘을 추출하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0c0-125">Describes how to extract an icon that is an embedded resource of a file.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5e0c0-126">참조</span><span class="sxs-lookup"><span data-stu-id="5e0c0-126">Reference</span></span>  
 <xref:System.Drawing.Image>  
 <span data-ttu-id="5e0c0-127">이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0c0-127">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Imaging.Metafile>  
 <span data-ttu-id="5e0c0-128">이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0c0-128">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Bitmap>  
 <span data-ttu-id="5e0c0-129">이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0c0-129">Describes this class and has links to all of its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5e0c0-130">관련 단원</span><span class="sxs-lookup"><span data-stu-id="5e0c0-130">Related Sections</span></span>  
 [<span data-ttu-id="5e0c0-131">이미지, 비트맵 및 메타파일</span><span class="sxs-lookup"><span data-stu-id="5e0c0-131">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 <span data-ttu-id="5e0c0-132">다양한 유형의 비트맵 및 응용 프로그램에서 조작하는 방법을 설명하는 항목의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5e0c0-132">Contains links to topics that discuss different types of bitmaps and manipulating them in your applications.</span></span>
