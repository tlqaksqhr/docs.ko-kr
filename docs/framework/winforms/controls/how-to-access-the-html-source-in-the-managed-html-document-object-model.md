---
title: "방법: 관리되는 HTML 문서 개체 모델의 HTML 소스에 액세스 | Microsoft Docs"
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
  - "HTML, Windows Forms에서 액세스"
  - "관리되는 HTML DOM"
ms.assetid: 53db79fa-8a5e-448e-88c2-f54ace3860b6
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 관리되는 HTML 문서 개체 모델의 HTML 소스에 액세스
<xref:System.Windows.Forms.WebBrowser> 컨트롤의 <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> 및 <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> 속성은 현재 문서의 HTML을 처음 표시되었을 때의 상태로 반환합니다.  그러나 <xref:System.Windows.Forms.HtmlElement.AppendChild%2A> 및 <xref:System.Windows.Forms.HtmlElement.InnerHtml%2A>과 같은 메서드 및 속성 호출을 사용하여 페이지를 수정하는 경우 <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> 및 <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>를 호출해도 해당 변경 내용이 표시되지 않습니다.  DOM의 최신 HTML 소스를 가져오려면 HTML 요소에 대해 <xref:System.Windows.Forms.HtmlElement.OuterHtml%2A> 속성을 호출해야 합니다.  
  
 다음 절차에서는 동적 소스를 검색하여 별도의 바로 가기 메뉴에 표시하는 방법을 보여줍니다.  
  
### OuterHtml 속성을 사용하여 동적 소스 검색  
  
1.  새 Windows Forms 응용 프로그램을 만듭니다.  먼저 <xref:System.Windows.Forms.Form> 하나를 만들어 이름을 `Form1`로 지정합니다.  
  
2.  Windows Forms 응용 프로그램에서 <xref:System.Windows.Forms.WebBrowser> 컨트롤을 호스팅하고 이름을 `WebBrowser1`로 지정합니다.  자세한 내용은 [방법: Windows Forms 응용 프로그램에 웹 브라우저 기능 추가](../../../../docs/framework/winforms/controls/how-to-add-web-browser-capabilities-to-a-windows-forms-application.md)을 참조하십시오.  
  
3.  응용 프로그램에서 `CodeForm`이라는 두 번째 <xref:System.Windows.Forms.Form>을 만듭니다.  
  
4.  <xref:System.Windows.Forms.RichTextBox> 컨트롤을 `CodeForm`에 추가하고 해당 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 `Fill`로 설정합니다.  
  
5.  `CodeForm`에 대해 `Code`라는 공용 속성을 만듭니다.  
  
     [!code-csharp[DisplayWebBrowserCode#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/CodeForm.cs#1)]
     [!code-vb[DisplayWebBrowserCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/CodeForm.vb#1)]  
  
6.  `Button1`이라는 <xref:System.Windows.Forms.Button> 컨트롤을 <xref:System.Windows.Forms.Form>에 추가하고 <xref:System.Windows.Forms.Control.Click> 이벤트를 모니터링합니다.  이벤트 모니터링에 대한 자세한 내용은 [이벤트](../../../../docs/standard/events/index.md)을 참조하세요.  
  
7.  다음 코드를 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기에 추가합니다.  
  
     [!code-csharp[DisplayWebBrowserCode#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/Form1.cs#2)]
     [!code-vb[DisplayWebBrowserCode#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/Form1.vb#2)]  
  
## 강력한 프로그래밍  
 검색을 시도하기 전에 항상 <xref:System.Windows.Forms.WebBrowser.Document%2A>의 값을 테스트해야 합니다.  현재 페이지의 로드가 완료되지 않으면 <xref:System.Windows.Forms.WebBrowser.Document%2A> 또는 하나 이상의 해당 자식 개체가 초기화되지 않을 수 있습니다.  
  
## 참고 항목  
 [관리되는 HTML 문서 개체 모델 사용](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)   
 [WebBrowser 컨트롤 개요](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)