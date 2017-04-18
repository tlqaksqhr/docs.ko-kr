---
title: "방법: 영역을 사용하여 클리핑 | Microsoft Docs"
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
  - "영역, 클리핑"
  - "영역, 그리기 화면 제한"
ms.assetid: 43d121b4-e14c-4901-b25c-2d6c25ba4e29
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: 영역을 사용하여 클리핑
<xref:System.Drawing.Graphics> 클래스의 속성 중 하나는 클리핑 영역입니다.  특정 <xref:System.Drawing.Graphics> 개체에서 수행하는 모든 그리기 작업은 해당 <xref:System.Drawing.Graphics> 개체의 클리핑 영역으로 제한됩니다.  <xref:System.Drawing.Graphics.SetClip%2A> 메서드를 호출하여 클리핑 영역을 설정할 수 있습니다.  
  
## 예제  
 아래 예제에서는 다각형 하나로 구성되는 경로를 만듭니다.  그런 다음 코드에서는 그 경로를 바탕으로 영역을 구성합니다.  그러면 이 영역이 <xref:System.Drawing.Graphics> 개체의 <xref:System.Drawing.Graphics.SetClip%2A> 메서드에 전달되고 두 개의 문자열이 그려집니다.  
  
 아래 그림에 클리핑된 문자열이 나와 있습니다.  
  
 ![클립](../../../../docs/framework/winforms/advanced/media/clip1.png "clip1")  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.MiscLegacyTopics#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#41)]  
  
## 코드 컴파일  
 앞의 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.PaintEventHandler>의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  
  
## 참고 항목  
 [GDI\+의 영역](../../../../docs/framework/winforms/advanced/regions-in-gdi.md)   
 [영역 사용](../../../../docs/framework/winforms/advanced/using-regions.md)