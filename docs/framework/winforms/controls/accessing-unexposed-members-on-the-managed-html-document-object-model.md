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
ms.openlocfilehash: dda2581ceed854fa5121076f0c7b9df414bffe52
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="accessing-unexposed-members-on-the-managed-html-document-object-model"></a><span data-ttu-id="b6324-102">관리되는 HTML 문서 개체 모델의 노출되지 않은 멤버에 액세스</span><span class="sxs-lookup"><span data-stu-id="b6324-102">Accessing Unexposed Members on the Managed HTML Document Object Model</span></span>
<span data-ttu-id="b6324-103">라는 클래스를 포함 하는 관리 되는 HTML 문서 개체 모델 (DOM) <xref:System.Windows.Forms.HtmlElement> 속성, 메서드 및 모든 HTML 요소에 공통 된 이벤트를 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6324-103">The managed HTML Document Object Model (DOM) contains a class called <xref:System.Windows.Forms.HtmlElement> that exposes the properties, methods, and events that all HTML elements have in common.</span></span> <span data-ttu-id="b6324-104">그러나 경우에 따라 해야 합니다 직접 관리 되는 인터페이스를 노출 하지 않는 멤버에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6324-104">Sometimes, however, you will need to access members that the managed interface does not directly expose.</span></span> <span data-ttu-id="b6324-105">이 항목을 포함 하는 노출 되지 않은 멤버에 액세스 하기 위한 두 가지 방법으로 검사 [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] 및 웹 페이지 내에서 정의 된 VBScript 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="b6324-105">This topic examines two ways for accessing unexposed members, including [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] and VBScript functions defined inside of a Web page.</span></span>  
  
## <a name="accessing-unexposed-members-through-managed-interfaces"></a><span data-ttu-id="b6324-106">관리 되는 인터페이스를 통해 노출 되지 않은 멤버 액세스</span><span class="sxs-lookup"><span data-stu-id="b6324-106">Accessing Unexposed Members through Managed Interfaces</span></span>  
 <span data-ttu-id="b6324-107"><xref:System.Windows.Forms.HtmlDocument>및 <xref:System.Windows.Forms.HtmlElement> 노출 되지 않은 멤버에 대 한 액세스를 사용할 수 있는 네 가지 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6324-107"><xref:System.Windows.Forms.HtmlDocument> and <xref:System.Windows.Forms.HtmlElement> provide four methods that enable access to unexposed members.</span></span> <span data-ttu-id="b6324-108">다음 표에서 형식 및 해당 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b6324-108">The following table shows the types and their corresponding methods.</span></span>  
  
|<span data-ttu-id="b6324-109">멤버 형식</span><span class="sxs-lookup"><span data-stu-id="b6324-109">Member Type</span></span>|<span data-ttu-id="b6324-110">메서드</span><span class="sxs-lookup"><span data-stu-id="b6324-110">Method(s)</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="b6324-111">속성 (<xref:System.Windows.Forms.HtmlElement>)</span><span class="sxs-lookup"><span data-stu-id="b6324-111">Properties (<xref:System.Windows.Forms.HtmlElement>)</span></span>|<xref:System.Windows.Forms.HtmlElement.GetAttribute%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.SetAttribute%2A>|  
|<span data-ttu-id="b6324-112">메서드</span><span class="sxs-lookup"><span data-stu-id="b6324-112">Methods</span></span>|<xref:System.Windows.Forms.HtmlElement.InvokeMember%2A>|  
|<span data-ttu-id="b6324-113">이벤트 (<xref:System.Windows.Forms.HtmlDocument>)</span><span class="sxs-lookup"><span data-stu-id="b6324-113">Events (<xref:System.Windows.Forms.HtmlDocument>)</span></span>|<xref:System.Windows.Forms.HtmlDocument.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlDocument.DetachEventHandler%2A>|  
|<span data-ttu-id="b6324-114">이벤트 (<xref:System.Windows.Forms.HtmlElement>)</span><span class="sxs-lookup"><span data-stu-id="b6324-114">Events (<xref:System.Windows.Forms.HtmlElement>)</span></span>|<xref:System.Windows.Forms.HtmlElement.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.DetachEventHandler%2A>|  
|<span data-ttu-id="b6324-115">이벤트 (<xref:System.Windows.Forms.HtmlWindow>)</span><span class="sxs-lookup"><span data-stu-id="b6324-115">Events (<xref:System.Windows.Forms.HtmlWindow>)</span></span>|<xref:System.Windows.Forms.HtmlWindow.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlWindow.DetachEventHandler%2A>|  
  
 <span data-ttu-id="b6324-116">이러한 메서드를 사용 하는 경우 올바른 기본 형식의 요소가 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6324-116">When you use these methods, it is assumed that you have an element of the correct underlying type.</span></span> <span data-ttu-id="b6324-117">수신 대기 하려고 한다고 가정할 경우는 `Submit` 의 이벤트는 `FORM` 요소에는 HTML 페이지에 몇 가지 전처리 작업을 수행할 수 있도록는 `FORM`의 사용자가 서버에 제출 하기 전에 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b6324-117">Suppose that you want to listen to the `Submit` event of a `FORM` element on an HTML page, so that you can perform some pre-processing on the `FORM`'s values before the user submits them to the server.</span></span> <span data-ttu-id="b6324-118">이상적으로 HTML에 대 한 제어를 사용 하는 경우 정의 하는 `FORM` 는 고유 해야 `ID` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b6324-118">Ideally, if you have control over the HTML, you would define the `FORM` to have a unique `ID` attribute.</span></span>  
  
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
  
 <span data-ttu-id="b6324-119">이 페이지를 로드 한 후에 <xref:System.Windows.Forms.WebBrowser> 컨트롤, 있습니다 사용할 수 있습니다는 <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> 를 검색할 메서드는 `FORM` 사용 하 여 런타임에 `form1` 인수로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6324-119">After you load this page into the <xref:System.Windows.Forms.WebBrowser> control, you can use the <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> method to retrieve the `FORM` at run time using `form1` as the argument.</span></span>  
  
 [!code-csharp[System.Windows.Forms.HtmlElement#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/CS/Form1.cs#10)]
 [!code-vb[System.Windows.Forms.HtmlElement#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/VB/Form1.vb#10)]  
  
## <a name="accessing-unmanaged-interfaces"></a><span data-ttu-id="b6324-120">관리 되지 않는 인터페이스에 액세스</span><span class="sxs-lookup"><span data-stu-id="b6324-120">Accessing Unmanaged Interfaces</span></span>  
 <span data-ttu-id="b6324-121">또한 각 DOM 클래스에 의해 노출 되는 관리 되지 않는 구성 요소 개체 모델 (COM) 인터페이스를 사용 하 여 관리 되는 HTML DOM에 노출 되지 않은 멤버를 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6324-121">You can also access unexposed members on the managed HTML DOM by using the unmanaged Component Object Model (COM) interfaces exposed by each DOM class.</span></span> <span data-ttu-id="b6324-122">노출 되지 않은 멤버는 관리 되는 HTML DOM으로 래핑되지 다른 관리 되지 않는 인터페이스를 반환 하는 경우 또는 노출 되지 않은 멤버에 대 한 여러 호출을 수행 해야 할 경우이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b6324-122">This is recommended if you have to make several calls against unexposed members, or if the unexposed members return other unmanaged interfaces not wrapped by the managed HTML DOM.</span></span>  
  
 <span data-ttu-id="b6324-123">다음 표에서 모든 관리 되는 HTML DOM을 통해 제공 되는 관리 되지 않는 인터페이스 표시</span><span class="sxs-lookup"><span data-stu-id="b6324-123">The following table shows all of the unmanaged interfaces exposed through the managed HTML DOM.</span></span> <span data-ttu-id="b6324-124">각 링크에 대 한 설명은 해당 사용법 및 예를 들어 코드에서 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6324-124">Click on each link for an explanation of its usage and for example code.</span></span>  
  
|<span data-ttu-id="b6324-125">형식</span><span class="sxs-lookup"><span data-stu-id="b6324-125">Type</span></span>|<span data-ttu-id="b6324-126">관리 되지 않는 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b6324-126">Unmanaged Interface</span></span>|  
|----------|-------------------------|  
|<xref:System.Windows.Forms.HtmlDocument>|<xref:System.Windows.Forms.HtmlDocument.DomDocument%2A>|  
|<xref:System.Windows.Forms.HtmlElement>|<xref:System.Windows.Forms.HtmlElement.DomElement%2A>|  
|<xref:System.Windows.Forms.HtmlWindow>|<xref:System.Windows.Forms.HtmlWindow.DomWindow%2A>|  
|<xref:System.Windows.Forms.HtmlHistory>|<xref:System.Windows.Forms.HtmlHistory.DomHistory%2A>|  
  
 <span data-ttu-id="b6324-127">COM 인터페이스를 사용 하는 가장 쉬운 방법은 지원 되는 것은 아니지만 응용 프로그램에서 관리 되지 않는 HTML DOM 라이브러리 (MSHTML.dll)에 대 한 참조를 추가 하입니다.</span><span class="sxs-lookup"><span data-stu-id="b6324-127">The easiest way to use the COM interfaces is to add a reference to the unmanaged HTML DOM library (MSHTML.dll) from your application, although this is unsupported.</span></span> <span data-ttu-id="b6324-128">자세한 내용은 참조 [기술 자료 문서 934368](http://support.microsoft.com/kb/934368)합니다.</span><span class="sxs-lookup"><span data-stu-id="b6324-128">For more information, see [Knowledge Base Article 934368](http://support.microsoft.com/kb/934368).</span></span>  
  
## <a name="accessing-script-functions"></a><span data-ttu-id="b6324-129">스크립트 함수에 액세스</span><span class="sxs-lookup"><span data-stu-id="b6324-129">Accessing Script Functions</span></span>  
 <span data-ttu-id="b6324-130">HTML 페이지와 같은 스크립트 언어를 사용 하 여 하나 이상의 함수를 정의할 수 [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] 또는 VBScript입니다.</span><span class="sxs-lookup"><span data-stu-id="b6324-130">An HTML page can define one or more functions by using a scripting language such as [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] or VBScript.</span></span> <span data-ttu-id="b6324-131">이러한 함수 내부에 배치 되며는 `SCRIPT` 페이지에서 페이지 및 DOM에서 요청 시 또는 이벤트에 대 한 응답으로 실행 수</span><span class="sxs-lookup"><span data-stu-id="b6324-131">These functions are placed inside of a `SCRIPT` page in the page, and can be run on demand or in response to an event on the DOM.</span></span>  
  
 <span data-ttu-id="b6324-132">사용 하 여 HTML 페이지에 정의 되는 스크립트 함수를 호출할 수는 <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="b6324-132">You can call any script functions you define in an HTML page using the <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> method.</span></span> <span data-ttu-id="b6324-133">스크립트 메서드는 HTML 요소를 반환 하면이 반환 결과 변환 하는 캐스트를 사용할 수 있습니다는 <xref:System.Windows.Forms.HtmlElement>합니다.</span><span class="sxs-lookup"><span data-stu-id="b6324-133">If the script method returns an HTML element, you can use a cast to convert this return result to an <xref:System.Windows.Forms.HtmlElement>.</span></span> <span data-ttu-id="b6324-134">자세한 내용 및 예제 코드 참조 <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="b6324-134">For details and example code, see <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6324-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b6324-135">See Also</span></span>  
 [<span data-ttu-id="b6324-136">관리되는 HTML 문서 개체 모델 사용</span><span class="sxs-lookup"><span data-stu-id="b6324-136">Using the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)
