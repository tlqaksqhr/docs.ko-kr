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
ms.workload: dotnet
ms.openlocfilehash: 00be8ca2e4e227b6e4593b0a9e32172ecb9457f5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-an-html-document-viewer-in-a-windows-forms-application"></a><span data-ttu-id="d9e11-102">방법: Windows Forms 응용 프로그램에서 HTML 문서 뷰어 만들기</span><span class="sxs-lookup"><span data-stu-id="d9e11-102">How to: Create an HTML Document Viewer in a Windows Forms Application</span></span>
<span data-ttu-id="d9e11-103">사용할 수는 <xref:System.Windows.Forms.WebBrowser> 컨트롤 표시 하 고는 인터넷 웹 브라우저의 전체 기능을 제공 하지 않고 HTML 문서를 인쇄 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e11-103">You can use the <xref:System.Windows.Forms.WebBrowser> control to display and print HTML documents without providing the full functionality of an Internet Web browser.</span></span> <span data-ttu-id="d9e11-104">Html 서식 지정 기능을 활용 하려고 하지만 사용자가 신뢰할 수 없는 웹 컨트롤 또는 잠재적 악성 스크립트 코드를 포함할 수 있는 임의 웹 페이지를 로드 하지 않을 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e11-104">This is useful when you want to take advantage of the formatting capabilities of HTML but do not want your users to load arbitrary Web pages that may contain untrusted Web controls or potentially malicious script code.</span></span> <span data-ttu-id="d9e11-105">기능을 제한 하려는 경우는 <xref:System.Windows.Forms.WebBrowser> HTML 전자 메일 뷰어도 사용 하거나 응용 프로그램에서 HTML 형식의 도움말을 제공 하려면 예를 들어 이러한 방식으로 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e11-105">You might want to restrict the capability of the <xref:System.Windows.Forms.WebBrowser> control in this manner, for example, to use it as an HTML e-mail viewer or to provide HTML-formatted help in your application.</span></span>  
  
### <a name="to-create-an-html-document-viewer"></a><span data-ttu-id="d9e11-106">HTML 문서 뷰어 만들기를</span><span class="sxs-lookup"><span data-stu-id="d9e11-106">To create an HTML document viewer</span></span>  
  
1.  <span data-ttu-id="d9e11-107">설정의 <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> 속성을 `false` 방지 하기 위해는 <xref:System.Windows.Forms.WebBrowser> 컨트롤이 놓여진 파일을 열 수 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e11-107">Set the <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> property to `false` to prevent the <xref:System.Windows.Forms.WebBrowser> control from opening files dropped onto it.</span></span>  
  
     [!code-csharp[WebBrowserMisc#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#20)]
     [!code-vb[WebBrowserMisc#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#20)]  
  
2.  <span data-ttu-id="d9e11-108">설정의 <xref:System.Windows.Forms.WebBrowser.Url%2A> 속성을 표시할 초기 파일의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="d9e11-108">Set the <xref:System.Windows.Forms.WebBrowser.Url%2A> property to the location of the initial file to display.</span></span>  
  
     [!code-csharp[WebBrowserMisc#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#21)]
     [!code-vb[WebBrowserMisc#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d9e11-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="d9e11-109">Compiling the Code</span></span>  
 <span data-ttu-id="d9e11-110">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e11-110">This example requires:</span></span>  
  
-   <span data-ttu-id="d9e11-111">`webBrowser1`이라는 <xref:System.Windows.Forms.WebBrowser> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="d9e11-111">A <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1`.</span></span>  
  
-   <span data-ttu-id="d9e11-112">`System` 및 `System.Windows.Forms` 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="d9e11-112">References to the `System` and `System.Windows.Forms` assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9e11-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9e11-113">See Also</span></span>  
 <xref:System.Windows.Forms.WebBrowser>  
 <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>  
 <xref:System.Windows.Forms.WebBrowser.Url%2A>  
 [<span data-ttu-id="d9e11-114">WebBrowser 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="d9e11-114">WebBrowser Control Overview</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)  
 [<span data-ttu-id="d9e11-115">WebBrowser 보안</span><span class="sxs-lookup"><span data-stu-id="d9e11-115">WebBrowser Security</span></span>](../../../../docs/framework/winforms/controls/webbrowser-security.md)  
 [<span data-ttu-id="d9e11-116">방법: WebBrowser 컨트롤을 사용하여 URL 탐색</span><span class="sxs-lookup"><span data-stu-id="d9e11-116">How to: Navigate to a URL with the WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/how-to-navigate-to-a-url-with-the-webbrowser-control.md)  
 [<span data-ttu-id="d9e11-117">방법: WebBrowser 컨트롤을 사용하여 인쇄</span><span class="sxs-lookup"><span data-stu-id="d9e11-117">How to: Print with a WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)
