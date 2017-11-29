---
title: "방법: 관리되는 HTML 문서 개체 모델의 HTML 소스에 액세스"
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
- managed HTML DOM
- HTML [Windows Forms], accessing in Windows Forms
ms.assetid: 53db79fa-8a5e-448e-88c2-f54ace3860b6
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7ef9839029e1c60cbc0d713e8982baa5708a281f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-the-html-source-in-the-managed-html-document-object-model"></a>방법: 관리되는 HTML 문서 개체 모델의 HTML 소스에 액세스
<xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> 컨트롤의 <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> 및 <xref:System.Windows.Forms.WebBrowser> 속성은 현재 문서의 HTML을 처음 표시되었을 때의 상태로 반환합니다. 그러나 <xref:System.Windows.Forms.HtmlElement.AppendChild%2A> 및 <xref:System.Windows.Forms.HtmlElement.InnerHtml%2A>과 같은 메서드 및 속성 호출을 사용하여 페이지를 수정하는 경우 <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> 및 <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>를 호출해도 해당 변경 내용이 표시되지 않습니다. DOM의 최신 HTML 소스를 가져오려면 HTML 요소에 대해 <xref:System.Windows.Forms.HtmlElement.OuterHtml%2A> 속성을 호출해야 합니다.  
  
 다음 절차에서는 동적 소스를 검색하여 별도의 바로 가기 메뉴에 표시하는 방법을 보여줍니다.  
  
### <a name="retrieving-the-dynamic-source-with-the-outerhtml-property"></a>OuterHtml 속성을 사용하여 동적 소스 검색  
  
1.  새 Windows Forms 응용 프로그램을 만듭니다. 단일 시작 <xref:System.Windows.Forms.Form>, 해당 버전을 호출 `Form1`합니다.  
  
2.  호스트는 <xref:System.Windows.Forms.WebBrowser> Windows Forms 응용 프로그램에서 제어 하 고 이름을 `WebBrowser1`합니다. 자세한 내용은 참조 [하는 방법: Windows Forms 응용 프로그램 웹 브라우저 기능 추가](../../../../docs/framework/winforms/controls/how-to-add-web-browser-capabilities-to-a-windows-forms-application.md)합니다.  
  
3.  두 번째 만들기 <xref:System.Windows.Forms.Form> 이라는 응용 프로그램에서는 `CodeForm`합니다.  
  
4.  추가 <xref:System.Windows.Forms.RichTextBox> 컨트롤을 `CodeForm` 설정 하 고 해당 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 `Fill`합니다.  
  
5.  공용 속성을 만들지 `CodeForm` 호출 `Code`합니다.  
  
     [!code-csharp[DisplayWebBrowserCode#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/CodeForm.cs#1)]
     [!code-vb[DisplayWebBrowserCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/CodeForm.vb#1)]  
  
6.  추가 <xref:System.Windows.Forms.Button> 라는 컨트롤 `Button1` 에 프로그램 <xref:System.Windows.Forms.Form>, 모니터링는 <xref:System.Windows.Forms.Control.Click> 이벤트입니다. 이벤트를 모니터링에 대 한 자세한 내용은 참조 하십시오. [이벤트](../../../../docs/standard/events/index.md)합니다.  
  
7.  다음 코드를 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기에 추가합니다.  
  
     [!code-csharp[DisplayWebBrowserCode#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/Form1.cs#2)]
     [!code-vb[DisplayWebBrowserCode#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/Form1.vb#2)]  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 검색을 시도하기 전에 항상 <xref:System.Windows.Forms.WebBrowser.Document%2A>의 값을 테스트해야 합니다. 현재 페이지의 로드가 완료되지 않으면 <xref:System.Windows.Forms.WebBrowser.Document%2A> 또는 하나 이상의 해당 자식 개체가 초기화되지 않을 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [관리되는 HTML 문서 개체 모델 사용](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)  
 [WebBrowser 컨트롤 개요](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)
