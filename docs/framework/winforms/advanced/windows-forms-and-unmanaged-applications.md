---
title: "Windows Forms 및 관리되지 않는 응용 프로그램 | Microsoft Docs"
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
  - "ActiveX 컨트롤[Windows Forms]"
  - "COM[Windows Forms]"
  - "COM interop, Windows Forms"
  - "Windows Forms, interop"
  - "Windows Forms, 관리되지 않는"
ms.assetid: 81bc100c-fa49-4614-85a6-0f7ab59eac8a
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Windows Forms 및 관리되지 않는 응용 프로그램
Windows Forms 응용 프로그램과 컨트롤은 관리되지 않는 응용 프로그램과 상호 운용될 수 있지만 몇 가지 주의할 사항이 있습니다.  다음 섹션에서는 Windows Forms 응용 프로그램과 컨트롤이 지원하는 시나리오 및 구성과 지원하지 않는 시나리오 및 구성을 설명합니다.  
  
## 단원 내용  
 [Windows Forms 및 관리되지 않는 응용 프로그램 개요](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications-overview.md)  
 관리되지 않는 응용 프로그램에서 작동하는 Windows Forms 컨트롤을 사용 및 구현하는 방법에 대한 일반적인 정보를 제공합니다.  
  
 [방법: ShowDialog 메서드로 Windows Form을 표시하여 COM Interop 지원](../../../../docs/framework/winforms/advanced/com-interop-by-displaying-a-windows-form-shadow.md)  
 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=fullName> 메서드를 사용하여 관리되지 않는 응용 프로그램에서 Windows Form을 실행하는 방법을 보여 주는 코드 예제를 제공합니다.  
  
 [방법: 각 Windows Form을 별개의 스레드에서 표시하여 COM Interop 지원](../../../../docs/framework/winforms/advanced/how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)  
 고유한 스레드에서 Windows Form을 실행하는 방법을 보여 주는 코드 예제를 제공합니다.  
  
 [연습: 각 Windows Form을 별개의 스레드에서 표시하여 COM Interop 지원](http://msdn.microsoft.com/library/ms233639\(v=vs.110\))을 참조하세요.  
  
## 참조  
 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=fullName>  
 Windows Form에 대한 별도 스레드를 만드는 데 사용됩니다.  
  
 <xref:System.Windows.Forms.Application.Run%2A?displayProperty=fullName>  
 스레드에 대한 메시지 루프를 시작합니다.  
  
 <xref:System.Windows.Forms.Control.Invoke%2A>  
 관리되지 않는 응용 프로그램에서의 폼 호출을 마샬링합니다.  
  
## 관련 단원  
 [.NET Framework 구성 요소를 COM에 노출](../../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 관리되지 않는 응용 프로그램에서 .NET Framework 형식을 사용하는 방법에 대한 일반적인 정보를 제공합니다.