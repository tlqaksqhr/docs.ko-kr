---
title: "My.Response 개체 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- My.MyWebExtension.Response
- My.Response
dev_langs:
- VB
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b9b34c9df31536f6d553cda2e26677a2645768c2
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="myresponse-object"></a><span data-ttu-id="59f77-102">My.Response 개체</span><span class="sxs-lookup"><span data-stu-id="59f77-102">My.Response Object</span></span>
<span data-ttu-id="59f77-103"><xref:System.Web.HttpResponse> <xref:System.Web.UI.Page>.</xref:System.Web.UI.Page> 와 연결 된 개체</xref:System.Web.HttpResponse> 를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="59f77-103">Gets the <xref:System.Web.HttpResponse> object associated with the <xref:System.Web.UI.Page>.</span></span> <span data-ttu-id="59f77-104">이 개체를 클라이언트에 HTTP 응답 데이터를 보낼 수 있도록 및 해당 응답에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="59f77-104">This object allows you to send HTTP response data to a client and contains information about that response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59f77-105">설명</span><span class="sxs-lookup"><span data-stu-id="59f77-105">Remarks</span></span>  
 <span data-ttu-id="59f77-106">`My.Response` 개체에 현재 포함 되어 <xref:System.Web.HttpResponse>페이지와 관련 된 개체입니다.</xref:System.Web.HttpResponse></span><span class="sxs-lookup"><span data-stu-id="59f77-106">The `My.Response` object contains the current <xref:System.Web.HttpResponse> object associated with the page.</span></span>  
  
 <span data-ttu-id="59f77-107">`My.Response` 개체는 사용할 수만 [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="59f77-107">The `My.Response` object is only available for [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59f77-108">예제</span><span class="sxs-lookup"><span data-stu-id="59f77-108">Example</span></span>  
 <span data-ttu-id="59f77-109">다음 예제에서 헤더 컬렉션을 가져오고는 `My.Request` 사용 하 여 개체는 `My.Response` ASP.NET 페이지에 쓸 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="59f77-109">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 <span data-ttu-id="59f77-110">[!code-vb[VbVbalrMyWeb #&1;](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-response-object_1.aspx)]</span><span class="sxs-lookup"><span data-stu-id="59f77-110">[!code-vb[VbVbalrMyWeb#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-response-object_1.aspx)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59f77-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59f77-111">See Also</span></span>  
 <span data-ttu-id="59f77-112"><xref:System.Web.HttpResponse></xref:System.Web.HttpResponse></span><span class="sxs-lookup"><span data-stu-id="59f77-112"><xref:System.Web.HttpResponse></span></span>   
<span data-ttu-id="59f77-113"> [My.Request 개체](../../../visual-basic/language-reference/objects/my-request-object.md)</span><span class="sxs-lookup"><span data-stu-id="59f77-113"> [My.Request Object](../../../visual-basic/language-reference/objects/my-request-object.md)</span></span>
