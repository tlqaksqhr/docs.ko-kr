---
title: "Windows Forms 컨트롤의 이벤트 | Microsoft Docs"
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
  - "사용자 지정 컨트롤[Windows Forms], 이벤트 개요(코드 사용)"
  - "이벤트[Windows Forms], 사용자 지정 컨트롤(코드 사용)"
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Windows Forms 컨트롤의 이벤트
Windows Forms 컨트롤에서는 <xref:System.Windows.Forms.Control?displayProperty=fullName>에서 60개 이상의 이벤트가 상속됩니다.  이러한 이벤트에는 컨트롤을 그리는 <xref:System.Windows.Forms.Control.Paint> 이벤트, <xref:System.Windows.Forms.Control.Resize> 및 <xref:System.Windows.Forms.Control.Layout> 이벤트와 같이 창 표시에 관련된 이벤트, 하위 수준 마우스 및 키보드 이벤트 등이 포함됩니다.  일부 하위 수준 이벤트는 <xref:System.Windows.Forms.Control>에 의해 <xref:System.Windows.Forms.Control.Click> 및 <xref:System.Windows.Forms.Control.DoubleClick>과 같은 의미 이벤트로 통합됩니다.  상속된 이벤트에 대한 자세한 내용은 <xref:System.Windows.Forms.Control>을 참조하십시오.  
  
 사용자 지정 컨트롤이 상속된 이벤트 기능을 재정의해야 할 경우 대리자를 연결하는 대신 상속된 `On`*EventName* 메서드를 재정의합니다.  .NET Framework의 이벤트 모델에 대해 잘 모르는 경우 [구성 요소에서 이벤트 발생시키기](../Topic/Raising%20Events%20from%20a%20Component.md)를 참조하십시오.  
  
## 참고 항목  
 [OnPaint 메서드 재정의](../../../../docs/framework/winforms/controls/overriding-the-onpaint-method.md)   
 [사용자 입력 처리](../../../../docs/framework/winforms/controls/handling-user-input.md)   
 [이벤트 정의](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)   
 [이벤트](../../../../docs/standard/events/index.md)