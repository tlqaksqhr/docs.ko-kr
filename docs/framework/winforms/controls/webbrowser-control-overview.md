---
title: "WebBrowser 컨트롤 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- WebBrowser
helpviewer_keywords:
- WebBrowser control [Windows Forms], about
- Web pages [Windows Forms], displaying in applications
ms.assetid: 6e3e1cc2-9c48-4136-9659-e99e4e60b7e9
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d2c1ed93769cc91d9622a86ea2d894cea57f5bcd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="webbrowser-control-overview"></a>WebBrowser 컨트롤 개요
<xref:System.Windows.Forms.WebBrowser> 컨트롤은 WebBrowser ActiveX 컨트롤에 대 한 관리 되는 래퍼를 제공 합니다. 관리 되는 래퍼를 사용 하면 Windows Forms 클라이언트 응용 프로그램에서 웹 페이지를 표시할 수 있습니다. 사용할 수는 <xref:System.Windows.Forms.WebBrowser> Internet Explorer 웹 응용 프로그램에 검색 기능을 복제 하는 컨트롤 기본 Internet Explorer 기능을 사용 하지 않도록 설정 하 고 간단한 HTML 문서 뷰어 컨트롤을 사용할 수 있습니다. DHTML 기반 사용자 인터페이스 요소를 폼에 추가 하 고 숨길에서 호스트 되는 팩트에 컨트롤을 사용할 수도 있습니다는 <xref:System.Windows.Forms.WebBrowser> 제어 합니다. 이 방법을 사용 하면 단일 응용 프로그램에서 Windows Forms 컨트롤을 사용 하 여 웹 컨트롤을 원활 하 게 결합 수 있습니다.  
  
## <a name="frequently-used-properties-methods-and-events"></a>자주 사용 되는 속성, 메서드 및 이벤트  
 <xref:System.Windows.Forms.WebBrowser> 컨트롤에 여러 속성, 메서드 및 Internet Explorer에 있는 컨트롤을 구현 하는 데 사용할 수 있는 이벤트입니다. 예를 들어 사용할 수 있습니다는 `Navigate` 주소 표시줄을 구현 하는 메서드 및 `GoBack`, `GoForward`, `Stop`, 및 `Refresh` 도구 모음에 탐색 단추를 구현 하는 방법입니다. 처리할 수 있습니다는 `Navigated` 주소 표시줄의 값으로 업데이트 하는 이벤트는 `Url` 속성 및 값이 있는 제목 표시줄의 `DocumentTitle` 속성입니다.  
  
 응용 프로그램 내에서 고유한 페이지 콘텐츠를 생성 하려는 경우 설정할 수 있습니다는 `DocumentText` 속성입니다. HTML 문서 개체 모델 (DOM)에 잘 알고 있다면 통해 현재 웹 페이지의 내용을 조작할 수도 있습니다는 `Document` 속성입니다. 이 속성을 저장 하 고 파일을 탐색 하는 대신 메모리에 문서를 수정할 수 있습니다.  
  
 `Document` 속성 또한 웹 페이지 스크립팅 코드에서 클라이언트 응용 프로그램 코드에서에서 구현 되는 메서드를 호출할 수 있습니다. 설정 스크립팅 코드에서 클라이언트 응용 프로그램 코드에 액세스 하려면는 `ObjectForScripting` 속성입니다. 스크립트 코드에서 지정 하는 개체를 액세스할 수 있습니다는 `window.external` 개체입니다.  
  
|name|설명|  
|----------|-----------------|  
|<xref:System.Windows.Forms.WebBrowser.Document%2A> 속성|현재 웹 페이지의 HTML 문서 개체 모델 (DOM)에 대 한 관리 되는 액세스를 제공 하는 개체를 가져옵니다.|  
|<xref:System.Windows.Forms.WebBrowser.DocumentCompleted>이벤트|웹 페이지 로드가 완료 되 면 발생 합니다.|  
|<xref:System.Windows.Forms.WebBrowser.DocumentText%2A> 속성|현재 웹 페이지의 콘텐츠는 HTML 가져오거나 설정 합니다.|  
|<xref:System.Windows.Forms.WebBrowser.DocumentTitle%2A> 속성|현재 웹 페이지의 제목을 가져옵니다.|  
|<xref:System.Windows.Forms.WebBrowser.GoBack%2A> 메서드|기록의 이전 페이지를 탐색합니다.|  
|<xref:System.Windows.Forms.WebBrowser.GoForward%2A> 메서드|기록의 다음 페이지로 이동합니다.|  
|<xref:System.Windows.Forms.WebBrowser.Navigate%2A> 메서드|지정된 된 URL로 이동합니다.|  
|<xref:System.Windows.Forms.WebBrowser.Navigating>이벤트|작업을 취소할 수 있도록 탐색이 시작 되기 전에 발생 합니다.|  
|<xref:System.Windows.Forms.WebBrowser.ObjectForScripting%2A> 속성|웹 페이지 스크립팅 코드에서 응용 프로그램과 통신 하는 데 사용할 수 있는 개체를 가져오거나 설정 합니다.|  
|<xref:System.Windows.Forms.WebBrowser.Print%2A> 메서드|현재 웹 페이지를 인쇄합니다.|  
|<xref:System.Windows.Forms.WebBrowser.Refresh%2A> 메서드|현재 웹 페이지를 다시 로드합니다.|  
|<xref:System.Windows.Forms.WebBrowser.Stop%2A> 메서드|현재 탐색 하 고 소리 및 애니메이션과 같은 동적 페이지 요소를 중지 합니다.|  
|<xref:System.Windows.Forms.WebBrowser.Url%2A> 속성|현재 웹 페이지의 URL을 가져오거나 설정 합니다. 컨트롤에 새 URL 탐색이 속성을 설정 합니다.|  
  
## <a name="see-also"></a>참고 항목  
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
