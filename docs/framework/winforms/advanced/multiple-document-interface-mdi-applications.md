---
title: "MDI 응용 프로그램 | Microsoft Docs"
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
  - "폼, MDI"
  - "MDI"
  - "Windows Forms, MDI 응용 프로그램"
  - "windows, MDI"
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# MDI 응용 프로그램
MDI\(다중 문서 인터페이스\) 응용 프로그램을 사용하면 자체 창을 가진 여러 문서를 동시에 표시할 수 있습니다.  MDI 응용 프로그램에는 창에서 창으로 또는 문서에서 문서로 전환할 수 있는 하위 메뉴가 포함된 창 메뉴 항목이 있는 경우가 많습니다.  
  
> [!NOTE]
>  Windows Forms의 SDI\(단일 문서 인터페이스\) 창 및 MDI 폼의 동작 사이에는 몇 가지 차이점이 있습니다.  `Opacity` 속성은 MDI 자식 폼의 모양에 영향을 주지 않으며  <xref:System.Windows.Forms.Form.CenterToParent%2A> 메서드도 MDI 자식 폼의 동작에 영향을 주지 않습니다.  
  
## 단원 내용  
 [방법: MDI 상위 폼 만들기](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 MDI 응용 프로그램에서 다중 문서의 컨테이너를 만드는 방법에 대해 설명합니다.  
  
 [방법: MDI 자식 폼 만들기](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 MDI 부모 폼에서 실행되는 하나 이상의 창을 만드는 방법에 대해 설명합니다.  
  
 [방법: 활성 MDI 자식 확인](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)  
 포커스를 가진 자식 창을 확인하고 이 창의 내용을 클립보드로 보내는 방법에 대해 설명합니다.  
  
 [방법: 활성 MDI 자식으로 데이터 전송](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)  
 활성 자식 창으로 정보를 전송하는 방법에 대해 설명합니다.  
  
 [방법: MDI 자식 폼 정렬](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)  
 MDI 응용 프로그램의 자식 창을 정렬하거나 바둑판식 또는 계단식으로 배열하는 방법에 대해 설명합니다.