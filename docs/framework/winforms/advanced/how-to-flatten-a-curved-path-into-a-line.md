---
title: "방법: 구부러진 경로를 선으로 펴기 | Microsoft Docs"
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
  - "곡선, 직선화"
  - "그리기, 곡선 펴기"
  - "Flatten 메서드"
  - "그래픽, 곡선을 선으로 펴기"
  - "GraphicsPath 개체"
  - "경로, 직선화"
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: 구부러진 경로를 선으로 펴기
<xref:System.Drawing.Drawing2D.GraphicsPath> 개체에는 일련의 선과 3차원 곡선 스플라인이 저장됩니다.  타원, 원호, 카디널 스플라인 같은 다양한 곡선을 경로에 추가할 수 있지만 각 곡선은 경로에 저장되기 전에 3차원 곡선 스플라인으로 변환됩니다.  경로의 각 3차원 곡선 스플라인을 일련의 직선으로 변환하는 과정을 통해 경로를 펼 수 있습니다.  다음 그림은 펴기 작업을 하기 전과 후의 경로를 보여 줍니다.  
  
 ![직선 및 곡선](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art32a.png "AboutGdip02\_Art32A")  
  
### 경로를 펴려면  
  
-   <xref:System.Drawing.Drawing2D.GraphicsPath> 개체의 <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> 메서드를 호출합니다.  <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> 메서드는 펴진 경로와 원래 경로 사이의 최대 거리를 지정하는 편평 인수를 받습니다.  
  
## 참고 항목  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=fullName>   
 [선, 곡선 및 도형](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [경로 구성 및 그리기](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)