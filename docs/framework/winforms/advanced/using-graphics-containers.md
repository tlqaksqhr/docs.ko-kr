---
title: "Graphics 컨테이너 사용 | Microsoft Docs"
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
  - "예제[Windows Forms], Graphics 컨테이너"
  - "Graphics 컨테이너"
  - "그래픽, 컨테이너 사용"
ms.assetid: 74632f91-cefa-4f51-ab7c-f9ac91942caf
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Graphics 컨테이너 사용
<xref:System.Drawing.Graphics> 개체는 벡터 이미지, 래스터 이미지 및 텍스트를 표시하기 위한 <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A> 및 <xref:System.Drawing.Graphics.DrawString%2A> 등과 같은 메서드를 제공합니다.  <xref:System.Drawing.Graphics> 개체에는 그리는 항목의 품질과 방향에 영향을 미치는 몇 가지 속성도 있습니다.  예를 들어, 다듬기 모드 속성은 선과 곡선에 앤티 앨리어싱의 적용 여부를 결정하며 전역 변환 속성은 그리는 항목의 위치와 회전에 영향을 미칩니다.  
  
 <xref:System.Drawing.Graphics> 개체는 특정 디스플레이 장치와 연결됩니다.  창에서 <xref:System.Drawing.Graphics> 개체를 사용하여 그릴 때 <xref:System.Drawing.Graphics> 개체는 해당 창과도 연결됩니다.  
  
 <xref:System.Drawing.Graphics> 개체는 그리기에 영향을 미치는 속성 집합을 포함하며 장치 관련 정보와 연결되어 있으므로 컨테이너라고 할 수 있습니다.  기존 <xref:System.Drawing.Graphics> 개체의 <xref:System.Drawing.Graphics.BeginContainer%2A> 메서드를 호출하여 <xref:System.Drawing.Graphics> 개체 안에 또다른 컨테이너를 만들 수 있습니다.  
  
## 단원 내용  
 [Graphics 개체의 상태 관리](../../../../docs/framework/winforms/advanced/managing-the-state-of-a-graphics-object.md)  
 <xref:System.Drawing.Graphics> 개체의 품질 설정, 클리핑 영역 및 변환을 관리하는 방법에 대해 설명합니다.  
  
 [중첩된 Graphics 컨테이너 사용](../../../../docs/framework/winforms/advanced/using-nested-graphics-containers.md)  
 컨테이너를 사용하여 <xref:System.Drawing.Graphics> 개체 상태를 제어하는 방법에 대해 설명합니다.