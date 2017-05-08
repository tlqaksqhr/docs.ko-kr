---
title: "방법: 사용자 지정 레이아웃 엔진 구현 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "FlowLayoutPanel 컨트롤[Windows Forms], 레이아웃 엔진"
  - "레이아웃 엔진, 사용자 지정"
  - "레이아웃 엔진, 구현"
  - "LayoutEngine 클래스"
  - "TableLayoutPanel 컨트롤[Windows Forms], 레이아웃 엔진"
ms.assetid: f91aa91c-29f4-4089-95ca-5d48b774b00e
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: 사용자 지정 레이아웃 엔진 구현
다음 코드 예제에서는 간단한 선형 레이아웃을 수행하는 사용자 지정 레이아웃 엔진을 만드는 방법을 보여 줍니다.  이 코드는 `DemoFlowPanel`이라는 Panel 컨트롤을 구현합니다. 이 컨트롤은 <xref:System.Windows.Forms.Control.LayoutEngine%2A> 속성을 재정의하여 `DemoFlowLayout` 클래스의 인스턴스를 제공합니다.  
  
## 예제  
 [!code-cpp[System.Windows.Forms.Layout.LayoutEngine#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/cpp/DemoFlowLayout.cpp#1)]
 [!code-csharp[System.Windows.Forms.Layout.LayoutEngine#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/CS/DemoFlowLayout.cs#1)]
 [!code-vb[System.Windows.Forms.Layout.LayoutEngine#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Layout.LayoutEngine/VB/DemoFlowLayout.vb#1)]  
  
## 참고 항목  
 <xref:System.Windows.Forms.Layout.LayoutEngine>   
 <xref:System.Windows.Forms.Control.LayoutEngine%2A?displayProperty=fullName>