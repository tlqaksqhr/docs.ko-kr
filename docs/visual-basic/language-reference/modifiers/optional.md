---
title: Optional(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Optional
- vb.optional
helpviewer_keywords:
- Optional keyword [Visual Basic], contexts
- Optional keyword [Visual Basic]
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3aa01c2c1ae731c8fe00fdee24521760db69e624
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="optional-visual-basic"></a><span data-ttu-id="fda79-102">Optional(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fda79-102">Optional (Visual Basic)</span></span>
<span data-ttu-id="fda79-103">프로시저가 호출 될 때 프로시저 인수를 생략할 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda79-103">Specifies that a procedure argument can be omitted when the procedure is called.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fda79-104">설명</span><span class="sxs-lookup"><span data-stu-id="fda79-104">Remarks</span></span>  
 <span data-ttu-id="fda79-105">각 선택적 매개 변수를 상수 식의 매개 변수 값을 기본값으로 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda79-105">For each optional parameter, you must specify a constant expression as the default value of that parameter.</span></span> <span data-ttu-id="fda79-106">식이 계산 되는 경우 [Nothing](../../../visual-basic/language-reference/nothing.md), 값 데이터 형식의 기본 값 매개 변수의 값을 기본값으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fda79-106">If the expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the default value of the value data type is used as the default value of the parameter.</span></span>  
  
 <span data-ttu-id="fda79-107">선택적 매개 변수를 포함 하는 매개 변수 목록, 그 다음에 오는 모든 매개 변수에 선택적 수도 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda79-107">If the parameter list contains an optional parameter, every parameter that follows it must also be optional.</span></span>  
  
 <span data-ttu-id="fda79-108">`Optional` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda79-108">The `Optional` modifier can be used in these contexts:</span></span>  
  
-   [<span data-ttu-id="fda79-109">Declare 문</span><span class="sxs-lookup"><span data-stu-id="fda79-109">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [<span data-ttu-id="fda79-110">Function 문</span><span class="sxs-lookup"><span data-stu-id="fda79-110">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [<span data-ttu-id="fda79-111">Property 문</span><span class="sxs-lookup"><span data-stu-id="fda79-111">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [<span data-ttu-id="fda79-112">Sub 문</span><span class="sxs-lookup"><span data-stu-id="fda79-112">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
> [!NOTE]
>  <span data-ttu-id="fda79-113">또는 선택적 매개 변수 없이 프로시저를 호출할 때 위치 또는 이름으로 인수를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda79-113">When calling a procedure with or without optional parameters, you can pass arguments by position or by name.</span></span> <span data-ttu-id="fda79-114">자세한 내용은 참조 [이름 및 위치도 인수 전달](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fda79-114">For more information, see [Passing Arguments by Position and by Name](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fda79-115">오버 로드를 사용 하 여 선택적 매개 변수가 있는 프로시저를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda79-115">You can also define a procedure with optional parameters by using overloading.</span></span> <span data-ttu-id="fda79-116">하나의 선택적 매개 변수를 설정한 경우에 프로시저, 매개 변수를 허용 하 고 다른 하나는 하지 않는 두 개의 오버 로드 된 버전을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fda79-116">If you have one optional parameter, you can define two overloaded versions of the procedure, one that accepts the parameter and one that doesn’t.</span></span> <span data-ttu-id="fda79-117">자세한 내용은 참조 [프로시저 오버 로드](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fda79-117">For more information, see [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fda79-118">예제</span><span class="sxs-lookup"><span data-stu-id="fda79-118">Example</span></span>  
 <span data-ttu-id="fda79-119">다음 예제에서는 선택적 매개 변수가 있는 프로시저를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="fda79-119">The following example defines a procedure that has an optional parameter.</span></span>  
  
```  
Public Function FindMatches(ByRef values As List(Of String),  
                            ByVal searchString As String,  
                            Optional ByVal matchCase As Boolean = False) As List(Of String)  
  
    Dim results As IEnumerable(Of String)  
  
    If matchCase Then  
        results = From v In values  
                  Where v.Contains(searchString)  
    Else  
        results = From v In values  
                  Where UCase(v).Contains(UCase(searchString))  
    End If  
  
    Return results.ToList()  
End Function  
```  
  
## <a name="example"></a><span data-ttu-id="fda79-120">예제</span><span class="sxs-lookup"><span data-stu-id="fda79-120">Example</span></span>  
 <span data-ttu-id="fda79-121">다음 예제에서는 위치로 전달 된 인수를 사용 하 고 이름으로 전달 된 인수와 함께 프로시저를 호출 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fda79-121">The following example demonstrates how to call a procedure with arguments passed by position and with arguments passed by name.</span></span> <span data-ttu-id="fda79-122">프로시저에는 두 가지 선택적 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="fda79-122">The procedure has two optional parameters.</span></span>  
  
 [!code-vb[VbVbalrKeywords#21](../../../visual-basic/language-reference/codesnippet/VisualBasic/optional_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="fda79-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fda79-123">See Also</span></span>  
 [<span data-ttu-id="fda79-124">매개 변수 목록</span><span class="sxs-lookup"><span data-stu-id="fda79-124">Parameter List</span></span>](../../../visual-basic/language-reference/statements/parameter-list.md)  
 [<span data-ttu-id="fda79-125">선택적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="fda79-125">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)  
 [<span data-ttu-id="fda79-126">키워드</span><span class="sxs-lookup"><span data-stu-id="fda79-126">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
