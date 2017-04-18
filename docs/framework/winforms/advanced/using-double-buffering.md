---
title: "이중 버퍼링 사용 | Microsoft Docs"
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
  - "버퍼링, 이중 버퍼링"
  - "이중 버퍼링"
  - "깜빡임, Windows Forms에서 줄이기"
  - "그래픽, 이중 버퍼링"
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 이중 버퍼링 사용
이중 버퍼링된 그래픽을 사용하면 복잡한 그리기 작업이 포함된 응용 프로그램에서 깜빡임을 줄일 수 있습니다.  .NET Framework에서는 이중 버퍼링에 대한 지원을 기본적으로 제공하며 사용자가 그래픽을 직접 관리하거나 렌더링할 수도 있습니다.  
  
## 단원 내용  
 [이중 버퍼링 그래픽](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 이중 버퍼링 개념과 .NET Framework 지원에 대한 개요를 설명합니다.  
  
 [방법: 폼과 컨트롤에 이중 버퍼링을 사용하여 그래픽 깜빡임 줄이기](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 .NET Framework에서 기본 이중 버퍼링 지원을 사용하는 방법을 보여 줍니다.  
  
 [방법: 버퍼링된 그래픽 수동 관리](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)  
 응용 프로그램에서 이중 버퍼링을 관리하는 방법을 보여 줍니다.  
  
 [방법: 버퍼링된 그래픽 수동 렌더링](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)  
 이중 버퍼링된 그래픽을 렌더링하는 방법을 보여 줍니다.  
  
## 참조  
 <xref:System.Windows.Forms.Control.SetStyle%2A> ,  
 이중 버퍼링을 사용할 수 있도록 하는 컨트롤 메서드입니다.  
  
 <xref:System.Drawing.BufferedGraphicsContext> ,  
 그래픽 버퍼를 만드는 데 사용할 수 있는 메서드를 제공합니다.  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 응용 프로그램 도메인의 버퍼링된 그래픽 컨텍스트에 대한 액세스를 제공합니다.