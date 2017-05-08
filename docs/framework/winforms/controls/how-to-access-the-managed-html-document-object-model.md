---
title: "방법: 관리되는 HTML 문서 개체 모델에 액세스 | Microsoft Docs"
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
  - "HTML DOM에 액세스"
  - "관리 HTML DOM에 액세스"
ms.assetid: 40fa5cd5-1ed8-42f6-a93f-9ac01608bbeb
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: 관리되는 HTML 문서 개체 모델에 액세스
다음과 같은 두 가지 유형의 응용 프로그램에서 관리되는 HTML DOM(문서 개체 모델)에 액세스할 수 있습니다.  
  
-   관리 되는 호스트 하는 Windows Forms 응용 프로그램 (.exe) <xref:System.Windows.Forms.WebBrowser> 제어 합니다. 이러한 두 기술을 서로를 보완는 <xref:System.Windows.Forms.WebBrowser> 컨트롤 사용자는 문서의 논리 구조를 나타내는 HTML DOM에 페이지를 표시 합니다.  
  
-   Windows Forms <xref:System.Windows.Forms.UserControl> Internet Explorer 내에서 호스팅됩니다. 페이지를 나타내는 HTML DOM에 액세스할 수 여 <xref:System.Windows.Forms.UserControl> 문서의 구조를 변경 하거나 다른 많은 가능성 중 모달 대화 상자에 호스팅됩니다.  
  
### <a name="to-access-dom-from-a-windows-forms-application"></a>Windows Forms 응용 프로그램에서 DOM에 액세스하려면  
  
1.  호스트는 <xref:System.Windows.Forms.WebBrowser> Windows Forms 응용 프로그램 내에서 제어 하 고에 대 한 모니터링은 <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> 이벤트입니다. 컨트롤 호스팅 및 이벤트에 대 한 모니터링 정보를 참조 하십시오. [이벤트](../../../../docs/standard/events/index.md)합니다.  
  
2.  검색는 <xref:System.Windows.Forms.HtmlDocument> 에 액세스 하 여 현재 페이지에 대 한는 <xref:System.Windows.Forms.WebBrowser.Document%2A> 의 속성은 <xref:System.Windows.Forms.WebBrowser> 제어 합니다.  
  
<!-- TODO: review snippet reference  [!CODE [AccessHTMLDOMApp#1](AccessHTMLDOMApp#1)]  -->  
  
### <a name="to-access-dom-from-a-usercontrol-hosted-in-internet-explorer"></a>Internet Explorer에서 호스팅되는 UserControl에서 DOM에 액세스하려면  
  
1.  고유한 사용자 지정 파생된 클래스를 만들기는 <xref:System.Windows.Forms.UserControl> 클래스입니다. 자세한 내용은 참조 [하는 방법: 복합 컨트롤 작성자](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)합니다.  
  
2.  에 대 한 로드 이벤트 처리기 내에 다음 코드를 배치 하면 <xref:System.Windows.Forms.UserControl>:  
  
 [!code-csharp[AccessHTMLDOMControl#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/AccessHTMLDOMControl/cs/UserControl1.cs#1)]
 [!code-vb[AccessHTMLDOMControl#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/AccessHTMLDOMControl/vb/UserControl1.vb#1)]  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
  
1.  통해 DOM을 사용 하는 경우는 <xref:System.Windows.Forms.WebBrowser> 제어 하면 항상까지 기다려야는 <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> 이벤트에 액세스 하기 전에 발생는 <xref:System.Windows.Forms.WebBrowser.Document%2A> 속성의는 <xref:System.Windows.Forms.WebBrowser> 제어 합니다. <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> 이벤트는 전체 문서가 로드 된 후 발생 하 고 응용 프로그램에서 런타임 예외가 발생할 위험이 그 전에 DOM을 사용 합니다.  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
  
1.  응용 프로그램 또는 <xref:System.Windows.Forms.UserControl> 관리 되는 HTML DOM에 액세스 하려면 완전 신뢰가 필요 합니다 사용 하 여 Windows Forms 응용 프로그램을 배포 하는 경우 [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)], 권한 상승 또는 신뢰할 수 있는 응용 프로그램 배포를 사용 하 여 완전 신뢰를 요청할 수 있습니다; 참조 [ClickOnce 응용 프로그램 보안](../Topic/Securing%20ClickOnce%20Applications.md) 대 한 자세한 내용은 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [관리 되는 HTML 문서 개체 모델을 사용 하 여](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)