---
title: "방법: 버퍼링된 그래픽 수동 관리 | Microsoft Docs"
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
  - "BufferedGraphicsContext 클래스"
  - "깜빡임, 그래픽을 수동으로 관리하여 줄이기"
  - "그래픽, 버퍼링된 그래픽 관리"
ms.assetid: 4c2a90ee-bbbe-4ff6-9170-1b06c195c918
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 버퍼링된 그래픽 수동 관리
보다 수준 높은 이중 버퍼링 시나리오의 경우 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 클래스를 사용하여 원하는 이중 버퍼링 논리를 구현할 수 있습니다.  개별 그래픽 버퍼를 할당 및 관리하는 클래스는 <xref:System.Drawing.BufferedGraphicsContext> 클래스입니다.  모든 응용 프로그램에는 해당 응용 프로그램에 대한 모든 기본 이중 버퍼링을 관리하는 자체 기본 <xref:System.Drawing.BufferedGraphicsContext>가 있습니다.  <xref:System.Drawing.BufferedGraphicsManager.Current%2A>를 호출하여 이 인스턴스에 대한 참조를 검색할 수 있습니다.  
  
### 기본 BufferedGraphicsContext에 대한 참조를 가져오려면  
  
-   다음 코드 예제에서처럼 <xref:System.Drawing.BufferedGraphicsManager.Current%2A> 속성을 설정합니다.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    >  <xref:System.Drawing.BufferedGraphicsManager> 클래스에서 받는 <xref:System.Drawing.BufferedGraphicsContext> 참조에서는 `Dispose` 메서드를 호출할 필요가 없습니다.  <xref:System.Drawing.BufferedGraphicsManager>는 기본 <xref:System.Drawing.BufferedGraphicsContext> 인스턴스에 대한 모든 메모리 할당과 배포를 처리합니다.  
  
     애니메이션과 같은 그래픽 위주의 응용 프로그램에서는 경우에 따라 <xref:System.Drawing.BufferedGraphicsManager>에서 제공하는 <xref:System.Drawing.BufferedGraphicsContext> 대신 전용 <xref:System.Drawing.BufferedGraphicsContext>를 사용하여 성능을 향상시킬 수 있습니다.  이렇게 하면 그래픽 버퍼를 개별적으로 만들고 관리할 수 있습니다. 이 때 응용 프로그램에서 많은 메모리가 사용되더라도 응용 프로그램에 연결된 다른 모든 버퍼링된 그래픽 관리에 대한 성능 오버헤드가 발생하지 않습니다.  
  
### 전용 BufferedGraphicsContext를 만들려면  
  
-   다음 코드 예제에서처럼 <xref:System.Drawing.BufferedGraphicsContext> 클래스의 새 인스턴스를 선언하고 만듭니다.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## 참고 항목  
 <xref:System.Drawing.BufferedGraphicsContext>   
 [이중 버퍼링 그래픽](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)   
 [방법: 버퍼링된 그래픽 수동 렌더링](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)