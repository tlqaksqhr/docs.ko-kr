---
title: "식이 재귀적으로 포함 하는 속성 &#39; 호출 &lt;propertyname&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42026
- BC42026
helpviewer_keywords: BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 47de3c2d25336962168f01a4c8717274de7c9aad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="expression-recursively-calls-the-containing-property-39ltpropertynamegt39"></a><span data-ttu-id="a7127-102">식이 재귀적으로 포함 하는 속성 &#39; 호출 &lt;propertyname&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="a7127-102">Expression recursively calls the containing property &#39;&lt;propertyname&gt;&#39;</span></span>
<span data-ttu-id="a7127-103">문은 `Set` 프로시저 속성 정의의 값을 속성의 이름에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7127-103">A statement in the `Set` procedure of a property definition stores a value into the name of the property.</span></span>  
  
 <span data-ttu-id="a7127-104">정의 하는 속성의 값을 보유 하는 것이 좋습니다는 `Private` 속성의 컨테이너에 변수 둘 다에서 사용 하는 `Get` 및 `Set` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="a7127-104">The recommended approach to holding the value of a property is to define a `Private` variable in the property's container and use it in both the `Get` and `Set` procedures.</span></span> <span data-ttu-id="a7127-105">`Set` 프로시저 해야이 들어오는 값을 저장 한 다음 `Private` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="a7127-105">The `Set` procedure should then store the incoming value in this `Private` variable.</span></span>  
  
 <span data-ttu-id="a7127-106">`Get` 프로시저 처럼 동작는 `Function` 프로시저, 속성 이름에 값을 할당 하 고 발생 하 여 컨트롤을 반환할 수 있도록는 `End Get` 문.</span><span class="sxs-lookup"><span data-stu-id="a7127-106">The `Get` procedure behaves like a `Function` procedure, so it can assign a value to the property name and return control by encountering the `End Get` statement.</span></span> <span data-ttu-id="a7127-107">그러나 권장 되는 방법 포함 하도록는 `Private` 에 값으로 변수는 [Return 문을](../../../visual-basic/language-reference/statements/return-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a7127-107">The recommended approach, however, is to include the `Private` variable as the value in a [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).</span></span>  
  
 <span data-ttu-id="a7127-108">`Set` 프로시저 처럼 동작는 `Sub` 프로시저에서 값을 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7127-108">The `Set` procedure behaves like a `Sub` procedure, which does not return a value.</span></span> <span data-ttu-id="a7127-109">따라서 프로시저 또는 속성 이름에 내에서 특별 한 의미는 `Set` 프로시저에 값을 저장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7127-109">Therefore, the procedure or property name has no special meaning within a `Set` procedure, and you cannot store a value into it.</span></span>  
  
 <span data-ttu-id="a7127-110">다음 예제에는 뒤에 권장 되는 방법으로이 오류를 일으킬 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a7127-110">The following example illustrates the approach that can cause this error, followed by the recommended approach.</span></span>  
  
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
  
 <span data-ttu-id="a7127-111">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="a7127-111">By default, this message is a warning.</span></span> <span data-ttu-id="a7127-112">경고를 숨기 거 나 경고를 오류로 처리 하는 방법에 대 한 자세한 내용은 참조 하십시오 [Visual Basic에서 경고 구성](/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="a7127-112">For more information about hiding warnings or treating warnings as errors, please see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="a7127-113">**오류 ID:** BC42026</span><span class="sxs-lookup"><span data-stu-id="a7127-113">**Error ID:** BC42026</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a7127-114">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="a7127-114">To correct this error</span></span>  
  
-   <span data-ttu-id="a7127-115">앞의 예제와 같이 한 권장된 접근 방식을 사용 하도록 속성 정의 다시 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7127-115">Rewrite the property definition to use the recommended approach as illustrated in the preceding example.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7127-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a7127-116">See Also</span></span>  
 [<span data-ttu-id="a7127-117">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="a7127-117">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [<span data-ttu-id="a7127-118">Property 문</span><span class="sxs-lookup"><span data-stu-id="a7127-118">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="a7127-119">Set 문</span><span class="sxs-lookup"><span data-stu-id="a7127-119">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
