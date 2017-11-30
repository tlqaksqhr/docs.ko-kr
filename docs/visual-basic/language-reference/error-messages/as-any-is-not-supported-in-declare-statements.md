---
title: "&#39; 모든 &#39; 지원 되지 않습니다 &#39; Declare &#39; 문"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30828
- vbc30828
helpviewer_keywords: BC30828
ms.assetid: 7e5cf519-8b64-4ac5-8116-705fe26c846d
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 59120622688ee38d5b8f45c08dfc3ae40711fb8b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="39as-any39-is-not-supported-in-39declare39-statements"></a><span data-ttu-id="d79eb-102">&#39; 모든 &#39; 지원 되지 않습니다 &#39; Declare &#39; 문</span><span class="sxs-lookup"><span data-stu-id="d79eb-102">&#39;As Any&#39; is not supported in &#39;Declare&#39; statements</span></span>
<span data-ttu-id="d79eb-103">`Any` 데이터 형식이 사용 된 `Declare` Visual Basic 6.0 및 이전 버전의 모든 종류의 데이터를 포함할 수 있는 인수 사용을 허용 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="d79eb-103">The `Any` data type was used with `Declare` statements in Visual Basic 6.0 and earlier versions to permit the use of arguments that could contain any type of data.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="d79eb-104">그러나 오버 로드 지원 하 고 그렇게는 `Any` 데이터 형식은 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d79eb-104"> supports overloading, however, and so makes the `Any` data type obsolete.</span></span>  
  
 <span data-ttu-id="d79eb-105">**오류 ID:** BC30828</span><span class="sxs-lookup"><span data-stu-id="d79eb-105">**Error ID:** BC30828</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d79eb-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="d79eb-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="d79eb-107">사용할; 특정 종류의 매개 변수를 선언 합니다. 예를 들어.</span><span class="sxs-lookup"><span data-stu-id="d79eb-107">Declare parameters of the specific type you want to use; for example.</span></span>  
  
     [!code-vb[VbVbalrStatements#95](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_1.vb)]  
  
2.  <span data-ttu-id="d79eb-108">사용 하 여는 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 지정 하려면 특성 `As Any` 때 `Void*` 호출 되는 프로시저에서 예상 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="d79eb-108">Use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to specify `As Any` when `Void*` is expected by the procedure being called.</span></span>  
  
     [!code-vb[VbVbalrStatements#96](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/as-any-is-not-supported-in-declare-statements_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d79eb-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d79eb-109">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="d79eb-110">연습: Windows API 호출</span><span class="sxs-lookup"><span data-stu-id="d79eb-110">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 [<span data-ttu-id="d79eb-111">Declare 문</span><span class="sxs-lookup"><span data-stu-id="d79eb-111">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [<span data-ttu-id="d79eb-112">관리 코드에서 프로토타입 만들기</span><span class="sxs-lookup"><span data-stu-id="d79eb-112">Creating Prototypes in Managed Code</span></span>](../../../framework/interop/creating-prototypes-in-managed-code.md)
