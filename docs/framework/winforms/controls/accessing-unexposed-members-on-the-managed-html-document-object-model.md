---
title: "관리되는 HTML 문서 개체 모델의 노출되지 않은 멤버에 액세스 | Microsoft Docs"
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
  - "관리되는 HTML DOM, 노출되지 않은 멤버 액세스"
  - "노출되지 않은 멤버"
ms.assetid: 762295bd-2355-4aa7-b43c-5bff997a33e6
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 관리되는 HTML 문서 개체 모델의 노출되지 않은 멤버에 액세스
관리되는 HTML DOM\(문서 개체 모델\)에는 모든 HTML 요소에 공통적으로 있는 속성, 메서드 및 이벤트를 노출하는 <xref:System.Windows.Forms.HtmlElement>라는 클래스가 있습니다.  그러나 관리되는 인터페이스에서 직접 노출하지 않는 멤버에 액세스해야 하는 경우도 있습니다.  이 항목에서는 웹 페이지 내부에서 정의되는 [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] 및 VBScript 함수를 비롯하여 노출되지 않은 멤버에 액세스할 수 있는 두 가지 방법을 설명합니다.  
  
## 관리되는 인터페이스를 통해 노출되지 않은 멤버에 액세스  
 <xref:System.Windows.Forms.HtmlDocument>와 <xref:System.Windows.Forms.HtmlElement>에서는 노출되지 않은 멤버에 액세스할 수 있는 네 가지 메서드를 제공합니다.  다음 표에서는 형식과 각 형식의 해당 메서드를 보여 줍니다.  
  
|멤버 형식|메서드|  
|-----------|---------|  
|속성\(<xref:System.Windows.Forms.HtmlElement>\)|<xref:System.Windows.Forms.HtmlElement.GetAttribute%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.SetAttribute%2A>|  
|메서드|<xref:System.Windows.Forms.HtmlElement.InvokeMember%2A>|  
|이벤트\(<xref:System.Windows.Forms.HtmlDocument>\)|<xref:System.Windows.Forms.HtmlDocument.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlDocument.DetachEventHandler%2A>|  
|이벤트\(<xref:System.Windows.Forms.HtmlElement>\)|<xref:System.Windows.Forms.HtmlElement.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.DetachEventHandler%2A>|  
|이벤트\(<xref:System.Windows.Forms.HtmlWindow>\)|<xref:System.Windows.Forms.HtmlWindow.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlWindow.DetachEventHandler%2A>|  
  
 여기서는 이러한 메서드를 사용할 때 올바른 내부 형식 요소가 있다고 가정합니다.  그리고 사용자가 서버에 보내기 전에 `FORM`의 값에 대해 몇 가지 전처리 작업을 할 수 있도록 HTML 페이지에서 `FORM` 요소의 `Submit` 이벤트를 수신 대기하려고 한다고 가정합니다.  HTML을 제어할 수 있으면 고유 `ID` 특성을 갖도록 `FORM`을 정의하는 것이 가장 좋습니다.  
  
```  
<HTML>  
  
    <HEAD>  
        <TITLE>Form Page</TITLE>  
    </HEAD>  
  
    <BODY>  
        <FORM ID="form1">  
             ... form fields defined here ...  
        </FORM>  
    </BODY>  
  
</HTML>  
```  
  
 이 페이지를 <xref:System.Windows.Forms.WebBrowser> 컨트롤에 로드하고 나면 런타임에 <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> 메서드에 `form1`을 인수로 사용하여 `FORM`을 검색할 수 있습니다.  
  
 [!code-csharp[System.Windows.Forms.HtmlElement#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/CS/Form1.cs#10)]
 [!code-vb[System.Windows.Forms.HtmlElement#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/VB/Form1.vb#10)]  
  
## 관리되지 않는 인터페이스 액세스  
 각 DOM 클래스에서 노출하는 관리되지 않는 COM\(구성 요소 개체 모델\) 인터페이스를 사용하여 관리되는 HTML DOM에서 노출되지 않은 멤버에 액세스할 수도 있습니다.  노출되지 않은 멤버를 여러 번 호출해야 하는 경우나 노출되지 않은 멤버가 관리되는 HTML DOM에서 래핑되지 않은 관리되지 않는 다른 인터페이스를 반환하는 경우 이 기능을 사용하면 좋습니다.  
  
 다음 표에서는 관리되는 HTML DOM을 통해 노출되는 관리되지 않는 인터페이스를 모두 보여 줍니다.  각 링크를 클릭하면 사용법과 예제 코드에 대한 설명이 표시됩니다.  
  
|형식|관리되지 않는 인터페이스|  
|--------|-------------------|  
|<xref:System.Windows.Forms.HtmlDocument>|<xref:System.Windows.Forms.HtmlDocument.DomDocument%2A>|  
|<xref:System.Windows.Forms.HtmlElement>|<xref:System.Windows.Forms.HtmlElement.DomElement%2A>|  
|<xref:System.Windows.Forms.HtmlWindow>|<xref:System.Windows.Forms.HtmlWindow.DomWindow%2A>|  
|<xref:System.Windows.Forms.HtmlHistory>|<xref:System.Windows.Forms.HtmlHistory.DomHistory%2A>|  
  
 지원 되는 것은 아니지만COM인터페이스를 사용 하는 가장 쉬운 방법은 참조를 관리 되지 않는HTMLDOM라이브러리\(MSHTML.dll\)를응용 프로그램에서 추가 하는 것입니다.  자세한 내용은 [기술 자료 문서 934368](http://support.microsoft.com/kb/934368).  
  
## 스크립트 함수 액세스  
 HTML 페이지에서는 [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)]나 VBScript와 같은 스크립트 언어를 사용하여 하나 이상의 함수를 정의할 수 있습니다.  이러한 함수는 페이지 내의 `SCRIPT` 페이지 내부에 배치되며 요청이 있을 때 또는 DOM의 이벤트에 대한 응답으로 실행될 수 있습니다.  
  
 <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> 메서드를 사용하면 HTML 페이지에 정의한 스크립트 함수를 호출할 수 있습니다.  스크립트 메서드에서 HTML 요소를 반환하면 캐스트를 사용하여 이 반환 결과를 <xref:System.Windows.Forms.HtmlElement>로 변환할 수 있습니다.  자세한 내용 및 예제 코드를 보려면 <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>를 참조하십시오.  
  
## 참고 항목  
 [관리되는 HTML 문서 개체 모델 사용](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)