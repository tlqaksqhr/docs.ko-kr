---
title: "My.Request 개체"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- My.MyWebExtension.Request
- My.Request
helpviewer_keywords: My.Request object
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e0e67c8fd85860eacc57bcc7dd7f15f97097efe3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="myrequest-object"></a><span data-ttu-id="316c1-102">My.Request 개체</span><span class="sxs-lookup"><span data-stu-id="316c1-102">My.Request Object</span></span>
<span data-ttu-id="316c1-103">요청된 페이지에 대한 <xref:System.Web.HttpRequest> 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="316c1-103">Gets the <xref:System.Web.HttpRequest> object for the requested page.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="316c1-104">설명</span><span class="sxs-lookup"><span data-stu-id="316c1-104">Remarks</span></span>  
 <span data-ttu-id="316c1-105">`My.Request` 개체에는 현재 HTTP 요청에 대한 정보가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="316c1-105">The `My.Request` object contains information about the current HTTP request.</span></span>  
  
 <span data-ttu-id="316c1-106">`My.Request` 개체는 ASP.NET 응용 프로그램에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="316c1-106">The `My.Request` object is available only for ASP.NET applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="316c1-107">예제</span><span class="sxs-lookup"><span data-stu-id="316c1-107">Example</span></span>  
 <span data-ttu-id="316c1-108">다음 예제에서는에서 헤더 컬렉션을 가져옵니다는 `My.Request` 개체와 사용 하 여는 `My.Response` ASP.NET 페이지에 쓸 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="316c1-108">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-vb[VbVbalrMyWeb#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-request-object_1.aspx)]  
  
## <a name="see-also"></a><span data-ttu-id="316c1-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="316c1-109">See Also</span></span>  
 <xref:System.Web.HttpRequest>  
 [<span data-ttu-id="316c1-110">My.Response 개체</span><span class="sxs-lookup"><span data-stu-id="316c1-110">My.Response Object</span></span>](../../../visual-basic/language-reference/objects/my-response-object.md)
