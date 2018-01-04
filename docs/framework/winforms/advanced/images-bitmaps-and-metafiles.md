---
title: "이미지, 비트맵 및 메타파일"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- metafiles [Windows Forms], about metafiles
- bitmaps [Windows Forms], about bitmaps
- images [Windows Forms], about images
- Windows Forms, images
ms.assetid: 7152b45b-a55c-49bc-8c78-ae002a844f71
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 67f72847e5dca20acd623c566a882e0094e94f68
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="images-bitmaps-and-metafiles"></a><span data-ttu-id="ea9ae-102">이미지, 비트맵 및 메타파일</span><span class="sxs-lookup"><span data-stu-id="ea9ae-102">Images, Bitmaps, and Metafiles</span></span>
<span data-ttu-id="ea9ae-103">`Image` 클래스는 래스터 이미지(비트맵) 및 벡터 이미지(메타파일) 작업을 위한 메서드를 제공하는 추상 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="ea9ae-103">The `Image` class is an abstract base class that provides methods for working with raster images (bitmaps) and vector images (metafiles).</span></span> <span data-ttu-id="ea9ae-104">`Bitmap` 클래스와 <xref:System.Drawing.Imaging.Metafile> 클래스는 모두 `Image` 클래스에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea9ae-104">The `Bitmap` class and the <xref:System.Drawing.Imaging.Metafile> class both inherit from the `Image` class.</span></span> <span data-ttu-id="ea9ae-105">`Bitmap` 클래스는 래스터 이미지를 로드, 저장 및 조작하기 위한 추가 메서드를 제공하여 `Image` 클래스의 기능을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="ea9ae-105">The `Bitmap` class expands on the capabilities of the `Image` class by providing additional methods for loading, saving, and manipulating raster images.</span></span> <span data-ttu-id="ea9ae-106"><xref:System.Drawing.Imaging.Metafile> 클래스는 벡터 이미지를 기록 및 검사하기 위한 추가 메서드를 제공하여 `Image` 클래스의 기능을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="ea9ae-106">The <xref:System.Drawing.Imaging.Metafile> class expands on the capabilities of the `Image` class by providing additional methods for recording and examining vector images.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ea9ae-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="ea9ae-107">In This Section</span></span>  
 [<span data-ttu-id="ea9ae-108">비트맵의 유형</span><span class="sxs-lookup"><span data-stu-id="ea9ae-108">Types of Bitmaps</span></span>](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)  
 <span data-ttu-id="ea9ae-109">다양한 이미지 형식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ea9ae-109">Discusses the various image formats.</span></span>  
  
 [<span data-ttu-id="ea9ae-110">GDI+의 메타파일</span><span class="sxs-lookup"><span data-stu-id="ea9ae-110">Metafiles in GDI+</span></span>](../../../../docs/framework/winforms/advanced/metafiles-in-gdi.md)  
 <span data-ttu-id="ea9ae-111">메타파일에 대한 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 지원을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ea9ae-111">Discusses [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] support for metafiles.</span></span>  
  
 [<span data-ttu-id="ea9ae-112">GDI+에서 이미지 그리기, 위치 지정 및 복제</span><span class="sxs-lookup"><span data-stu-id="ea9ae-112">Drawing, Positioning, and Cloning Images in GDI+</span></span>](../../../../docs/framework/winforms/advanced/drawing-positioning-and-cloning-images-in-gdi.md)  
 <span data-ttu-id="ea9ae-113">관리 코드로 벡터 및 래스터 이미지를 그리기 위한 메서드를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ea9ae-113">Discusses methods for drawing vector and raster images with managed code.</span></span>  
  
 [<span data-ttu-id="ea9ae-114">GDI+에서 이미지 자르기 및 배율 조정</span><span class="sxs-lookup"><span data-stu-id="ea9ae-114">Cropping and Scaling Images in GDI+</span></span>](../../../../docs/framework/winforms/advanced/cropping-and-scaling-images-in-gdi.md)  
 <span data-ttu-id="ea9ae-115">관리 코드로 벡터 및 래스터 이미지를 자르고 크기를 조정하기 위한 메서드를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ea9ae-115">Discusses methods for cropping and scaling vector and raster images with managed code</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ea9ae-116">참조</span><span class="sxs-lookup"><span data-stu-id="ea9ae-116">Reference</span></span>  
 <xref:System.Drawing.Image>  
 <span data-ttu-id="ea9ae-117">이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ea9ae-117">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Bitmap>  
 <span data-ttu-id="ea9ae-118">이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ea9ae-118">Describes this class and has links to all of its members</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ea9ae-119">관련 단원</span><span class="sxs-lookup"><span data-stu-id="ea9ae-119">Related Sections</span></span>  
 [<span data-ttu-id="ea9ae-120">이미지, 비트맵, 아이콘 및 메타파일 사용</span><span class="sxs-lookup"><span data-stu-id="ea9ae-120">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)  
 <span data-ttu-id="ea9ae-121">응용 프로그램에서 이미지를 사용하는 방법을 설명하는 항목의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ea9ae-121">Contains links to topics that demonstrate how to use images in your application.</span></span>
