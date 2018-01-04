---
title: "관리되는 HTML 문서 개체 모델의 노출되지 않은 멤버에 액세스"
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
- unexposed members
- managed HTML DOM [Windows Forms], accessing unexposed members
ms.assetid: 762295bd-2355-4aa7-b43c-5bff997a33e6
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 97a795930eb6965bd0ed15254969a72f45700306
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="accessing-unexposed-members-on-the-managed-html-document-object-model"></a>관리되는 HTML 문서 개체 모델의 노출되지 않은 멤버에 액세스
라는 클래스를 포함 하는 관리 되는 HTML 문서 개체 모델 (DOM) <xref:System.Windows.Forms.HtmlElement> 속성, 메서드 및 모든 HTML 요소에 공통 된 이벤트를 노출 합니다. 그러나 경우에 따라 해야 합니다 직접 관리 되는 인터페이스를 노출 하지 않는 멤버에 액세스 합니다. 이 항목을 포함 하는 노출 되지 않은 멤버에 액세스 하기 위한 두 가지 방법으로 검사 [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] 및 웹 페이지 내에서 정의 된 VBScript 함수입니다.  
  
## <a name="accessing-unexposed-members-through-managed-interfaces"></a>관리 되는 인터페이스를 통해 노출 되지 않은 멤버 액세스  
 <xref:System.Windows.Forms.HtmlDocument>및 <xref:System.Windows.Forms.HtmlElement> 노출 되지 않은 멤버에 대 한 액세스를 사용할 수 있는 네 가지 메서드를 제공 합니다. 다음 표에서 형식 및 해당 메서드를 보여 줍니다.  
  
|멤버 형식|메서드|  
|-----------------|-----------------|  
|속성 (<xref:System.Windows.Forms.HtmlElement>)|<xref:System.Windows.Forms.HtmlElement.GetAttribute%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.SetAttribute%2A>|  
|메서드|<xref:System.Windows.Forms.HtmlElement.InvokeMember%2A>|  
|이벤트 (<xref:System.Windows.Forms.HtmlDocument>)|<xref:System.Windows.Forms.HtmlDocument.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlDocument.DetachEventHandler%2A>|  
|이벤트 (<xref:System.Windows.Forms.HtmlElement>)|<xref:System.Windows.Forms.HtmlElement.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.DetachEventHandler%2A>|  
|이벤트 (<xref:System.Windows.Forms.HtmlWindow>)|<xref:System.Windows.Forms.HtmlWindow.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlWindow.DetachEventHandler%2A>|  
  
 이러한 메서드를 사용 하는 경우 올바른 기본 형식의 요소가 있다고 가정 합니다. 수신 대기 하려고 한다고 가정할 경우는 `Submit` 의 이벤트는 `FORM` 요소에는 HTML 페이지에 몇 가지 전처리 작업을 수행할 수 있도록는 `FORM`의 사용자가 서버에 제출 하기 전에 값입니다. 이상적으로 HTML에 대 한 제어를 사용 하는 경우 정의 하는 `FORM` 는 고유 해야 `ID` 특성입니다.  
  
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
  
 이 페이지를 로드 한 후에 <xref:System.Windows.Forms.WebBrowser> 컨트롤, 있습니다 사용할 수 있습니다는 <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> 를 검색할 메서드는 `FORM` 사용 하 여 런타임에 `form1` 인수로 합니다.  
  
 [!code-csharp[System.Windows.Forms.HtmlElement#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/CS/Form1.cs#10)]
 [!code-vb[System.Windows.Forms.HtmlElement#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/VB/Form1.vb#10)]  
  
## <a name="accessing-unmanaged-interfaces"></a>관리 되지 않는 인터페이스에 액세스  
 또한 각 DOM 클래스에 의해 노출 되는 관리 되지 않는 구성 요소 개체 모델 (COM) 인터페이스를 사용 하 여 관리 되는 HTML DOM에 노출 되지 않은 멤버를 액세스할 수 있습니다. 노출 되지 않은 멤버는 관리 되는 HTML DOM으로 래핑되지 다른 관리 되지 않는 인터페이스를 반환 하는 경우 또는 노출 되지 않은 멤버에 대 한 여러 호출을 수행 해야 할 경우이 좋습니다.  
  
 다음 표에서 모든 관리 되는 HTML DOM을 통해 제공 되는 관리 되지 않는 인터페이스 표시 각 링크에 대 한 설명은 해당 사용법 및 예를 들어 코드에서 클릭 합니다.  
  
|형식|관리 되지 않는 인터페이스|  
|----------|-------------------------|  
|<xref:System.Windows.Forms.HtmlDocument>|<xref:System.Windows.Forms.HtmlDocument.DomDocument%2A>|  
|<xref:System.Windows.Forms.HtmlElement>|<xref:System.Windows.Forms.HtmlElement.DomElement%2A>|  
|<xref:System.Windows.Forms.HtmlWindow>|<xref:System.Windows.Forms.HtmlWindow.DomWindow%2A>|  
|<xref:System.Windows.Forms.HtmlHistory>|<xref:System.Windows.Forms.HtmlHistory.DomHistory%2A>|  
  
 COM 인터페이스를 사용 하는 가장 쉬운 방법은 지원 되는 것은 아니지만 응용 프로그램에서 관리 되지 않는 HTML DOM 라이브러리 (MSHTML.dll)에 대 한 참조를 추가 하입니다. 자세한 내용은 참조 [기술 자료 문서 934368](http://support.microsoft.com/kb/934368)합니다.  
  
## <a name="accessing-script-functions"></a>스크립트 함수에 액세스  
 HTML 페이지와 같은 스크립트 언어를 사용 하 여 하나 이상의 함수를 정의할 수 [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] 또는 VBScript입니다. 이러한 함수 내부에 배치 되며는 `SCRIPT` 페이지에서 페이지 및 DOM에서 요청 시 또는 이벤트에 대 한 응답으로 실행 수  
  
 사용 하 여 HTML 페이지에 정의 되는 스크립트 함수를 호출할 수는 <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> 메서드. 스크립트 메서드는 HTML 요소를 반환 하면이 반환 결과 변환 하는 캐스트를 사용할 수 있습니다는 <xref:System.Windows.Forms.HtmlElement>합니다. 자세한 내용 및 예제 코드 참조 <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>합니다.  
  
## <a name="see-also"></a>참고 항목  
 [관리되는 HTML 문서 개체 모델 사용](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)
