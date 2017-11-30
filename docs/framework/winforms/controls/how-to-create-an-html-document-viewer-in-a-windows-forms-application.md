---
title: "방법: Windows Forms 응용 프로그램에서 HTML 문서 뷰어 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebBrowser control [Windows Forms], creating an HTML document viewer
- document viewers
- Windows Forms, creating document viewers
ms.assetid: 6a6338fe-f7ee-4f5e-9d8f-0465c57e9039
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e06fbfde68c0d02a94f8c7e4657e2907cd3fa7eb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-an-html-document-viewer-in-a-windows-forms-application"></a>방법: Windows Forms 응용 프로그램에서 HTML 문서 뷰어 만들기
사용할 수는 <xref:System.Windows.Forms.WebBrowser> 컨트롤 표시 하 고는 인터넷 웹 브라우저의 전체 기능을 제공 하지 않고 HTML 문서를 인쇄 합니다. Html 서식 지정 기능을 활용 하려고 하지만 사용자가 신뢰할 수 없는 웹 컨트롤 또는 잠재적 악성 스크립트 코드를 포함할 수 있는 임의 웹 페이지를 로드 하지 않을 경우에 유용 합니다. 기능을 제한 하려는 경우는 <xref:System.Windows.Forms.WebBrowser> HTML 전자 메일 뷰어도 사용 하거나 응용 프로그램에서 HTML 형식의 도움말을 제공 하려면 예를 들어 이러한 방식으로 제어 합니다.  
  
### <a name="to-create-an-html-document-viewer"></a>HTML 문서 뷰어 만들기를  
  
1.  설정의 <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> 속성을 `false` 방지 하기 위해는 <xref:System.Windows.Forms.WebBrowser> 컨트롤이 놓여진 파일을 열 수 없도록 합니다.  
  
     [!code-csharp[WebBrowserMisc#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#20)]
     [!code-vb[WebBrowserMisc#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#20)]  
  
2.  설정의 <xref:System.Windows.Forms.WebBrowser.Url%2A> 속성을 표시할 초기 파일의 위치입니다.  
  
     [!code-csharp[WebBrowserMisc#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#21)]
     [!code-vb[WebBrowserMisc#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#21)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   `webBrowser1`이라는 <xref:System.Windows.Forms.WebBrowser> 컨트롤  
  
-   `System` 및 `System.Windows.Forms` 어셈블리에 대한 참조  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.WebBrowser>  
 <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>  
 <xref:System.Windows.Forms.WebBrowser.Url%2A>  
 [WebBrowser 컨트롤 개요](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)  
 [WebBrowser 보안](../../../../docs/framework/winforms/controls/webbrowser-security.md)  
 [방법: WebBrowser 컨트롤을 사용하여 URL 탐색](../../../../docs/framework/winforms/controls/how-to-navigate-to-a-url-with-the-webbrowser-control.md)  
 [방법: WebBrowser 컨트롤을 사용하여 인쇄](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)
