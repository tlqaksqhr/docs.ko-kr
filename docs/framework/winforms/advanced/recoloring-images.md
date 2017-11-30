---
title: "이미지 다시 칠하기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- images [Windows Forms], recoloring
- recoloring images
- examples [Windows Forms], recoloring images
ms.assetid: f28c54fd-9c80-4f6f-b242-55f7ffcda84b
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7f6f432742c966e3f17a7b7fa84628f24109d08e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="recoloring-images"></a><span data-ttu-id="6ccea-102">이미지 다시 칠하기</span><span class="sxs-lookup"><span data-stu-id="6ccea-102">Recoloring Images</span></span>
<span data-ttu-id="6ccea-103">이미지 색을 조정 하는 과정은 다시 칠하기 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccea-103">Recoloring is the process of adjusting image colors.</span></span> <span data-ttu-id="6ccea-104">다시 칠하기의 몇 가지 예는 한 가지 색 다른를 조정 하는 다른 색을 기준으로 색의 강도, 밝기 또는 모든 색의 대비 조정 및 회색 음영으로 변환 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ccea-104">Some examples of recoloring are changing one color to another, adjusting a color's intensity relative to another color, adjusting the brightness or contrast of all colors, and converting colors to shades of gray.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6ccea-105">단원 내용</span><span class="sxs-lookup"><span data-stu-id="6ccea-105">In This Section</span></span>  
 [<span data-ttu-id="6ccea-106">방법: 색 매트릭스를 사용하여 단색으로 변형</span><span class="sxs-lookup"><span data-stu-id="6ccea-106">How to: Use a Color Matrix to Transform a Single Color</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-a-color-matrix-to-transform-a-single-color.md)  
 <span data-ttu-id="6ccea-107">색 매트릭스를 사용 하 여 색 변환에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccea-107">Discusses using a color matrix to transform a color.</span></span>  
  
 [<span data-ttu-id="6ccea-108">방법: 이미지 색 변환</span><span class="sxs-lookup"><span data-stu-id="6ccea-108">How to: Translate Image Colors</span></span>](../../../../docs/framework/winforms/advanced/how-to-translate-image-colors.md)  
 <span data-ttu-id="6ccea-109">색 매트릭스를 사용 하 여 색을 변환 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6ccea-109">Shows how to translate colors using a color matrix.</span></span>  
  
 [<span data-ttu-id="6ccea-110">변형을 사용하여 색의 비율 조정</span><span class="sxs-lookup"><span data-stu-id="6ccea-110">Using Transformations to Scale Colors</span></span>](../../../../docs/framework/winforms/advanced/using-transformations-to-scale-colors.md)  
 <span data-ttu-id="6ccea-111">색 매트릭스를 사용 하 여 색의 크기를 조정 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccea-111">Explains how to scale colors using a color matrix.</span></span>  
  
 [<span data-ttu-id="6ccea-112">방법: 색 회전</span><span class="sxs-lookup"><span data-stu-id="6ccea-112">How to: Rotate Colors</span></span>](../../../../docs/framework/winforms/advanced/how-to-rotate-colors.md)  
 <span data-ttu-id="6ccea-113">색 매트릭스를 사용 하 여 색을 회전 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccea-113">Describes how to rotate a color using a color matrix.</span></span>  
  
 [<span data-ttu-id="6ccea-114">방법: 색 전단</span><span class="sxs-lookup"><span data-stu-id="6ccea-114">How to: Shear Colors</span></span>](../../../../docs/framework/winforms/advanced/how-to-shear-colors.md)  
 <span data-ttu-id="6ccea-115">기울이기 정의 하 고 색 매트릭스를 사용 하 여 색 전단 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccea-115">Defines shearing and explains how to shear colors using a color matrix.</span></span>  
  
 [<span data-ttu-id="6ccea-116">방법: 색 매핑 변경 테이블 사용</span><span class="sxs-lookup"><span data-stu-id="6ccea-116">How to: Use a Color Remap Table</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-a-color-remap-table.md)  
 <span data-ttu-id="6ccea-117">다시 매핑을 정의 하 고 색 다시 매핑 테이블을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6ccea-117">Defines remapping and shows how to use a color remap table.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6ccea-118">참조</span><span class="sxs-lookup"><span data-stu-id="6ccea-118">Reference</span></span>  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <span data-ttu-id="6ccea-119">이 클래스를 설명 하 고 모든 해당 멤버의 링크를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccea-119">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Drawing.Imaging.ColorMap>  
 <span data-ttu-id="6ccea-120">이 클래스를 설명 하 고 모든 해당 멤버의 링크를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccea-120">Describes this class and contains links to all of its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6ccea-121">관련 단원</span><span class="sxs-lookup"><span data-stu-id="6ccea-121">Related Sections</span></span>  
 [<span data-ttu-id="6ccea-122">이미지, 비트맵 및 메타파일</span><span class="sxs-lookup"><span data-stu-id="6ccea-122">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 <span data-ttu-id="6ccea-123">여러 종류의 이미지에 대 한 항목 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccea-123">Provides a list of topics regarding the different types of images.</span></span>  
  
 [<span data-ttu-id="6ccea-124">이미지, 비트맵, 아이콘 및 메타파일 사용</span><span class="sxs-lookup"><span data-stu-id="6ccea-124">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)  
 <span data-ttu-id="6ccea-125">여러 종류의 이미지를 사용 하는 방법을 보여 주는 항목의 목록을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccea-125">Contains a list of topics that show how to use different types of images.</span></span>  
  
 [<span data-ttu-id="6ccea-126">관리되는 그래픽 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="6ccea-126">Using Managed Graphics Classes</span></span>](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)  
 <span data-ttu-id="6ccea-127">관리 되는 그래픽 클래스를 사용 하는 방법을 설명 하는 항목의 목록을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ccea-127">Contains a list of topics describing how to use managed graphics classes.</span></span>
