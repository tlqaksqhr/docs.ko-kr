---
title: "WebBrowser 보안 | Microsoft Docs"
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
  - "보안[Windows Forms], WebBrowser 컨트롤"
  - "WebBrowser 컨트롤[Windows Forms], 보안"
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# WebBrowser 보안
<xref:System.Windows.Forms.WebBrowser> 컨트롤은 완전 신뢰 수준에서만 작동합니다.  컨트롤에 표시된 HTML 콘텐츠는 외부 웹 서버에서 가져올 수 있으며 스크립트나 웹 컨트롤 형식의 비관리 코드를 포함할 수 있습니다.  이러한 경우 <xref:System.Windows.Forms.WebBrowser> 컨트롤을 사용하면 Internet Explorer를 사용할 때와 같은 보안 수준이 유지되지만 관리되는 <xref:System.Windows.Forms.WebBrowser> 컨트롤로 이러한 비관리 코드가 실행되지 않도록 할 수는 없습니다.  
  
 기본 ActiveX `WebBrowser` 컨트롤과 관련된 보안 문제에 대한 자세한 내용은 [WebBrowser Control](http://go.microsoft.com/fwlink/?LinkId=198812)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Forms.WebBrowser>   
 [WebBrowser 컨트롤 개요](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)   
 [WebBrowser Control](http://go.microsoft.com/fwlink/?LinkId=198812)