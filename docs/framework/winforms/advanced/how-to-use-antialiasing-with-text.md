---
title: "방법: 텍스트에 앤티 앨리어싱 사용 | Microsoft Docs"
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
  - "앤티 앨리어싱, 텍스트에 사용"
  - "문자열[Windows Forms], 그릴 때 앤티 앨리어싱"
  - "문자열[Windows Forms], 그린 항목 다듬기"
  - "텍스트[Windows Forms], 앤티 앨리어싱"
  - "텍스트[Windows Forms], 다듬기"
ms.assetid: 48fc34f3-f236-4b01-a0cb-f0752e6d22ae
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: 텍스트에 앤티 앨리어싱 사용
*앤티 앨리어싱*은 그려진 그래픽과 텍스트의 거친 부분을 부드럽게 다듬어 그래픽과 텍스트의 모양과 가독성을 향상시키는 것을 말합니다.  관리되는 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 클래스를 사용하면 낮은 품질의 텍스트뿐만 아니라 고품질의 앤티 앨리어싱 텍스트를 렌더링할 수 있습니다.  일반적으로 고품질로 렌더링하려면 낮은 품질로 렌더링할 때보다 처리 시간이 오래 걸립니다.  텍스트 품질 수준을 설정하려면 <xref:System.Drawing.Graphics>의 <xref:System.Drawing.Graphics.TextRenderingHint%2A> 속성을 <xref:System.Drawing.Text.TextRenderingHint> 열거형의 요소 중 하나로 설정합니다.  
  
## 예제  
 다음 코드 예제에서는 두 가지의 다른 품질 설정을 사용하여 텍스트를 그립니다.  
  
 다음 그림은 코드 예제 코드의 실행 결과를 보여 줍니다.  
  
 ![글꼴 텍스트](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")  
  
 [!code-csharp[System.Drawing.FontsAndText#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  
  
## 코드 컴파일  
 위의 코드 예제는 Windows Forms에서 사용해야 하며 <xref:System.Windows.Forms.PaintEventHandler>의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`를 필요로 합니다.  
  
## 참고 항목  
 [글꼴 및 텍스트 사용](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)