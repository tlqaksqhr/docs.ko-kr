---
title: "방법: 도형에 이미지를 바둑판식으로 배열"
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
- texture brushes [Windows Forms], tiling images with
- images [Windows Forms], filling shapes with
- shapes [Windows Forms], tiling with images
- bitmaps [Windows Forms], filling shapes with
ms.assetid: 6d407891-6e5c-4495-a546-3da5604e9fb8
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d8726322e9443042b76c28e7b4b22ebc51c871bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-tile-a-shape-with-an-image"></a><span data-ttu-id="e33fd-102">방법: 도형에 이미지를 바둑판식으로 배열</span><span class="sxs-lookup"><span data-stu-id="e33fd-102">How to: Tile a Shape with an Image</span></span>
<span data-ttu-id="e33fd-103">타일을 층을 서로 옆에 배치할 것 처럼 사각형 이미지 서로 인접 (타일) 도형 채우기 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e33fd-103">Just as tiles can be placed next to each other to cover a floor, rectangular images can be placed next to each other to fill (tile) a shape.</span></span> <span data-ttu-id="e33fd-104">도형의 내부가 바둑판식으로 배열 하려면 질감 브러시를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e33fd-104">To tile the interior of a shape, use a texture brush.</span></span> <span data-ttu-id="e33fd-105">생성할 때는 <xref:System.Drawing.TextureBrush> 개체 생성자에 전달 하는 인수 중 하나는 <xref:System.Drawing.Image> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="e33fd-105">When you construct a <xref:System.Drawing.TextureBrush> object, one of the arguments you pass to the constructor is an <xref:System.Drawing.Image> object.</span></span> <span data-ttu-id="e33fd-106">질감 브러시를 사용 하 여 도형의 내부를 그리는 경우 셰이프가이 이미지의 반복된 복사본으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="e33fd-106">When you use the texture brush to paint the interior of a shape, the shape is filled with repeated copies of this image.</span></span>  
  
 <span data-ttu-id="e33fd-107">래핑 모드 속성은 <xref:System.Drawing.TextureBrush> 방법을 이미지는 사각형 그리드에서 반복 되는 대로 방향 개체를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e33fd-107">The wrap mode property of the <xref:System.Drawing.TextureBrush> object determines how the image is oriented as it is repeated in a rectangular grid.</span></span> <span data-ttu-id="e33fd-108">눈금에서 타일 모두 동일한 방향을 만들 수 있습니다 또는 다음 그리드 위치에서 대칭 이동 이미지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e33fd-108">You can make all the tiles in the grid have the same orientation, or you can make the image flip from one grid position to the next.</span></span> <span data-ttu-id="e33fd-109">반전 가로 스크롤 가능 세로 축 또는 둘 다 합니다.</span><span class="sxs-lookup"><span data-stu-id="e33fd-109">The flipping can be horizontal, vertical, or both.</span></span> <span data-ttu-id="e33fd-110">다음 예에서는 대칭 이동 하는 여러 유형의 사용한 바둑판식 배열 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e33fd-110">The following examples demonstrate tiling with different types of flipping.</span></span>  
  
### <a name="to-tile-an-image"></a><span data-ttu-id="e33fd-111">이미지를 바둑판식으로 배열 하려면</span><span class="sxs-lookup"><span data-stu-id="e33fd-111">To tile an image</span></span>  
  
-   <span data-ttu-id="e33fd-112">이 예제에서는 200 × 200 사각형 바둑판식으로 배열 하 다음 75 × 75 이미지를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e33fd-112">This example uses the following 75×75 image to tile a 200×200 rectangle.</span></span>  
  
 <span data-ttu-id="e33fd-113">![1 바둑판식으로 배열](../../../../docs/framework/winforms/advanced/media/tile1.gif "tile1")</span><span class="sxs-lookup"><span data-stu-id="e33fd-113">![Tile 1](../../../../docs/framework/winforms/advanced/media/tile1.gif "tile1")</span></span>  
  
-   <span data-ttu-id="e33fd-114">다음 그림에서는 사각형이 이미지와 바둑판식으로 배열 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e33fd-114">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="e33fd-115">모든 타일이 동일한 방향을;가 대칭 이동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e33fd-115">Note that all tiles have the same orientation; there is no flipping.</span></span>  
  
 <span data-ttu-id="e33fd-116">![2 바둑판식으로 배열](../../../../docs/framework/winforms/advanced/media/tile2.gif "tile2")</span><span class="sxs-lookup"><span data-stu-id="e33fd-116">![Tile 2](../../../../docs/framework/winforms/advanced/media/tile2.gif "tile2")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingABrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#31)]  
  
### <a name="to-flip-an-image-horizontally-while-tiling"></a><span data-ttu-id="e33fd-117">가로 바둑판식 배열 하는 동안 이미지 대칭 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="e33fd-117">To flip an image horizontally while tiling</span></span>  
  
-   <span data-ttu-id="e33fd-118">이 예제에서는 동일한 75 × 75 이미지를 사용 하 여 200 × 200 사각형을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="e33fd-118">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="e33fd-119">래핑 모드 이미지를 가로로 대칭 이동로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e33fd-119">The wrap mode is set to flip the image horizontally.</span></span> <span data-ttu-id="e33fd-120">다음 그림에서는 사각형이 이미지와 바둑판식으로 배열 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e33fd-120">The following illustration shows how the rectangle is tiled with the image.</span></span> <span data-ttu-id="e33fd-121">하나의 타일에서 특정된 행을 이동 하면 이미지 가로로 대칭을 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e33fd-121">Note that as you move from one tile to the next in a given row, the image is flipped horizontally.</span></span>  
  
 <span data-ttu-id="e33fd-122">![타일 3](../../../../docs/framework/winforms/advanced/media/tile3.gif "tile3")</span><span class="sxs-lookup"><span data-stu-id="e33fd-122">![Tile 3](../../../../docs/framework/winforms/advanced/media/tile3.gif "tile3")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.UsingABrush#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#32)]  
  
### <a name="to-flip-an-image-vertically-while-tiling"></a><span data-ttu-id="e33fd-123">바둑판식 배열 하는 동안에 세로로 이미지 대칭 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="e33fd-123">To flip an image vertically while tiling</span></span>  
  
-   <span data-ttu-id="e33fd-124">이 예제에서는 동일한 75 × 75 이미지를 사용 하 여 200 × 200 사각형을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="e33fd-124">This example uses the same 75×75 image to fill a 200×200 rectangle.</span></span> <span data-ttu-id="e33fd-125">래핑 모드 이미지를 세로로 대칭 이동로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e33fd-125">The wrap mode is set to flip the image vertically.</span></span>  
  
     [!code-csharp[System.Drawing.UsingABrush#33](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#33)]
     [!code-vb[System.Drawing.UsingABrush#33](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#33)]  
  
### <a name="to-flip-an-image-horizontally-and-vertically-while-tiling"></a><span data-ttu-id="e33fd-126">바둑판식 배열 하는 동안 가로 및 세로로 여러 이미지를 대칭 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="e33fd-126">To flip an image horizontally and vertically while tiling</span></span>  
  
-   <span data-ttu-id="e33fd-127">이 예제에서는 200 × 200 사각형 바둑판식으로 배열 하 같은 75 × 75 이미지를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e33fd-127">This example uses the same 75×75 image to tile a 200×200 rectangle.</span></span> <span data-ttu-id="e33fd-128">래핑 모드는 가로 및 세로로 이미지가 대칭으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e33fd-128">The wrap mode is set to flip the image both horizontally and vertically.</span></span> <span data-ttu-id="e33fd-129">다음 그림에서는 사각형 이미지가 바둑판식으로 배열 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e33fd-129">The following illustration shows how the rectangle is tiled by the image.</span></span> <span data-ttu-id="e33fd-130">이미지를 세로로 대칭은 하나의 타일에서 특정된 열에서 다음을 이동 하면과 하나의 타일에서 특정된 행을 이동 하면 이미지를 가로로 대칭 있는지 확인 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e33fd-130">Note that as you move from one tile to the next in a given row, the image is flipped horizontally, and as you move from one tile to the next in a given column, the image is flipped vertically.</span></span>  
  
 <span data-ttu-id="e33fd-131">![5 바둑판식으로 배열](../../../../docs/framework/winforms/advanced/media/tile5.gif "tile5")</span><span class="sxs-lookup"><span data-stu-id="e33fd-131">![Tile 5](../../../../docs/framework/winforms/advanced/media/tile5.gif "tile5")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#34](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.UsingABrush#34](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="e33fd-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e33fd-132">See Also</span></span>  
 [<span data-ttu-id="e33fd-133">브러시를 사용하여 도형 채우기</span><span class="sxs-lookup"><span data-stu-id="e33fd-133">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
