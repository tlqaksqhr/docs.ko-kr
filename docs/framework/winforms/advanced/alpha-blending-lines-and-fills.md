---
title: "선 및 채우기 알파 혼합 | Microsoft Docs"
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
  - "알파 혼합"
  - "알파 혼합, 채우기에 사용"
  - "알파 혼합, 선에 사용"
  - "예제[Windows Forms], 알파 혼합"
  - "채우기, 알파 혼합"
  - "선, 투명도 추가"
  - "선, 알파 혼합"
  - "도형, 투명도 추가"
ms.assetid: 5440f48c-3ac9-44c3-b170-c1c110bdbab8
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 선 및 채우기 알파 혼합
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서 색은 알파, 빨강, 녹색 및 파랑 구성 요소 각각에 8비트씩 모두 32비트로 이루어진 값입니다.  알파 값은 색의 투명도, 즉 색이 배경색과 혼합되는 정도를 나타냅니다.  알파 값은 0에서 255 사이로, 0은 완전히 투명한 색을 나타내고 255는 완전히 불투명한 색을 나타냅니다.  
  
 알파 혼합에서는 원본 색 데이터와 배경색 데이터의 픽셀을 혼합합니다.  아래와 같은 공식에 따라 원본 색의 세 가지 구성 요소\(빨강, 녹색, 파랑\)가 배경색의 각 구성 요소와 혼합됩니다.  
  
 displayColor \= sourceColor × alpha \/ 255 \+ backgroundColor × \(255 \- alpha\) \/ 255  
  
 예를 들어 원본 색의 빨강 구성 요소가 150이고 배경색의 빨강 구성 요소는 100인 경우  알파 값이 200이면 빨강 구성 요소의 결과 색은 다음과 같이 계산됩니다.  
  
 150 × 200 \/ 255 \+ 100 × \(255 – 200\) \/ 255 \= 139  
  
## 단원 내용  
 [방법: 불투명 및 반투명 선 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-opaque-and-semitransparent-lines.md)  
 알파 혼합 선을 그리는 방법에 대해 설명합니다.  
  
 [방법: 불투명 및 반투명 브러시를 사용하여 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-with-opaque-and-semitransparent-brushes.md)  
 브러시를 사용하여 알파 혼합하는 방법에 대해 설명합니다.  
  
 [방법: 합성 모드를 사용하여 알파 혼합 조절](../../../../docs/framework/winforms/advanced/how-to-use-compositing-mode-to-control-alpha-blending.md)  
 <xref:System.Drawing.Drawing2D.CompositingMode>를 사용하여 알파 혼합을 제어하는 방법에 대해 설명합니다.  
  
 [방법: 색 매트릭스를 사용하여 이미지에 알파 값 설정](../../../../docs/framework/winforms/advanced/how-to-use-a-color-matrix-to-set-alpha-values-in-images.md)  
 <xref:System.Drawing.Imaging.ColorMatrix> 개체를 사용하여 알파 혼합을 제어하는 방법에 대해 설명합니다.