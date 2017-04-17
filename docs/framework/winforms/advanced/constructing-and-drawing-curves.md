---
title: "곡선 구성 및 그리기 | Microsoft Docs"
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
  - "곡선, 그리기"
  - "그리기, 곡선"
  - "예제[Windows Forms], 곡선 그리기"
ms.assetid: 76e92623-4130-4644-b867-faca58bdb3a2
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 곡선 구성 및 그리기
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]에서는 타원, 원호, 카디널 스플라인 및 3차원 곡선 스플라인과 같은 여러 종류의 곡선을 지원합니다.  타원은 그것을 둘러싸는 사각형으로 정의되며, 원호는 시작 각도와 전진 각도로 정의되는 타원의 일부입니다.  카디널 스플라인은 점의 배열과 장력 매개 변수로 정의됩니다. 배열의 각 점을 지나는 부드러운 곡선이 그려지며 곡선의 굴곡 정도는 장력 매개 변수에 의해 영향을 받습니다.  3차원 곡선 스플라인은 두 끝점과 두 제어점으로 정의됩니다. 제어점은 한 끝점과 다른 끝점 사이에 그려지는 곡선의 굴곡 정도와 방향에 영향을 미치지만 곡선이 제어점을 지나 그려지는 것은 아닙니다.  
  
## 단원 내용  
 [방법: 카디널 스플라인 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-cardinal-splines.md)  
 카디널 스플라인 및 카디널 스플라인을 그리는 방법에 대해 설명합니다.  
  
 [방법: 단일 3차원 곡선 스플라인 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-a-single-bezier-spline.md)  
 3차원 곡선 스플라인 및 3차원 곡선 스플라인을 그리는 방법에 대해 설명합니다.  
  
 [방법: 일련의 3차원 곡선 스플라인 그리기](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)  
 여러 3차원 곡선 스플라인을 순서대로 그리는 방법에 대해 설명합니다.