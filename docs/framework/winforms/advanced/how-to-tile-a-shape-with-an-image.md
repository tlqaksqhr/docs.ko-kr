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
# <a name="how-to-tile-a-shape-with-an-image"></a>방법: 도형에 이미지를 바둑판식으로 배열
타일을 층을 서로 옆에 배치할 것 처럼 사각형 이미지 서로 인접 (타일) 도형 채우기 배치할 수 있습니다. 도형의 내부가 바둑판식으로 배열 하려면 질감 브러시를 사용 합니다. 생성할 때는 <xref:System.Drawing.TextureBrush> 개체 생성자에 전달 하는 인수 중 하나는 <xref:System.Drawing.Image> 개체입니다. 질감 브러시를 사용 하 여 도형의 내부를 그리는 경우 셰이프가이 이미지의 반복된 복사본으로 채워집니다.  
  
 래핑 모드 속성은 <xref:System.Drawing.TextureBrush> 방법을 이미지는 사각형 그리드에서 반복 되는 대로 방향 개체를 확인 합니다. 눈금에서 타일 모두 동일한 방향을 만들 수 있습니다 또는 다음 그리드 위치에서 대칭 이동 이미지를 만들 수 있습니다. 반전 가로 스크롤 가능 세로 축 또는 둘 다 합니다. 다음 예에서는 대칭 이동 하는 여러 유형의 사용한 바둑판식 배열 보여 줍니다.  
  
### <a name="to-tile-an-image"></a>이미지를 바둑판식으로 배열 하려면  
  
-   이 예제에서는 200 × 200 사각형 바둑판식으로 배열 하 다음 75 × 75 이미지를 사용 합니다.  
  
 ![1 바둑판식으로 배열](../../../../docs/framework/winforms/advanced/media/tile1.gif "tile1")  
  
-   다음 그림에서는 사각형이 이미지와 바둑판식으로 배열 방법을 보여 줍니다. 모든 타일이 동일한 방향을;가 대칭 이동 하지 않습니다.  
  
 ![2 바둑판식으로 배열](../../../../docs/framework/winforms/advanced/media/tile2.gif "tile2")  
  
 [!code-csharp[System.Drawing.UsingABrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingABrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#31)]  
  
### <a name="to-flip-an-image-horizontally-while-tiling"></a>가로 바둑판식 배열 하는 동안 이미지 대칭 이동 하려면  
  
-   이 예제에서는 동일한 75 × 75 이미지를 사용 하 여 200 × 200 사각형을 채웁니다. 래핑 모드 이미지를 가로로 대칭 이동로 설정 됩니다. 다음 그림에서는 사각형이 이미지와 바둑판식으로 배열 방법을 보여 줍니다. 하나의 타일에서 특정된 행을 이동 하면 이미지 가로로 대칭을 참고 합니다.  
  
 ![타일 3](../../../../docs/framework/winforms/advanced/media/tile3.gif "tile3")  
  
 [!code-csharp[System.Drawing.UsingABrush#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.UsingABrush#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#32)]  
  
### <a name="to-flip-an-image-vertically-while-tiling"></a>바둑판식 배열 하는 동안에 세로로 이미지 대칭 이동 하려면  
  
-   이 예제에서는 동일한 75 × 75 이미지를 사용 하 여 200 × 200 사각형을 채웁니다. 래핑 모드 이미지를 세로로 대칭 이동로 설정 됩니다.  
  
     [!code-csharp[System.Drawing.UsingABrush#33](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#33)]
     [!code-vb[System.Drawing.UsingABrush#33](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#33)]  
  
### <a name="to-flip-an-image-horizontally-and-vertically-while-tiling"></a>바둑판식 배열 하는 동안 가로 및 세로로 여러 이미지를 대칭 이동 하려면  
  
-   이 예제에서는 200 × 200 사각형 바둑판식으로 배열 하 같은 75 × 75 이미지를 사용 합니다. 래핑 모드는 가로 및 세로로 이미지가 대칭으로 설정 됩니다. 다음 그림에서는 사각형 이미지가 바둑판식으로 배열 방법을 보여 줍니다. 이미지를 세로로 대칭은 하나의 타일에서 특정된 열에서 다음을 이동 하면과 하나의 타일에서 특정된 행을 이동 하면 이미지를 가로로 대칭 있는지 확인 하십시오.  
  
 ![5 바둑판식으로 배열](../../../../docs/framework/winforms/advanced/media/tile5.gif "tile5")  
  
 [!code-csharp[System.Drawing.UsingABrush#34](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.UsingABrush#34](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#34)]  
  
## <a name="see-also"></a>참고 항목  
 [브러시를 사용하여 도형 채우기](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
