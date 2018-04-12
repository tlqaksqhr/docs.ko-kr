---
title: '&#39; 확장 &#39; 특성에만 적용할 수 &#39; 모듈 &#39; &#39; Sub &#39; 또는 &#39; 함수 &#39; 선언'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9d77933c52484eb934501107d1ddad15f0eca826
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="39extension39-attribute-can-be-applied-only-to-39module39-39sub39-or-39function39-declarations"></a><span data-ttu-id="cfdc2-102">&#39; 확장 &#39; 특성에만 적용할 수 &#39; 모듈 &#39; &#39; Sub &#39; 또는 &#39; 함수 &#39; 선언</span><span class="sxs-lookup"><span data-stu-id="cfdc2-102">&#39;Extension&#39; attribute can be applied only to &#39;Module&#39;, &#39;Sub&#39;, or &#39;Function&#39; declarations</span></span>
<span data-ttu-id="cfdc2-103">Visual Basic의 데이터 형식을 확장 하는 유일한 방법은 표준 모듈 내에 확장 메서드를 정의 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc2-103">The only way to extend a data type in Visual Basic is to define an extension method inside a standard module.</span></span> <span data-ttu-id="cfdc2-104">사용할 수 있는 확장 메서드에 `Sub` 프로시저 또는 `Function` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc2-104">The extension method can be a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="cfdc2-105">모든 확장 메서드가 확장 특성으로 표시 해야 `<Extension()>`에서 <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc2-105">All extension methods must be marked with the extension attribute, `<Extension()>`, from the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="cfdc2-106">필요에 따라 확장 메서드를 포함 하는 모듈은 같은 방식으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc2-106">Optionally, a module that contains an extension method may be marked in the same way.</span></span> <span data-ttu-id="cfdc2-107">확장 특성의 사용 하지 않는 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc2-107">No other use of the extension attribute is valid.</span></span>  
  
 <span data-ttu-id="cfdc2-108">**오류 ID:** BC36550</span><span class="sxs-lookup"><span data-stu-id="cfdc2-108">**Error ID:** BC36550</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cfdc2-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="cfdc2-109">To correct this error</span></span>  
  
-   <span data-ttu-id="cfdc2-110">확장 특성을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc2-110">Remove the extension attribute.</span></span>  
  
-   <span data-ttu-id="cfdc2-111">바깥쪽 모듈에 정의 된 메서드와, 확장 프로그램을 다시 디자인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc2-111">Redesign your extension as a method, defined in an enclosing module.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cfdc2-112">예제</span><span class="sxs-lookup"><span data-stu-id="cfdc2-112">Example</span></span>  
 <span data-ttu-id="cfdc2-113">다음 예제에서는 정의 `Print` 에 대 한 메서드는 `String` 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="cfdc2-113">The following example defines a `Print` method for the `String` data type.</span></span>  
  
```  
Imports StringUtility  
Imports System.Runtime.CompilerServices  
Namespace StringUtility  
    <Extension()>   
    Module StringExtensions  
        <Extension()>   
        Public Sub Print (ByVal str As String)  
            Console.WriteLine(str)  
        End Sub  
    End Module  
End Namespace  
```  
  
## <a name="see-also"></a><span data-ttu-id="cfdc2-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cfdc2-114">See Also</span></span>  
 [<span data-ttu-id="cfdc2-115">특성 개요</span><span class="sxs-lookup"><span data-stu-id="cfdc2-115">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [<span data-ttu-id="cfdc2-116">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="cfdc2-116">Extension Methods</span></span>](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)  
 [<span data-ttu-id="cfdc2-117">Module 문</span><span class="sxs-lookup"><span data-stu-id="cfdc2-117">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
