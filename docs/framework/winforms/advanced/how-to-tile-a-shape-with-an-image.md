---
title: "방법: 도형에 이미지를 바둑판식으로 배열 | Microsoft Docs"
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
  - "비트맵[Windows Forms], 모양 채우기"
  - "이미지[Windows Forms], 모양 채우기"
  - "도형, 이미지를 바둑판식으로 배열"
  - "질감 브러시, 이미지를 바둑판식으로 배열"
ms.assetid: 6d407891-6e5c-4495-a546-3da5604e9fb8
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: 도형에 이미지를 바둑판식으로 배열
바닥을 타일로 덮듯이 사각형 이미지를 하나씩 맞닿게 붙여 놓아 도형을 채울 수 있습니다. 즉, 이미지를 바둑판식으로 배열할 수 있습니다.  도형의 내부를 바둑판식으로 채우려면 질감 브러시를 사용합니다.  <xref:System.Drawing.TextureBrush> 개체를 생성할 때 생성자에 전달하는 인수 중 하나는 <xref:System.Drawing.Image> 개체입니다.  질감 브러시를 사용하여 도형 내부를 칠할 때는 이 이미지의 복사본을 반복적으로 사용하여 도형이 채워집니다.  
  
 <xref:System.Drawing.TextureBrush> 개체의 랩 모드 속성에서는 사각형 모눈에서 이미지를 반복적으로 배열하는 방향을 지정합니다.  모눈에 이미지를 바둑판식으로 배열할 때 모두 같은 방향으로 배열하거나 서로 대칭 방향으로 배열할 수 있습니다.  가로, 세로 또는 두 방향 모두에서 대칭으로 배열할 수 있습니다.  아래 예제에서는 여러 유형으로 대칭 이동되는 바둑판식 배열을 보여 줍니다.  
  
### 이미지를 바둑판식으로 배열하려면  
  
-   이 예제에서는 다음 75×75 이미지를 200×200 사각형에 바둑판식으로 배열합니다.  
  
 ![바둑판식 배열 1](../../../../docs/framework/winforms/advanced/media/tile1.png "tile1")  
  
-   아래 그림에서는 이미지가 바둑판식으로 배열된 사각형을 보여 줍니다.  이 그림에서 배열된 이미지의 방향은 모두 같고 대칭되지 않음을 알 수 있습니다.  
  
 ![바둑판식 배열 2](../../../../docs/framework/winforms/advanced/media/tile2.png "tile2")  
  
 [!code-csharp[System.Drawing.UsingABrush#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingABrush#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#31)]  
  
### 바둑판식으로 배열할 때 이미지를 좌우 대칭 이동하려면  
  
-   이 예제에서는 같은 75×75 이미지를 200×200 사각형에 채웁니다.  이미지가 가로 대칭으로 배열되도록 랩 모드를 설정합니다.  아래 그림에서는 이미지가 바둑판식으로 배열된 사각형을 보여 줍니다.  이 그림에서는 행을 따라가며 이미지가 가로 대칭으로 배열된 것을 알 수 있습니다.  
  
 ![바둑판식 배열 3](../../../../docs/framework/winforms/advanced/media/tile3.png "tile3")  
  
 [!code-csharp[System.Drawing.UsingABrush#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.UsingABrush#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#32)]  
  
### 바둑판식으로 배열할 때 이미지를 상하 대칭 이동하려면  
  
-   이 예제에서는 같은 75×75 이미지를 200×200 사각형에 채웁니다.  이미지가 세로 대칭으로 배열되도록 랩 모드를 설정합니다.  
  
     [!code-csharp[System.Drawing.UsingABrush#33](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#33)]
     [!code-vb[System.Drawing.UsingABrush#33](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#33)]  
  
### 바둑판식으로 배열할 때 이미지를 상하 및 좌우 대칭 이동하려면  
  
-   이 예제에서는 같은 75×75 이미지를 200×200 사각형에 바둑판식으로 배열합니다.  이미지가 가로 및 세로 대칭으로 배열되도록 랩 모드를 설정합니다.  아래 그림에서는 이미지가 바둑판식으로 배열된 사각형을 보여 줍니다.  이 그림에서는 배열된 이미지가 행을 따라가며 가로로 대칭일 뿐만 아니라 열을 따라가며 세로로 대칭되어 있음을 알 수 있습니다.  
  
 ![바둑판식 배열 5](../../../../docs/framework/winforms/advanced/media/tile5.png "tile5")  
  
 [!code-csharp[System.Drawing.UsingABrush#34](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#34)]
 [!code-vb[System.Drawing.UsingABrush#34](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#34)]  
  
## 참고 항목  
 [브러시를 사용하여 도형 채우기](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)