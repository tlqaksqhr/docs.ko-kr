---
title: "방법: Windows Forms 응용 프로그램에서 HTML 문서 뷰어 만들기 | Microsoft Docs"
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
  - "문서 뷰어"
  - "WebBrowser 컨트롤[Windows Forms], HTML 문서 뷰어 만들기"
  - "Windows Forms, 문서 뷰어 만들기"
ms.assetid: 6a6338fe-f7ee-4f5e-9d8f-0465c57e9039
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: Windows Forms 응용 프로그램에서 HTML 문서 뷰어 만들기
<xref:System.Windows.Forms.WebBrowser> 컨트롤을 사용하면 인터넷 웹 브라우저의 모든 기능을 제공하지 않고 HTML 문서를 표시하고 인쇄할 수 있습니다.  이는 HTML의 형식 지정 기능을 활용하려고 하지만 사용자가 신뢰되지 않은 웹 컨트롤이나 악의적인 스크립트 코드가 포함되어 있을 수도 있는 임의의 웹 페이지를 로드하는 것을 원하지 않는 경우에 유용합니다.  예를 들어, <xref:System.Windows.Forms.WebBrowser> 컨트롤을 HTML 전자 메일 뷰어로 사용하거나 응용 프로그램에서 HTML 형식의 도움말을 제공하는 데 사용하려면 다음과 같은 방식으로 이 컨트롤의 기능을 제한할 수 있습니다.  
  
### HTML 문서 뷰어를 만들려면  
  
1.  <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> 속성을 `false`로 설정하여 <xref:System.Windows.Forms.WebBrowser> 컨트롤에 끌어 놓은 메뉴가 열리지 않도록 합니다.  
  
     [!code-csharp[WebBrowserMisc#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#20)]
     [!code-vb[WebBrowserMisc#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#20)]  
  
2.  <xref:System.Windows.Forms.WebBrowser.Url%2A> 속성을 표시할 초기 파일의 위치로 설정합니다.  
  
     [!code-csharp[WebBrowserMisc#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#21)]
     [!code-vb[WebBrowserMisc#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#21)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   `webBrowser1`이라는 <xref:System.Windows.Forms.WebBrowser> 컨트롤  
  
-   `System` 및 `System.Windows.Forms` 어셈블리에 대한 참조  
  
## 참고 항목  
 <xref:System.Windows.Forms.WebBrowser>   
 <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>   
 <xref:System.Windows.Forms.WebBrowser.Url%2A>   
 [WebBrowser 컨트롤 개요](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)   
 [WebBrowser 보안](../../../../docs/framework/winforms/controls/webbrowser-security.md)   
 [방법: WebBrowser 컨트롤을 사용하여 URL 탐색](../../../../docs/framework/winforms/controls/how-to-navigate-to-a-url-with-the-webbrowser-control.md)   
 [방법: WebBrowser 컨트롤을 사용하여 인쇄](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)