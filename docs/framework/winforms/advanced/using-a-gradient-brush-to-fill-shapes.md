---
title: "그라데이션 브러시를 사용하여 도형 채우기 | Microsoft Docs"
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
  - "브러시, 그라데이션 브러시"
  - "예제[Windows Forms], 그라데이션 브러시"
  - "그라데이션 브러시"
ms.assetid: 2c6037b9-05bd-44c0-a22a-19584b722524
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 그라데이션 브러시를 사용하여 도형 채우기
그라데이션 브러시를 사용하면 점진적으로 변하는 색으로 도형을 채울 수 있습니다.  예를 들어, 가로 그라데이션을 사용하면 도형의 왼쪽 가장자리에서 오른쪽 가장자리로 가면서 점차 변하는 색으로 도형을 채울 수 있습니다.  왼쪽 가장자리는 검정\(빨강, 녹색, 파랑 구성 요소가 각각 0, 0, 0\)이고 오른쪽 가장자리는 빨강\(255, 0, 0\)인 사각형의 경우,  사각형의 너비가 256픽셀이면 각 픽셀의 빨강 구성 요소는 왼쪽에 있는 픽셀의 빨강 구성 요소보다 1씩 증가합니다.  따라서 행에서 가장 왼쪽 픽셀의 색 구성 요소는 \(0, 0, 0\)이고, 두 번째 픽셀은 \(1, 0, 0\), 세 번째 픽셀은 \(2, 0, 0\)이 되는 방식으로 빨강 구성 요소의 값이 1씩 증가하여 가장 오른쪽 픽셀의 색 구성 요소는 \(255, 0, 0\)이 됩니다.  이러한 방식으로 색 값을 삽입하여 색 그라데이션을 구성합니다.  
  
 선형 그라데이션에서는 가로 방향, 세로 방향 또는 지정한 사선 방향을 따라 색이 점진적으로 변합니다.  경로 그라데이션에서는 경로의 내부 및 경계 주변에서 따라 점진적으로 색이 변합니다.  경로 그라데이션을 사용자 지정하여 다양한 효과를 얻을 수 있습니다.  
  
 아래 그림에 선형 그라데이션 브러시로 채운 사각형과 경로 그라데이션 브러시로 채운 타원이 나와 있습니다.  
  
 ![그라데이션](../../../../docs/framework/winforms/advanced/media/gradient2.png "gradient2")  
  
## 단원 내용  
 [방법: 선형 그라데이션 만들기](../../../../docs/framework/winforms/advanced/how-to-create-a-linear-gradient.md)  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush> 클래스를 사용하여 선형 그라데이션을 만드는 방법을 보여 줍니다.  
  
 [방법: 경로 그라데이션 만들기](../../../../docs/framework/winforms/advanced/how-to-create-a-path-gradient.md)  
 <xref:System.Drawing.Drawing2D.PathGradientBrush> 클래스를 사용하여 경로 그라데이션을 만드는 방법을 보여 줍니다.  
  
 [방법: 그라데이션에 감마 보정 적용](../../../../docs/framework/winforms/advanced/how-to-apply-gamma-correction-to-a-gradient.md)  
 그라데이션 브러시로 감마 보정을 사용하는 방법을 보여 줍니다.  
  
## 참조  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=fullName>  
 이 클래스를 설명하며 이 클래스의 모든 멤버에 대한 링크를 포함합니다.  
  
 <xref:System.Drawing.Drawing2D.PathGradientBrush?displayProperty=fullName>  
 이 클래스를 설명하며 이 클래스의 모든 멤버에 대한 링크를 포함합니다.