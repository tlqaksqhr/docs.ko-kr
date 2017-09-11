---
title: "포함 하는 속성을 호출 하는 식을 재귀적으로 &quot;&lt;propertyname&gt;&quot; | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42026
- BC42026
dev_langs:
- VB
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
caps.latest.revision: 10
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
ms.openlocfilehash: c7168ab2a2ec5eb0c0d423120b67c10b117c14b2
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="expression-recursively-calls-the-containing-property-39ltpropertynamegt39"></a><span data-ttu-id="59f47-102">포함 하는 속성을 호출 하는 식을 재귀적으로 '&lt;propertyname&gt;'</span><span class="sxs-lookup"><span data-stu-id="59f47-102">Expression recursively calls the containing property &#39;&lt;propertyname&gt;&#39;</span></span>
<span data-ttu-id="59f47-103">문에 `Set` 프로시저 속성 정의의 값을 속성의 이름에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="59f47-103">A statement in the `Set` procedure of a property definition stores a value into the name of the property.</span></span>  
  
 <span data-ttu-id="59f47-104">정의 하는 속성의 값을 보유 하는 것이 좋습니다는 `Private` 속성의 컨테이너에 있는 변수 둘 다에서 사용 하는 `Get` 및 `Set` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="59f47-104">The recommended approach to holding the value of a property is to define a `Private` variable in the property's container and use it in both the `Get` and `Set` procedures.</span></span> <span data-ttu-id="59f47-105">`Set` 프로시저 들어오는 값이 다음 저장 해야 `Private` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="59f47-105">The `Set` procedure should then store the incoming value in this `Private` variable.</span></span>  
  
 <span data-ttu-id="59f47-106">`Get` 프로시저 처럼 동작는 `Function` 속성 이름에 값을 할당 하 고 발생 하 여 컨트롤을 반환할 수 있도록 프로시저는 `End Get` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="59f47-106">The `Get` procedure behaves like a `Function` procedure, so it can assign a value to the property name and return control by encountering the `End Get` statement.</span></span> <span data-ttu-id="59f47-107">그러나 포함 하는 권장 되는 방법, 것은 `Private` 에 값으로 변수는 [Return 문을](../../../visual-basic/language-reference/statements/return-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="59f47-107">The recommended approach, however, is to include the `Private` variable as the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 <span data-ttu-id="59f47-108">`Set` 프로시저 처럼 동작을 `Sub` 프로시저에서 값을 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59f47-108">The `Set` procedure behaves like a `Sub` procedure, which does not return a value.</span></span> <span data-ttu-id="59f47-109">따라서 프로시저 또는 속성 이름에 내에서 특별 한 의미는 `Set` 프로시저에 값을 저장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="59f47-109">Therefore, the procedure or property name has no special meaning within a `Set` procedure, and you cannot store a value into it.</span></span>  
  
 <span data-ttu-id="59f47-110">다음 예제에는 뒤에 권장 되는 방법으로이 오류를 일으킬 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="59f47-110">The following example illustrates the approach that can cause this error, followed by the recommended approach.</span></span>  
  
```  
Public Class illustrateProperties  
' The code in the following property causes this error.  
    Public Property badProp() As Char  
        Get  
            Dim charValue As Char  
            ' Insert code to update charValue.  
            badProp = charValue  
        End Get  
        Set(ByVal Value As Char)  
            ' The following statement causes this error.  
            badProp = Value  
            ' The value stored in the local variable badProp  
            ' is not used by the Get procedure in this property.  
        End Set  
    End Property  
' The following code uses the recommended approach.  
    Private propValue As Char  
    Public Property goodProp() As Char  
        Get  
            ' Insert code to update propValue.  
            Return propValue  
        End Get  
        Set(ByVal Value As Char)  
            propValue = Value  
        End Set  
    End Property  
End Class  
```  
  
 <span data-ttu-id="59f47-111">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="59f47-111">By default, this message is a warning.</span></span> <span data-ttu-id="59f47-112">경고를 숨기 거 나 경고를 오류로 처리 하는 방법에 대 한 자세한 내용은 참조 하십시오 [Visual Basic에서 경고 구성](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="59f47-112">For more information about hiding warnings or treating warnings as errors, please see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="59f47-113">**오류 ID:** BC42026</span><span class="sxs-lookup"><span data-stu-id="59f47-113">**Error ID:** BC42026</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="59f47-114">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="59f47-114">To correct this error</span></span>  
  
-   <span data-ttu-id="59f47-115">앞의 예제와 같이 권장 되는 방법을 사용 하 여 속성 정의 다시 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="59f47-115">Rewrite the property definition to use the recommended approach as illustrated in the preceding example.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59f47-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59f47-116">See Also</span></span>  
 <span data-ttu-id="59f47-117">[속성 프로시저](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="59f47-117">[Property Procedures](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md) </span></span>  
<span data-ttu-id="59f47-118"> [Property 문](../../../visual-basic/language-reference/statements/property-statement.md) </span><span class="sxs-lookup"><span data-stu-id="59f47-118"> [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) </span></span>  
<span data-ttu-id="59f47-119"> [Set 문](../../../visual-basic/language-reference/statements/set-statement.md)</span><span class="sxs-lookup"><span data-stu-id="59f47-119"> [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md)</span></span>
