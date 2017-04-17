---
title: "관리되는 HTML 문서 개체 모델의 프레임에 액세스 | Microsoft Docs"
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
  - "DOM, 관리되는 HTML의 프레임 액세스"
  - "프레임, 액세스"
  - "HTML DOM, 관리"
  - "HTML, DOM"
  - "HTML, 관리"
  - "관리되는 HTML DOM"
ms.assetid: cdeeaa22-0be4-4bbf-9a75-4ddc79199f8d
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 관리되는 HTML 문서 개체 모델의 프레임에 액세스
일부 HTML 문서는 *프레임*으로 구성되거나, 고유한 HTML 문서를 포함할 수 있는 창으로 구성됩니다.  프레임을 사용하면 탐색 모음과 같이 페이지 조각 하나 이상이 정적으로 유지되지만 다른 프레임의 콘텐츠가 지속적으로 바뀌는 HTML 페이지를 쉽게 만들 수 있습니다.  
  
 HTML 작성자는 다음 두 방법의 하나로 프레임을 만들 수 있습니다.  
  
-   고정된 창을 만드는 `FRAMESET` 및 `FRAME` 태그 사용.  
  
 또는  
  
-   런타임에 위치가 변경될 수 있는 부동 창을 만드는 `IFRAME` 태그 사용.  
  
1.  프레임은 HTML 문서를 포함하므로 DOM\(문서 개체 모델\)에서 창 요소 및 프레임 요소로 표현됩니다.  
  
2.  <xref:System.Windows.Forms.HtmlWindow>의 프레임 컬렉션을 사용하여 `FRAME` 또는 `IFRAME` 태그에 액세스하면 프레임에 해당하는 창 요소가 검색됩니다.  이는 현재 URL, 문서 및 크기와 같은 프레임의 모든 동적 속성을 나타냅니다.  
  
3.  <xref:System.Windows.Forms.HtmlElementCollection.GetElementsByName%2A> 또는 <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A>와 같은 메서드, <xref:System.Windows.Forms.HtmlElement.Children%2A> 컬렉션 또는 <xref:System.Windows.Forms.HtmlWindow>의 <xref:System.Windows.Forms.HtmlWindow.WindowFrameElement%2A> 속성을 사용하여 `FRAME` 또는 `IFRAME` 태그에 액세스하면 프레임 요소가 검색됩니다.  이는 원래 HTML 파일에 지정된 URL을 포함하는 프레임의 정적 속성을 나타냅니다.  
  
## 프레임 및 보안  
 관리되는 HTML DOM이 *프레임 간 스크립팅 보안*이라는 보안 조치를 구현한다는 사실 때문에 프레임에 대한 액세스가 복잡해집니다.  서로 다른 도메인에 `FRAME`이 두 개 이상 있는 `FRAMESET`이 문서에 포함되면 이들 `FRAME`이 서로 상호 작용할 수 없습니다.  즉, 웹 사이트의 콘텐츠를 표시하는 `FRAME`는  http:\/\/www.adatum.com\/과 같은 타사 사이트를 호스트하는 `FRAME`의 정보에 액세스할 수 없습니다.  이 보안은 <xref:System.Windows.Forms.HtmlWindow> 클래스 수준에서 구현됩니다.  해당 URL과 같은 또 다른 웹 사이트를 호스트하는 `FRAME`에 대한 일반적인 정보를 가져올 수 있지만, <xref:System.Windows.Forms.HtmlWindow.Document%2A>에 액세스하거나 호스트 `FRAME` 또는 `IFRAME`의 크기나 위치를 변경할 수 없습니다.  
  
 <xref:System.Windows.Forms.HtmlWindow.Open%2A> 및 <xref:System.Windows.Forms.HtmlWindow.OpenNew%2A> 메서드를 사용하여 연 창에도 이 규칙이 적용됩니다.  <xref:System.Windows.Forms.WebBrowser> 컨트롤에 호스트된 페이지와 다른 도메인에 있는 창을 열면 해당 창을 이동하거나 콘텐츠를 검사할 수 없습니다.  <xref:System.Windows.Forms.WebBrowser> 컨트롤을 통해 Windows Forms 기반 응용 프로그램을 배포하는 데 사용된 웹 사이트를 표시하는 경우에도 이들 제한 사항이 적용됩니다.  [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] 배포 기술을 사용하여 웹 사이트 A에서 응용 프로그램을 설치하고 <xref:System.Windows.Forms.WebBrowser>를 사용하여 웹 사이트 B를 표시하면 웹 사이트 B의 데이터에 액세스할 수 없습니다.  
  
 사이트 간 스크립팅에 대한 자세한 내용은 [프레임 간 스크립팅 및 보안\(영문\)](http://msdn.microsoft.com/library/ms533028.aspx)을 참조하세요.  
  
## 참고 항목  
 [FRAME 요소 &#124; frame 개체\(영문\)](http://msdn.microsoft.com/library/ms535250.aspx)   
 [관리되는 HTML 문서 개체 모델 사용](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)