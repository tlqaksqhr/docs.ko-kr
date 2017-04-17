---
title: "좌표계 형식 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "좌표계"
  - "장치 좌표계"
  - "페이지 좌표계"
  - "페이지 변환"
  - "변환, 페이지"
  - "변환, 세계"
  - "측정 단위"
  - "표준 좌표계"
  - "표준 변환"
ms.assetid: c61ff50a-eb1d-4e6c-83cd-f7e9764cfa9f
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 좌표계 형식
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서는 영역, 페이지, 장치라는 세 개의 좌표 공간을 사용합니다.  영역 좌표는 특정 그래픽 영역을 모델링하는 데 사용되는 좌표이며 .NET Framework에서 메서드에 전달됩니다.  페이지 좌표는 폼이나 컨트롤 같은 그리기 화면에서 사용하는 좌표계를 참조하고  장치 좌표는 화면이나 용지 같이 항목이 그려지는 실제 장치에서 사용하는 좌표입니다.  `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`을 호출하면 <xref:System.Drawing.Graphics.DrawLine%2A> 메서드에 전달되는 점 `(0, 0)`과 `(160, 80)`은 영역 좌표 공간에 배치됩니다.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서 화면에 선을 그리려면 좌표에서 일련의 변환 과정을 수행해야 하는데  먼저 전역 변환을 통해 영역 좌표를 페이지 좌표로 변환하고 페이지 변환을 통해 이 좌표를 다시 장치 좌표로 변환해야 합니다.  
  
## 변환 및 좌표계  
 원점이 왼쪽 위 모퉁이에 존재하는 대신 클라이언트 공간의 본문 부분에 존재하는 좌표 시스템을 사용하려는 경우를 가정해 보겠습니다.  예를 들어, 클라이언트 공간의 왼쪽 가장자리에서 100픽셀, 클라이언트 공간의 위에서 50픽셀 떨어진 위치에 원점을 만들려고 합니다.  다음 그림은 이 좌표계를 나타냅니다.  
  
 ![좌표계](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art01.png "AboutGdip05\_art01")  
  
 `myGraphics.DrawLine(myPen, 0, 0, 160, 80)`을 호출하면 다음 그림과 같은 선이 표시됩니다.  
  
 ![좌표계](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art02.png "AboutGdip05\_art02")  
  
 세 좌표 공간에서 이 선의 끝점 좌표는 다음과 같습니다.  
  
|||  
|-|-|  
|World|\(0, 0\) \- \(160, 80\)|  
|페이징|\(100, 50\) \- \(260, 130\)|  
|장치|\(100, 50\) \- \(260, 130\)|  
  
 여기서 페이지 좌표 공간의 원점은 언제나 클라이언트 공간의 왼쪽 위 모퉁이에 존재한다는 점에 주의합니다.  또한 측정 단위가 픽셀이므로 장치 좌표와 페이지 좌표가 동일하다는 점에 주의합니다.  측정 단위를 픽셀이 아닌 다른 단위\(예: 인치\)로 설정한다면 장치 좌표와 페이지 좌표가 다르게 나타날 것입니다.  
  
 영역 좌표를 페이지 좌표에 매핑하는 전역 변환은 <xref:System.Drawing.Graphics> 클래스의 <xref:System.Drawing.Graphics.Transform%2A> 속성에 저장됩니다.  위의 예제에서 전역 변환은 x축으로 100단위, y축으로 50단위를 변환한 것입니다.  다음 예제에서는 <xref:System.Drawing.Graphics> 개체의 전역 변환을 설정한 다음 이 <xref:System.Drawing.Graphics> 개체를 사용하여 위의 그림에 표시된 선을 그립니다.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.CoordinateSystems#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#31)]  
  
 페이지 변환은 페이지 좌표를 장치 좌표에 매핑합니다.  <xref:System.Drawing.Graphics> 클래스는 페이지 변환을 처리할 수 있도록 <xref:System.Drawing.Graphics.PageUnit%2A> 및 <xref:System.Drawing.Graphics.PageScale%2A> 속성을 제공합니다.  또한 <xref:System.Drawing.Graphics> 클래스는 디스플레이 장치의 가로 및 세로 dpi를 검사할 수 있도록 <xref:System.Drawing.Graphics.DpiX%2A>와 <xref:System.Drawing.Graphics.DpiY%2A>라는 두 가지 읽기 전용 속성을 제공합니다.  
  
 <xref:System.Drawing.Graphics> 클래스의 <xref:System.Drawing.Graphics.PageUnit%2A> 속성을 사용하여 픽셀 이외의 다른 측정 단위를 지정할 수 있습니다.  
  
> [!NOTE]
>  <xref:System.Drawing.Graphics.PageUnit%2A> 속성을 <xref:System.Drawing.GraphicsUnit>로 설정할 수는 없습니다. 이는 실제 단위가 아니고 예외를 발생시키기 때문입니다.  
  
 다음 예제는 \(0, 0\)에서 \(2, 1\)로 선을 그립니다. 점 \(2, 1\)은 점 \(0, 0\)에서 2인치 오른쪽, 1인치 아래에 있는 것입니다.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.CoordinateSystems#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#32)]  
  
> [!NOTE]
>  펜을 만들 때 펜 굵기를 지정하지 않은 경우 위의 예제를 실행하면 두께가 1인치인 선이 그려집니다.  다음과 같이 <xref:System.Drawing.Pen> 생성자의 두 번째 인수에 펜 굵기를 지정할 수 있습니다.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#33](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#33)]
 [!code-vb[System.Drawing.CoordinateSystems#33](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#33)]  
  
 디스플레이 장치의 인치 당 도트 수를 각각 세로 96개, 가로 96개라고 가정하면, 세 좌표 공간에서 위 예제에 나온 선의 끝점 좌표는 다음과 같습니다.  
  
|||  
|-|-|  
|World|\(0, 0\) \- \(2, 1\)|  
|페이징|\(0, 0\) \- \(2, 1\)|  
|장치|\(0, 0\) \- \(192, 96\)|  
  
 영역 좌표 공간의 원점이 클라이언트 공간의 왼쪽 위 모퉁이에 존재하므로, 페이지 좌표와 영역 좌표는 동일합니다.  
  
 기하학적 변환과 페이지 변환을 함께 사용하면 다양한 효과를 낼 수 있습니다.  예를 들어, 측정 단위로 인치로 사용하여 클라이언트 공간의 왼쪽 가장자리에서 2인치, 클라이언트 공간의 위에서 2\/1인치만큼 떨어진 위치에 원점을 만들려고 합니다.  다음 예제에서는 <xref:System.Drawing.Graphics> 개체의 전역 변환과 페이지 변환을 설정한 다음 \(0, 0\)에서 \(2, 1\)로 선을 그립니다.  
  
 [!code-csharp[System.Drawing.CoordinateSystems#34](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.CoordinateSystems#34](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.CoordinateSystems/VB/Class1.vb#34)]  
  
 다음 그림은 이 선과 좌표계를 나타냅니다.  
  
 ![좌표계](../../../../docs/framework/winforms/advanced/media/aboutgdip05-art03.png "AboutGdip05\_art03")  
  
 디스플레이 장치의 인치 당 도트 수를 각각 세로 96개, 가로 96개라고 가정하면, 세 좌표 공간에서 위 예제에 나온 선의 끝점 좌표는 다음과 같습니다.  
  
|||  
|-|-|  
|World|\(0, 0\) \- \(2, 1\)|  
|페이징|\(2, 0.5\) \- \(4, 1.5\)|  
|장치|\(192, 48\) \- \(384, 144\)|  
  
## 참고 항목  
 [좌표계 및 변환](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)   
 [매트릭스에 의한 변환 표시](../../../../docs/framework/winforms/advanced/matrix-representation-of-transformations.md)