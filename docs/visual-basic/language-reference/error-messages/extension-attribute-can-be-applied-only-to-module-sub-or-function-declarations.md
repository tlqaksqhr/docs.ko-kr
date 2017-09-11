---
title: "&quot;Extension&quot; 특성 &quot;Module&quot;, &quot;Sub&quot; 또는 &quot;Function&quot; 선언에만 적용할 수 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36550
- vbc36550
dev_langs:
- VB
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
caps.latest.revision: 18
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
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: e88241180fe1320bfd1db90a38a9a7560ae3dead
ms.contentlocale: ko-kr
ms.lasthandoff: 05/23/2017

---
# <a name="39extension39-attribute-can-be-applied-only-to-39module39-39sub39-or-39function39-declarations"></a><span data-ttu-id="516f6-102">'Extension' 특성 'Module', 'Sub' 또는 'Function' 선언에만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="516f6-102">&#39;Extension&#39; attribute can be applied only to &#39;Module&#39;, &#39;Sub&#39;, or &#39;Function&#39; declarations</span></span>
<span data-ttu-id="516f6-103">Visual Basic의 데이터 형식을 확장 하 여 유일한 방법은 표준 모듈 내에 확장 메서드를 정의 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="516f6-103">The only way to extend a data type in Visual Basic is to define an extension method inside a standard module.</span></span> <span data-ttu-id="516f6-104">확장 메서드는 `Sub` 프로시저 또는 `Function` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="516f6-104">The extension method can be a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="516f6-105">모든 확장 메서드는 확장 특성으로 표시 해야 `<Extension()>`에서 <xref:System.Runtime.CompilerServices?displayProperty=fullName>네임 스페이스.</xref:System.Runtime.CompilerServices?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="516f6-105">All extension methods must be marked with the extension attribute, `<Extension()>`, from the <xref:System.Runtime.CompilerServices?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="516f6-106">필요에 따라 확장 메서드를 포함 하는 모듈은 동일한 방식으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="516f6-106">Optionally, a module that contains an extension method may be marked in the same way.</span></span> <span data-ttu-id="516f6-107">확장 특성을 사용 하지 않는 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="516f6-107">No other use of the extension attribute is valid.</span></span>  
  
 <span data-ttu-id="516f6-108">**오류 ID:** BC36550</span><span class="sxs-lookup"><span data-stu-id="516f6-108">**Error ID:** BC36550</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="516f6-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="516f6-109">To correct this error</span></span>  
  
-   <span data-ttu-id="516f6-110">확장 특성을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="516f6-110">Remove the extension attribute.</span></span>  
  
-   <span data-ttu-id="516f6-111">바깥쪽 모듈에 정의 하는 방법으로 확장 프로그램을 다시 디자인 합니다.</span><span class="sxs-lookup"><span data-stu-id="516f6-111">Redesign your extension as a method, defined in an enclosing module.</span></span>  
  
## <a name="example"></a><span data-ttu-id="516f6-112">예제</span><span class="sxs-lookup"><span data-stu-id="516f6-112">Example</span></span>  
 <span data-ttu-id="516f6-113">다음 예제에서는 정의 `Print` 에 대 한 메서드는 `String` 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="516f6-113">The following example defines a `Print` method for the `String` data type.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="516f6-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="516f6-114">See Also</span></span>  
 <span data-ttu-id="516f6-115">[특성 개요](../../../visual-basic/programming-guide/concepts/attributes/index.md) </span><span class="sxs-lookup"><span data-stu-id="516f6-115">[Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md) </span></span>  
<span data-ttu-id="516f6-116"> [확장 메서드](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md) </span><span class="sxs-lookup"><span data-stu-id="516f6-116"> [Extension Methods](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md) </span></span>  
<span data-ttu-id="516f6-117"> [Module 문](../../../visual-basic/language-reference/statements/module-statement.md)</span><span class="sxs-lookup"><span data-stu-id="516f6-117"> [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md)</span></span>

