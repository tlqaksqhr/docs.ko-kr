---
title: "이 인수에서 형식 매개 변수의 데이터 형식을 유추할 수 없습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36644
- bc36647
- vbc36647
- vbc36644
helpviewer_keywords:
- BC36644
- BC36647
ms.assetid: 0e0050f2-2039-4311-b260-f0ebfde84189
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b290c25286dce2236823919e8287db9abefc0dd7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="data-types-of-the-type-parameters-cannot-be-inferred-from-these-arguments"></a><span data-ttu-id="41d37-102">이 인수에서 형식 매개 변수의 데이터 형식을 유추할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41d37-102">Data type(s) of the type parameter(s) cannot be inferred from these arguments</span></span>
<span data-ttu-id="41d37-103">이 인수에서 형식 매개 변수의 데이터 형식을 유추할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41d37-103">Data type(s) of the type parameter(s) cannot be inferred from these arguments.</span></span> <span data-ttu-id="41d37-104">데이터 형식을 명시적으로 지정하면 이 오류를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41d37-104">Specifying the data type(s) explicitly might correct this error.</span></span>  
  
 <span data-ttu-id="41d37-105">이 오류는 오버로드 확인에 실패한 경우에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="41d37-105">This error occurs when overload resolution has failed.</span></span> <span data-ttu-id="41d37-106">특정 오버로드 후보가 제거된 이유를 나타내는 하위 메시지로 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="41d37-106">It occurs as a subordinate message that states why a particular overload candidate has been eliminated.</span></span> <span data-ttu-id="41d37-107">오류 메시지에 설명을 컴파일러에서 형식 매개 변수의 데이터 형식의 찾을를 형식 유추를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41d37-107">The error message explains that the compiler cannot use type inference to find data types for the type parameters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="41d37-108">인수 지정이 옵션이 아닌 경우(예: 쿼리 식의 쿼리 연산자) 두 번째 문장 없이 오류 메시지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="41d37-108">When specifying arguments is not an option (for example, for query operators in query expressions), the error message appears without the second sentence.</span></span>  
  
 <span data-ttu-id="41d37-109">다음 코드에서는  오류를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="41d37-109">The following code demonstrates the error.</span></span>  
  
```vb  
Module Module1  
  
    Sub Main()  
  
        '' Not Valid.  
        'OverloadedGenericMethod("Hello", "World")  
  
    End Sub  
  
    Sub OverloadedGenericMethod(Of T)(ByVal x As String,   
                                      ByVal y As InterfaceExample(Of T))  
    End Sub  
  
    Sub OverloadedGenericMethod(Of T, R)(ByVal x As T,   
                                         ByVal y As InterfaceExample(Of R))  
    End Sub  
  
End Module  
  
Interface InterfaceExample(Of T)  
End Interface  
```  
  
 <span data-ttu-id="41d37-110">**오류 ID:** BC36647 및 BC36644</span><span class="sxs-lookup"><span data-stu-id="41d37-110">**Error ID:** BC36647 and BC36644</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="41d37-111">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="41d37-111">To correct this error</span></span>  
  
-   <span data-ttu-id="41d37-112">형식 유추를 사용하지 않고 형식 매개 변수에 대한 데이터 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41d37-112">You may be able to specify a data type for the type parameter or parameters instead of relying on type inference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41d37-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="41d37-113">See Also</span></span>  
 [<span data-ttu-id="41d37-114">완화된 대리자 변환</span><span class="sxs-lookup"><span data-stu-id="41d37-114">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)  
 [<span data-ttu-id="41d37-115">Visual Basic의 제네릭 프로시저</span><span class="sxs-lookup"><span data-stu-id="41d37-115">Generic Procedures in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)  
 [<span data-ttu-id="41d37-116">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="41d37-116">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
