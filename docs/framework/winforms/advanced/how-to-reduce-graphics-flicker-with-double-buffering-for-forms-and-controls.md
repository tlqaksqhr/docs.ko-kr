---
title: "방법: 폼과 컨트롤에 이중 버퍼링을 사용하여 그래픽 깜빡임 줄이기 | Microsoft Docs"
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
  - "DoubleBuffered 속성"
  - "깜빡임, Windows Forms에서 줄이기"
  - "그래픽, 이중 버퍼링된 깜빡임 줄이기"
ms.assetid: 91083d3a-653f-4f15-a467-0f37b2aa39d6
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: 폼과 컨트롤에 이중 버퍼링을 사용하여 그래픽 깜빡임 줄이기
이중 버퍼링에서는 메모리 버퍼를 사용하여 다중 그리기 작업과 관련된 깜빡임 문제를 해결합니다.  이중 버퍼링을 사용하는 경우 모든 그리기 작업은 그리기 화면 대신 메모리 버퍼에 먼저 렌더링됩니다.  모든 그리기 작업이 완료되면 연결된 그리기 화면에 메모리 버퍼가 직접 복사됩니다.  그래픽 작업이 화면에서 하나만 수행되기 때문에 복잡한 그리기 작업과 관련된 이미지 깜빡임이 제거됩니다. 대부분의 응용 프로그램의 경우 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]에서 제공하는 기본 이중 버퍼링을 사용하는 것이 가장 좋습니다.  표준 Windows Forms 컨트롤은 기본적으로 이중 버퍼링됩니다.  폼 및 작성된 컨트롤에서 기본 이중 버퍼링을 두 가지 방식으로 사용할 수 있습니다.  <xref:System.Windows.Forms.Control.DoubleBuffered%2A> 속성을 `true`로 설정하거나 <xref:System.Windows.Forms.Control.SetStyle%2A> 메서드를 호출하여 <xref:System.Windows.Forms.ControlStyles> 플래그를 `true`로 설정할 수 있습니다.  두 메서드 모두 폼 또는 컨트롤에 대해 기본 이중 버퍼링을 사용하고 깜빡임 없는 그래픽 렌더링을 제공합니다.  모든 렌더링 코드를 사용자가 작성한 사용자 지정 컨트롤에 대해서만 <xref:System.Windows.Forms.Control.SetStyle%2A> 메서드를 호출하는 것이 좋습니다.  
  
 애니메이션 또는 고급 메모리 관리와 같은 보다 수준 높은 이중 버퍼링 시나리오의 경우 원하는 이중 버퍼링 논리를 구현할 수 있습니다.  자세한 내용은 [방법: 버퍼링된 그래픽 수동 관리](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)를 참조하십시오.  
  
### 깜빡임을 줄이려면  
  
-   <xref:System.Windows.Forms.Control.DoubleBuffered%2A> 속성을 `true`으로 설정합니다.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#31)]  
  
 \-또는\-  
  
-   <xref:System.Windows.Forms.Control.SetStyle%2A> 메서드를 호출하여 <xref:System.Windows.Forms.ControlStyles> 플래그를 `true`로 설정합니다.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#32)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#32)]  
  
## 참고 항목  
 <xref:System.Windows.Forms.Control.DoubleBuffered%2A>   
 <xref:System.Windows.Forms.Control.SetStyle%2A>   
 [이중 버퍼링 그래픽](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)   
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)