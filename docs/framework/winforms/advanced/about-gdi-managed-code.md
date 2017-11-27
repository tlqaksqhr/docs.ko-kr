---
title: "GDI+ 관리 코드 정보"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GDI+, about GDI+
- GDI+
- graphics [Windows Forms], GDI+
ms.assetid: a98a76ab-e455-49c9-891c-0491ac932f2c
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 711d25c600c2144ad4b134984501f641be24ced2
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="about-gdi-managed-code"></a><span data-ttu-id="089e5-102">GDI+ 관리 코드 정보</span><span class="sxs-lookup"><span data-stu-id="089e5-102">About GDI+ Managed Code</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="089e5-103">는 2차원 벡터 그래픽, 이미징 및 입력 체계를 제공하는 Windows 운영 체제의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="089e5-103"> is the portion of the Windows operating system that provides two-dimensional vector graphics, imaging, and typography.</span></span> [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]<span data-ttu-id="089e5-104">(이전 버전의 Windows에 포함된 그래픽 장치 인터페이스)에서는 새로운 기능을 추가하고 기존 기능을 최적화하여 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]가 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="089e5-104"> improves on [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] (the Graphics Device Interface included with earlier versions of Windows) by adding new features and by optimizing existing features.</span></span>  
  
 <span data-ttu-id="089e5-105">[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 관리되는 클래스 인터페이스(래퍼 집합)는 XML Web services 및 기타 응용 프로그램을 빌드, 배포 및 실행하기 위한 환경인 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="089e5-105">The [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] managed class interface (a set of wrappers) is part of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], an environment for building, deploying, and running XML Web services and other applications.</span></span>  
  
 <span data-ttu-id="089e5-106">이 섹션에서는 관리 코드를 사용하는 프로그래머를 위한 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] API에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="089e5-106">This section provides information about the [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] API for programmers using managed code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="089e5-107">단원 내용</span><span class="sxs-lookup"><span data-stu-id="089e5-107">In This Section</span></span>  
 [<span data-ttu-id="089e5-108">선, 곡선 및 도형</span><span class="sxs-lookup"><span data-stu-id="089e5-108">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 <span data-ttu-id="089e5-109">벡터 그래픽을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="089e5-109">Discusses vector graphics.</span></span>  
  
 [<span data-ttu-id="089e5-110">이미지, 비트맵 및 메타파일</span><span class="sxs-lookup"><span data-stu-id="089e5-110">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 <span data-ttu-id="089e5-111">사용할 수 있는 이미지 형식 및 작업 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="089e5-111">Discusses the type of images available and how to work with them.</span></span>  
  
 [<span data-ttu-id="089e5-112">좌표계 및 변형</span><span class="sxs-lookup"><span data-stu-id="089e5-112">Coordinate Systems and Transformations</span></span>](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)  
 <span data-ttu-id="089e5-113">[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서 그래픽을 변환하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="089e5-113">Discusses how to transform graphics with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span>  
  
## <a name="reference"></a><span data-ttu-id="089e5-114">참조</span><span class="sxs-lookup"><span data-stu-id="089e5-114">Reference</span></span>  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <span data-ttu-id="089e5-115">이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="089e5-115">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.Drawing.Image?displayProperty=nameWithType>  
 <span data-ttu-id="089e5-116">이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="089e5-116">Describes this class and has links to all its members.</span></span>  
  
 <span data-ttu-id="089e5-117"><xref:System.Drawing.Bitmap?displayProperty=nameWithType>,</span><span class="sxs-lookup"><span data-stu-id="089e5-117"><xref:System.Drawing.Bitmap?displayProperty=nameWithType>,</span></span>  
 <span data-ttu-id="089e5-118">이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="089e5-118">Describes this class and has links to all its members.</span></span>  
  
 <span data-ttu-id="089e5-119"><xref:System.Drawing.Imaging.Metafile?displayProperty=nameWithType>,</span><span class="sxs-lookup"><span data-stu-id="089e5-119"><xref:System.Drawing.Imaging.Metafile?displayProperty=nameWithType>,</span></span>  
 <span data-ttu-id="089e5-120">이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="089e5-120">Describes this class and has links to all its members.</span></span>  
  
 <span data-ttu-id="089e5-121"><xref:System.Drawing.Font?displayProperty=nameWithType>,</span><span class="sxs-lookup"><span data-stu-id="089e5-121"><xref:System.Drawing.Font?displayProperty=nameWithType>,</span></span>  
 <span data-ttu-id="089e5-122">이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="089e5-122">Describes this class and has links to all its members.</span></span>  
  
 <span data-ttu-id="089e5-123"><xref:System.Drawing.Brush?displayProperty=nameWithType>,</span><span class="sxs-lookup"><span data-stu-id="089e5-123"><xref:System.Drawing.Brush?displayProperty=nameWithType>,</span></span>  
 <span data-ttu-id="089e5-124">이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="089e5-124">Describes this class and has links to all its members.</span></span>  
  
 <span data-ttu-id="089e5-125"><xref:System.Drawing.Color?displayProperty=nameWithType>,</span><span class="sxs-lookup"><span data-stu-id="089e5-125"><xref:System.Drawing.Color?displayProperty=nameWithType>,</span></span>  
 <span data-ttu-id="089e5-126">이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="089e5-126">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.Drawing.Drawing2D.Matrix?displayProperty=nameWithType>  
 <span data-ttu-id="089e5-127">이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="089e5-127">Describes this class and has links to all its members.</span></span>  
  
 <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType>  
 <span data-ttu-id="089e5-128">이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="089e5-128">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="089e5-129">관련 단원</span><span class="sxs-lookup"><span data-stu-id="089e5-129">Related Sections</span></span>  
 <span data-ttu-id="089e5-130">[관리 되는 그래픽 클래스 사용](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="089e5-130">[Using Managed Graphics Classes](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md).</span></span>  
 <span data-ttu-id="089e5-131">`Graphics` 프로그래밍 인터페이스를 사용하는 방법을 보여 주는 항목의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="089e5-131">Contains links to topics that demonstrate how to use the `Graphics` programming interface.</span></span>
