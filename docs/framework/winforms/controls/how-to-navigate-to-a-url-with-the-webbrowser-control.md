---
title: "방법: WebBrowser 컨트롤을 사용하여 URL 탐색 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "WebBrowser.Navigate"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "예제[Windows Forms], WebBrowser 컨트롤"
  - "URL, 탐색"
  - "WebBrowser 컨트롤[Windows Forms], 예제"
  - "WebBrowser 컨트롤[Windows Forms], URL 탐색"
ms.assetid: b3ec38cb-f509-4d0b-bd79-9f3611259c62
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: WebBrowser 컨트롤을 사용하여 URL 탐색
다음 코드 예제에서는 특정 URL에 대한 <xref:System.Windows.Forms.WebBrowser> 컨트롤을 탐색하는 방법을 보여 줍니다.  
  
 새 문서가 완전하게 로드되는 시점을 확인하려면 <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> 이벤트를 처리합니다.  이 이벤트에 대한 예제는 [방법: WebBrowser 컨트롤을 사용하여 인쇄](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)를 참조하십시오.  
  
## 예제  
  
```vb  
Me.webBrowser1.Navigate("http://www.microsoft.com")  
```  
  
```csharp  
this.webBrowser1.Navigate("http://www.microsoft.com");  
```  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   `webBrowser1`이라는 <xref:System.Windows.Forms.WebBrowser> 컨트롤  
  
-   `System` 및 `System.Windows.Forms` 어셈블리에 대한 참조  
  
## 참고 항목  
 <xref:System.Windows.Forms.WebBrowser>   
 <xref:System.Windows.Forms.WebBrowser.DocumentCompleted?displayProperty=fullName>   
 <xref:System.Windows.Forms.WebBrowser.Navigating?displayProperty=fullName>   
 <xref:System.Windows.Forms.WebBrowser.Navigated?displayProperty=fullName>   
 [WebBrowser 컨트롤](../../../../docs/framework/winforms/controls/webbrowser-control-windows-forms.md)   
 [방법: WebBrowser 컨트롤을 사용하여 인쇄](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)