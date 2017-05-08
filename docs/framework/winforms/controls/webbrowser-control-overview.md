---
title: "WebBrowser 컨트롤 개요 | Microsoft Docs"
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
  - "WebBrowser"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "웹 페이지, 응용 프로그램에서 표시"
  - "WebBrowser 컨트롤[Windows Forms], 정보"
ms.assetid: 6e3e1cc2-9c48-4136-9659-e99e4e60b7e9
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# WebBrowser 컨트롤 개요
<xref:System.Windows.Forms.WebBrowser> 컨트롤은 WebBrowser ActiveX 컨트롤에 대한 관리되는 래퍼를 제공합니다.  관리되는 래퍼를 사용하면 Windows Forms 클라이언트 응용 프로그램에 웹 페이지를 표시할 수 있습니다.  <xref:System.Windows.Forms.WebBrowser> 컨트롤을 사용하면 응용 프로그램에서 Internet Explorer 웹 검색 기능을 복제하거나 기본 Internet Explorer 기능을 해제한 다음 해당 컨트롤을 단순한 HTML 문서 뷰어로 사용할 수 있습니다.  또한 이 컨트롤을 사용하여 DHTML 기반 사용자 인터페이스 요소를 폼에 추가하고 이 요소가 <xref:System.Windows.Forms.WebBrowser> 컨트롤에 호스팅된 사실을 숨길 수 있습니다.  이러한 방식으로 단일 응용 프로그램에서 웹 컨트롤과 Windows Forms 컨트롤을 완전하게 결합할 수 있습니다.  
  
## 자주 사용되는 속성, 메서드 및 이벤트  
 또한 <xref:System.Windows.Forms.WebBrowser> 컨트롤에는 Internet Explorer에 있는 컨트롤을 구현하는 데 사용할 수 있는 여러 속성, 메서드 및 이벤트가 포함되어 있습니다.  예를 들어, `Navigate` 메서드를 사용하여 주소 표시줄을 구현하고 `GoBack`, `GoForward`, `Stop` 및 `Refresh` 메서드를 사용하여 도구 모음에 탐색 단추를 구현할 수 있습니다.  `Navigated` 이벤트를 처리하여 주소 표시줄을 `Url` 속성 값으로 업데이트하고 제목 표시줄을 `DocumentTitle` 속성 값으로 업데이트할 수 있습니다.  
  
 응용 프로그램 내에 사용자 고유의 페이지 내용을 생성하려면 `DocumentText` 속성을 설정합니다.  HTML DOM\(문서 개체 모델\)에 친숙한 경우에는 `Document` 속성을 통해 현재 웹 페이지의 내용을 조작할 수도 있습니다.  이 속성을 사용하면 파일을 탐색하는 대신 메모리에 문서를 저장하거나 수정할 수 있습니다.  
  
 또한 `Document` 속성을 사용하면 클라이언트 응용 프로그램 코드에서 웹 페이지 스크립팅 코드에 구현된 메서드를 호출할 수 있습니다.  스크립팅 코드에서 클라이언트 응용 프로그램 코드에 액세스하려면 `ObjectForScripting` 속성을 설정합니다.  지정하는 개체는 스크립트 코드에서 `window.external` 개체로 액세스할 수 있습니다.  
  
|Name|설명|  
|----------|--------|  
|<xref:System.Windows.Forms.WebBrowser.Document%2A> 속성|현재 웹 페이지의 HTML DOM\(문서 개체 모델\)에 대한 관리되는 액세스를 제공하는 개체를 가져옵니다.|  
|<xref:System.Windows.Forms.WebBrowser.DocumentCompleted> 이벤트|웹 페이지 로드가 완료되면 발생합니다.|  
|<xref:System.Windows.Forms.WebBrowser.DocumentText%2A> 속성|현재 웹 페이지의 HTML 콘텐츠를 가져오거나 설정합니다.|  
|<xref:System.Windows.Forms.WebBrowser.DocumentTitle%2A> 속성|현재 웹 페이지의 제목을 가져옵니다.|  
|<xref:System.Windows.Forms.WebBrowser.GoBack%2A> 메서드|기록의 이전 페이지를 탐색합니다.|  
|<xref:System.Windows.Forms.WebBrowser.GoForward%2A> 메서드|기록의 다음 페이지를 탐색합니다.|  
|<xref:System.Windows.Forms.WebBrowser.Navigate%2A> 메서드|지정한 URL을 탐색합니다.|  
|<xref:System.Windows.Forms.WebBrowser.Navigating> 이벤트|작업을 취소할 수 있도록 탐색이 시작되기 전에 발생합니다.|  
|<xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> 속성|웹 페이지 스크립팅 코드에서 응용 프로그램과 통신하는 데 사용할 수 있는 개체를 가져오거나 설정합니다.|  
|<xref:System.Windows.Forms.WebBrowser.Print%2A> 메서드|현재 웹 페이지를 인쇄합니다.|  
|<xref:System.Windows.Forms.WebBrowser.Refresh%2A> 메서드|현재 웹 페이지를 다시 로드합니다.|  
|<xref:System.Windows.Forms.WebBrowser.Stop%2A> 메서드|현재 탐색을 중단하고 소리와 애니메이션 등의 동적 페이지 요소를 중지합니다.|  
|<xref:System.Windows.Forms.WebBrowser.Url%2A> 속성|현재 웹 페이지의 URL을 가져오거나 설정합니다.  이 속성을 설정하면 컨트롤이 새 URL로 이동됩니다.|  
  
## 참고 항목  
 <xref:System.Windows.Forms.WebBrowser>   
 <xref:System.Windows.Forms.WebBrowserDocumentCompletedEventArgs>   
 <xref:System.Windows.Forms.WebBrowserDocumentCompletedEventHandler>   
 <xref:System.Windows.Forms.WebBrowserEncryptionLevel>   
 <xref:System.Windows.Forms.WebBrowserNavigatedEventArgs>   
 <xref:System.Windows.Forms.WebBrowserNavigatedEventHandler>   
 <xref:System.Windows.Forms.WebBrowserNavigatingEventArgs>   
 <xref:System.Windows.Forms.WebBrowserNavigatingEventHandler>   
 <xref:System.Windows.Forms.WebBrowserProgressChangedEventArgs>   
 <xref:System.Windows.Forms.WebBrowserReadyState>   
 <xref:System.Windows.Forms.WebBrowserRefreshOption>   
 [방법: WebBrowser 컨트롤을 사용하여 URL 탐색](../../../../docs/framework/winforms/controls/how-to-navigate-to-a-url-with-the-webbrowser-control.md)   
 [방법: WebBrowser 컨트롤을 사용하여 인쇄](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)   
 [방법: Windows Forms 응용 프로그램에 웹 브라우저 기능 추가](../../../../docs/framework/winforms/controls/how-to-add-web-browser-capabilities-to-a-windows-forms-application.md)   
 [방법: Windows Forms 응용 프로그램에서 HTML 문서 뷰어 만들기](../../../../docs/framework/winforms/controls/how-to-create-an-html-document-viewer-in-a-windows-forms-application.md)   
 [방법: DHTML 코드와 클라이언트 응용 프로그램 코드 간의 양방향 통신 구현](../../../../docs/framework/winforms/controls/implement-two-way-com-between-dhtml-and-client.md)   
 [WebBrowser 보안](../../../../docs/framework/winforms/controls/webbrowser-security.md)