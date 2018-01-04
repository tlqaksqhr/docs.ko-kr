---
title: "방법: WebBrowser 컨트롤을 사용하여 URL 탐색"
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
f1_keywords: WebBrowser.Navigate
helpviewer_keywords:
- WebBrowser control [Windows Forms], examples
- URLs [Windows Forms], navigating to
- WebBrowser control [Windows Forms], navigating to URLs
- examples [Windows Forms], WebBrowser control
ms.assetid: b3ec38cb-f509-4d0b-bd79-9f3611259c62
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a447d69eb6dafbff75ddd9d161abd4f78c607cdd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-navigate-to-a-url-with-the-webbrowser-control"></a><span data-ttu-id="c7d3a-102">방법: WebBrowser 컨트롤을 사용하여 URL 탐색</span><span class="sxs-lookup"><span data-stu-id="c7d3a-102">How to: Navigate to a URL with the WebBrowser Control</span></span>
<span data-ttu-id="c7d3a-103">다음 코드 예제에서는 탐색 하는 방법을 보여 줍니다.는 <xref:System.Windows.Forms.WebBrowser> 특정 URL 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7d3a-103">The following code example demonstrates how to navigate the <xref:System.Windows.Forms.WebBrowser> control to a specific URL.</span></span>  
  
 <span data-ttu-id="c7d3a-104">새 문서를 완전히 로드 하는 시기를 확인 하려면 처리는 <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="c7d3a-104">To determine when the new document is fully loaded, handle the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="c7d3a-105">이 이벤트의 데모를 보려면 참조 [하는 방법: WebBrowser 컨트롤을 사용 하 여 인쇄](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c7d3a-105">For a demonstration of this event, see [How to: Print with a WebBrowser Control](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7d3a-106">예</span><span class="sxs-lookup"><span data-stu-id="c7d3a-106">Example</span></span>  
  
```vb  
Me.webBrowser1.Navigate("http://www.microsoft.com")  
```  
  
```csharp  
this.webBrowser1.Navigate("http://www.microsoft.com");  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c7d3a-107">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="c7d3a-107">Compiling the Code</span></span>  
 <span data-ttu-id="c7d3a-108">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c7d3a-108">This example requires:</span></span>  
  
-   <span data-ttu-id="c7d3a-109">`webBrowser1`이라는 <xref:System.Windows.Forms.WebBrowser> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="c7d3a-109">A <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1`.</span></span>  
  
-   <span data-ttu-id="c7d3a-110">`System` 및 `System.Windows.Forms` 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="c7d3a-110">References to the `System` and `System.Windows.Forms` assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7d3a-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7d3a-111">See Also</span></span>  
 <xref:System.Windows.Forms.WebBrowser>  
 <xref:System.Windows.Forms.WebBrowser.DocumentCompleted?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.WebBrowser.Navigating?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.WebBrowser.Navigated?displayProperty=nameWithType>  
 [<span data-ttu-id="c7d3a-112">WebBrowser 컨트롤</span><span class="sxs-lookup"><span data-stu-id="c7d3a-112">WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-windows-forms.md)  
 [<span data-ttu-id="c7d3a-113">방법: WebBrowser 컨트롤을 사용하여 인쇄</span><span class="sxs-lookup"><span data-stu-id="c7d3a-113">How to: Print with a WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)
