---
title: "이중 버퍼링 그래픽 | Microsoft Docs"
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
  - "이중 버퍼링"
  - "예제[Windows Forms], 이중 버퍼링된 그래픽"
  - "깜빡임, 이중 버퍼링으로 줄이기"
  - "그래픽, 이중 버퍼링"
ms.assetid: 4f6fef99-0972-436e-9d73-0167e4033f71
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 이중 버퍼링 그래픽
깜빡임은 그래픽을 프로그래밍할 때 일반적으로 발생하는 문제입니다.  여러 복잡한 그리기 작업이 필요한 그래픽 작업에서는 렌더링된 이미지에 깜빡임 현상이 발생하거나 의도하지 않은 모양이 나타날 수 있습니다.  이 문제를 해결하기 위해 .NET Framework에서는 이중 버퍼링에 대한 액세스를 제공합니다.  
  
 이중 버퍼링에서는 메모리 버퍼를 사용하여 다중 그리기 작업과 관련된 깜빡임 문제를 해결합니다.  이중 버퍼링을 사용하는 경우 모든 그리기 작업은 그리기 화면 대신 메모리 버퍼에 먼저 렌더링됩니다.  모든 그리기 작업이 완료되면 연결된 그리기 화면에 메모리 버퍼가 직접 복사됩니다.  그래픽 작업이 화면에서 하나만 수행되기 때문에 복잡한 그리기 작업과 관련된 이미지 깜빡임이 제거됩니다.  
  
## 기본 이중 버퍼링  
 응용 프로그램에서 이중 버퍼링을 사용하는 가장 쉬운 방법은 .NET Framework에 제공되는 폼 및 컨트롤에 대한 기본 이중 버퍼링을 사용하는 것입니다.  <xref:System.Windows.Forms.Control.DoubleBuffered%2A> 속성을 `true`로 설정하거나 <xref:System.Windows.Forms.Control.SetStyle%2A> 메서드를 사용하여 Windows Forms 및 작성된 Windows 컨트롤에 대한 기본 이중 버퍼링을 사용할 수 있습니다.  자세한 내용은 [방법: 폼과 컨트롤에 이중 버퍼링을 사용하여 그래픽 깜빡임 줄이기](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)를 참조하십시오.  
  
## 버퍼링된 그래픽 수동 관리  
 애니메이션 또는 고급 메모리 관리와 같은 고급 이중 버퍼링 시나리오에서는 .NET Framework 클래스를 사용하여 사용자의 이중 버퍼링 논리를 구현할 수 있습니다.  개별 그래픽 버퍼를 할당 및 관리하는 클래스는 <xref:System.Drawing.BufferedGraphicsContext> 클래스입니다.  모든 응용 프로그램 도메인에는 해당 응용 프로그램에 대한 모든 기본 이중 버퍼링을 관리하는 자체의 기본 <xref:System.Drawing.BufferedGraphicsContext> 인스턴스가 있습니다.  대부분의 경우 응용 프로그램 당 응용 프로그램 도메인이 하나만 있으므로 응용 프로그램 당 하나의 기본 <xref:System.Drawing.BufferedGraphicsContext>가 있습니다.  기본 <xref:System.Drawing.BufferedGraphicsContext> 인스턴스는 <xref:System.Drawing.BufferedGraphicsManager> 클래스에서 관리합니다.  [BufferedGraphicsManager.Current 속성](frlrfSystemDrawingBufferedGraphicsManagerClassCurrentTopic)을 호출하여 기본 <xref:System.Drawing.BufferedGraphicsContext> 인스턴스에 대한 참조를 검색할 수 있습니다.  전용 <xref:System.Drawing.BufferedGraphicsContext> 인스턴스를 만들어 그래픽 위주 응용 프로그램의 성능을 향상시킬 수도 있습니다.  <xref:System.Drawing.BufferedGraphicsContext> 인스턴스를 만드는 방법에 대한 자세한 내용은 [방법: 버퍼링된 그래픽 수동 관리](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)를 참조하십시오.  
  
## 버퍼링된 그래픽 수동 표시  
 <xref:System.Drawing.BufferedGraphics> 클래스의 인스턴스를 반환하는 [BufferedGraphicsContext.Allocate 메서드](frlrfSystemDrawingBufferedGraphicsContextClassAllocateTopic)를 호출함으로써 <xref:System.Drawing.BufferedGraphicsContext> 클래스의 인스턴스를 사용하여 그래픽 버퍼를 만들 수 있습니다.  <xref:System.Drawing.BufferedGraphics> 개체는 폼 또는 컨트롤과 같은 렌더링 화면에 연결되는 메모리 버퍼를 관리합니다.  
  
 인스턴스화된 후 <xref:System.Drawing.BufferedGraphics> 클래스는 메모리 내 그래픽 버퍼에 대한 렌더링을 관리합니다.  [BufferedGraphics.Graphics 속성](frlrfSystemDrawingBufferedGraphicsClassGraphicsTopic)을 통해 그래픽을 메모리 버퍼에 렌더링할 수 있습니다. 이 속성은 메모리 버퍼를 직접 나타내는 <xref:System.Drawing.Graphics> 개체를 노출합니다.  그리기 화면을 표시하는 <xref:System.Drawing.Graphics> 개체에서와 마찬가지로 이 <xref:System.Drawing.Graphics> 개체에 그릴 수 있습니다.  모든 그래픽이 버퍼에 그려지면 [BufferedGraphics.Render 메서드](frlrfSystemDrawingBufferedGraphicsClassRenderTopic)를 사용하여 버퍼 내용을 그리기 화면에 복사할 수 있습니다.  
  
 <xref:System.Drawing.BufferedGraphics> 클래스 사용에 대한 자세한 내용은 [버퍼링된 그래픽 수동 렌더링](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)을 참조하십시오.  그래픽 렌더링에 대한 자세한 내용은 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Drawing.BufferedGraphics>   
 <xref:System.Drawing.BufferedGraphicsContext>   
 <xref:System.Drawing.BufferedGraphicsManager>   
 [방법: 버퍼링된 그래픽 수동 렌더링](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)   
 [방법: 폼과 컨트롤에 이중 버퍼링을 사용하여 그래픽 깜빡임 줄이기](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)   
 [방법: 버퍼링된 그래픽 수동 관리](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)   
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)