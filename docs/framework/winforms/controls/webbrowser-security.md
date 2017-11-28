---
title: "WebBrowser 보안"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WebBrowser control [Windows Forms], security
- security [Windows Forms], WebBrowser control
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a0d84f0c70619324bbbd38a2961914f88ac42671
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="webbrowser-security"></a><span data-ttu-id="6891b-102">WebBrowser 보안</span><span class="sxs-lookup"><span data-stu-id="6891b-102">WebBrowser Security</span></span>
<span data-ttu-id="6891b-103"><xref:System.Windows.Forms.WebBrowser> 컨트롤은 완전 신뢰 수준에서 작동 하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6891b-103">The <xref:System.Windows.Forms.WebBrowser> control is designed to work in full trust only.</span></span> <span data-ttu-id="6891b-104">컨트롤에 표시 되는 HTML 콘텐츠 외부 웹 서버에서 가져올 수 있습니다 및 스크립트 또는 웹 컨트롤의 형태로 비관리 코드를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6891b-104">The HTML content displayed in the control can come from external Web servers and may contain unmanaged code in the form of scripts or Web controls.</span></span> <span data-ttu-id="6891b-105">사용 하는 경우는 <xref:System.Windows.Forms.WebBrowser> 컨트롤 이런이 경우에는 컨트롤은 하지만 관리 되는 Internet Explorer를 사용할 때 보다 덜 안전 <xref:System.Windows.Forms.WebBrowser> 컨트롤 사용 해도 이러한 비관리 코드를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6891b-105">If you use the <xref:System.Windows.Forms.WebBrowser> control in this situation, the control is no less secure than Internet Explorer would be, but the managed <xref:System.Windows.Forms.WebBrowser> control does not prevent such unmanaged code from running.</span></span>  
  
 <span data-ttu-id="6891b-106">내부 ActiveX와 관련 된 보안 문제에 대 한 자세한 내용은 `WebBrowser` 제어, 참조 [WebBrowser 컨트롤](http://go.microsoft.com/fwlink/?LinkId=198812)합니다.</span><span class="sxs-lookup"><span data-stu-id="6891b-106">For more information about security issues relating to the underlying ActiveX `WebBrowser` control, see [WebBrowser Control](http://go.microsoft.com/fwlink/?LinkId=198812).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6891b-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6891b-107">See Also</span></span>  
 <xref:System.Windows.Forms.WebBrowser>  
 [<span data-ttu-id="6891b-108">WebBrowser 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="6891b-108">WebBrowser Control Overview</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)  
 [<span data-ttu-id="6891b-109">WebBrowser 컨트롤</span><span class="sxs-lookup"><span data-stu-id="6891b-109">WebBrowser Control</span></span>](http://go.microsoft.com/fwlink/?LinkId=198812)
