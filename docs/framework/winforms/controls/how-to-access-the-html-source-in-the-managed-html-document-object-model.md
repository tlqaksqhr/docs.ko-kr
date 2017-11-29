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
# <a name="how-to-access-the-html-source-in-the-managed-html-document-object-model"></a><span data-ttu-id="32ca4-102">방법: 관리되는 HTML 문서 개체 모델의 HTML 소스에 액세스</span><span class="sxs-lookup"><span data-stu-id="32ca4-102">How to: Access the HTML Source in the Managed HTML Document Object Model</span></span>
<span data-ttu-id="32ca4-103"><xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> 컨트롤의 <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> 및 <xref:System.Windows.Forms.WebBrowser> 속성은 현재 문서의 HTML을 처음 표시되었을 때의 상태로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="32ca4-103">The <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> and <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> properties on the <xref:System.Windows.Forms.WebBrowser> control return the HTML of the current document as it existed when it was first displayed.</span></span> <span data-ttu-id="32ca4-104">그러나 <xref:System.Windows.Forms.HtmlElement.AppendChild%2A> 및 <xref:System.Windows.Forms.HtmlElement.InnerHtml%2A>과 같은 메서드 및 속성 호출을 사용하여 페이지를 수정하는 경우 <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> 및 <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>를 호출해도 해당 변경 내용이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="32ca4-104">However, if you modify the page using method and property calls such as <xref:System.Windows.Forms.HtmlElement.AppendChild%2A> and <xref:System.Windows.Forms.HtmlElement.InnerHtml%2A>, these changes will not appear when you call <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> and <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>.</span></span> <span data-ttu-id="32ca4-105">DOM의 최신 HTML 소스를 가져오려면 HTML 요소에 대해 <xref:System.Windows.Forms.HtmlElement.OuterHtml%2A> 속성을 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32ca4-105">To obtain the most up-to-date HTML source for the DOM, you must call the <xref:System.Windows.Forms.HtmlElement.OuterHtml%2A> property on the HTML element.</span></span>  
  
 <span data-ttu-id="32ca4-106">다음 절차에서는 동적 소스를 검색하여 별도의 바로 가기 메뉴에 표시하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="32ca4-106">The following procedure shows how to retrieve the dynamic source and display it in a separate shortcut menu.</span></span>  
  
### <a name="retrieving-the-dynamic-source-with-the-outerhtml-property"></a><span data-ttu-id="32ca4-107">OuterHtml 속성을 사용하여 동적 소스 검색</span><span class="sxs-lookup"><span data-stu-id="32ca4-107">Retrieving the dynamic source with the OuterHtml property</span></span>  
  
1.  <span data-ttu-id="32ca4-108">새 Windows Forms 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="32ca4-108">Create a new Windows Forms application.</span></span> <span data-ttu-id="32ca4-109">단일 시작 <xref:System.Windows.Forms.Form>, 해당 버전을 호출 `Form1`합니다.</span><span class="sxs-lookup"><span data-stu-id="32ca4-109">Start with a single <xref:System.Windows.Forms.Form>, and call it `Form1`.</span></span>  
  
2.  <span data-ttu-id="32ca4-110">호스트는 <xref:System.Windows.Forms.WebBrowser> Windows Forms 응용 프로그램에서 제어 하 고 이름을 `WebBrowser1`합니다.</span><span class="sxs-lookup"><span data-stu-id="32ca4-110">Host the <xref:System.Windows.Forms.WebBrowser> control in your Windows Forms application, and name it `WebBrowser1`.</span></span> <span data-ttu-id="32ca4-111">자세한 내용은 참조 [하는 방법: Windows Forms 응용 프로그램 웹 브라우저 기능 추가](../../../../docs/framework/winforms/controls/how-to-add-web-browser-capabilities-to-a-windows-forms-application.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="32ca4-111">For more information, see [How to: Add Web Browser Capabilities to a Windows Forms Application](../../../../docs/framework/winforms/controls/how-to-add-web-browser-capabilities-to-a-windows-forms-application.md).</span></span>  
  
3.  <span data-ttu-id="32ca4-112">두 번째 만들기 <xref:System.Windows.Forms.Form> 이라는 응용 프로그램에서는 `CodeForm`합니다.</span><span class="sxs-lookup"><span data-stu-id="32ca4-112">Create a second <xref:System.Windows.Forms.Form> in your application called `CodeForm`.</span></span>  
  
4.  <span data-ttu-id="32ca4-113">추가 <xref:System.Windows.Forms.RichTextBox> 컨트롤을 `CodeForm` 설정 하 고 해당 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 `Fill`합니다.</span><span class="sxs-lookup"><span data-stu-id="32ca4-113">Add a <xref:System.Windows.Forms.RichTextBox> control to `CodeForm` and set its <xref:System.Windows.Forms.Control.Dock%2A> property to `Fill`.</span></span>  
  
5.  <span data-ttu-id="32ca4-114">공용 속성을 만들지 `CodeForm` 호출 `Code`합니다.</span><span class="sxs-lookup"><span data-stu-id="32ca4-114">Create a public property on `CodeForm` called `Code`.</span></span>  
  
     [!code-csharp[DisplayWebBrowserCode#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/CodeForm.cs#1)]
     [!code-vb[DisplayWebBrowserCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/CodeForm.vb#1)]  
  
6.  <span data-ttu-id="32ca4-115">추가 <xref:System.Windows.Forms.Button> 라는 컨트롤 `Button1` 에 프로그램 <xref:System.Windows.Forms.Form>, 모니터링는 <xref:System.Windows.Forms.Control.Click> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="32ca4-115">Add a <xref:System.Windows.Forms.Button> control named `Button1` to your <xref:System.Windows.Forms.Form>, and monitor for the <xref:System.Windows.Forms.Control.Click> event.</span></span> <span data-ttu-id="32ca4-116">이벤트를 모니터링에 대 한 자세한 내용은 참조 하십시오. [이벤트](../../../../docs/standard/events/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="32ca4-116">For details on monitoring events, see [Events](../../../../docs/standard/events/index.md).</span></span>  
  
7.  <span data-ttu-id="32ca4-117">다음 코드를 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="32ca4-117">Add the following code to the <xref:System.Windows.Forms.Control.Click> event handler.</span></span>  
  
     [!code-csharp[DisplayWebBrowserCode#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/Form1.cs#2)]
     [!code-vb[DisplayWebBrowserCode#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/Form1.vb#2)]  
  
## <a name="robust-programming"></a><span data-ttu-id="32ca4-118">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="32ca4-118">Robust Programming</span></span>  
 <span data-ttu-id="32ca4-119">검색을 시도하기 전에 항상 <xref:System.Windows.Forms.WebBrowser.Document%2A>의 값을 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32ca4-119">Always test the value of <xref:System.Windows.Forms.WebBrowser.Document%2A> before attempting to retrieve it.</span></span> <span data-ttu-id="32ca4-120">현재 페이지의 로드가 완료되지 않으면 <xref:System.Windows.Forms.WebBrowser.Document%2A> 또는 하나 이상의 해당 자식 개체가 초기화되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32ca4-120">If the current page is not finished loading, <xref:System.Windows.Forms.WebBrowser.Document%2A> or one or more of its child objects may not be initialized.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32ca4-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="32ca4-121">See Also</span></span>  
 [<span data-ttu-id="32ca4-122">관리되는 HTML 문서 개체 모델 사용</span><span class="sxs-lookup"><span data-stu-id="32ca4-122">Using the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)  
 [<span data-ttu-id="32ca4-123">WebBrowser 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="32ca4-123">WebBrowser Control Overview</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)
