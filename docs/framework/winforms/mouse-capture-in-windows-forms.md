---
title: "Windows Forms의 마우스 캡처 | Microsoft Docs"
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
  - "마우스, capture"
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Windows Forms의 마우스 캡처
*마우스 캡처*는 컨트롤이 모든 마우스 입력 명령을 받는 시점을 나타냅니다.  컨트롤이 마우스를 캡처하면 포인터가 테두리 안에 있는지 여부에 관계없이 마우스 입력을 받습니다.  
  
## 마우스 캡처 설정  
 Windows Forms에서는 사용자가 컨트롤에서 마우스 단추를 누르면 컨트롤이 마우스를 캡처하고, 사용자가 마우스 단추를 놓으면 컨트롤이 마우스를 해제합니다.  
  
 <xref:System.Windows.Forms.Control> 클래스의 <xref:System.Windows.Forms.Control.Capture%2A> 속성은 컨트롤이 마우스를 캡처했는지 여부를 지정합니다.  컨트롤에서 마우스 캡처를 잃는 시점을 결정하려면 <xref:System.Windows.Forms.Control.MouseCaptureChanged> 이벤트를 처리합니다.  
  
 전경 창에서만 마우스를 캡처할 수 있습니다.  배경 창에서 마우스를 캡처하려고 하면 마우스 포인터가 창의 보이는 부분 안에 있을 때 발생하는 마우스 이벤트에 대한 메시지만 받습니다.  또한 전경 창에서 마우스를 캡처한 경우에도 사용자는 다른 창을 클릭하여 전경 창으로 만들 수 있습니다.  마우스가 캡처되면 바로 가기 키가 작동하지 않습니다.  
  
## 참고 항목  
 [Windows Forms 응용 프로그램의 마우스 입력](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)