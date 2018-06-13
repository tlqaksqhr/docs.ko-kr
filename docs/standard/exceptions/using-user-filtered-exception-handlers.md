---
title: 사용자 필터 예외 처리기 사용
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- user-filtered exceptions
- exceptions, user-filtered
ms.assetid: aa80d155-060d-41b4-a636-1ceb424afee8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e72f87bd4a33491df46576629971c60af4630ce3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571893"
---
# <a name="using-user-filtered-exception-handlers"></a><span data-ttu-id="c0d5f-102">사용자 필터 예외 처리기 사용</span><span class="sxs-lookup"><span data-stu-id="c0d5f-102">Using User-Filtered Exception Handlers</span></span>
<span data-ttu-id="c0d5f-103">현재 Visual Basic에서는 사용자 필터 예외를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d5f-103">Currently, Visual Basic supports user-filtered exceptions.</span></span> <span data-ttu-id="c0d5f-104">사용자 필터 예외 처리기는 예외에 대해 정의한 요구 사항을 기반으로 하여 예외를 catch하고 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d5f-104">User-filtered exception handlers catch and handle exceptions based on requirements you define for the exception.</span></span> <span data-ttu-id="c0d5f-105">이러한 처리기는 **Catch** 문을 **When** 키워드와 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d5f-105">These handlers use the **Catch** statement with the **When** keyword.</span></span>  
  
 <span data-ttu-id="c0d5f-106">이 기법은 특정 예외 개체가 여러 오류에 해당하는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d5f-106">This technique is useful when a particular exception object corresponds to multiple errors.</span></span> <span data-ttu-id="c0d5f-107">이 경우 개체는 일반적으로 오류와 관련된 특정 오류 코드를 포함하는 속성을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d5f-107">In this case, the object typically has a property that contains the specific error code associated with the error.</span></span> <span data-ttu-id="c0d5f-108">식에서 해당 오류 코드 속성을 사용하여 **Catch** 절에서 처리하려는 특정 오류만 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d5f-108">You can use the error code property in the expression to select only the particular error you want to handle in that **Catch** clause.</span></span>  
  
 <span data-ttu-id="c0d5f-109">다음 Visual Basic 예제에서는 **Catch/When** 문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c0d5f-109">The following Visual Basic example illustrates the **Catch/When** statement.</span></span>  
  
```  
Try  
      'Try statements.  
   Catch When Err = VBErr_ClassLoadException  
      'Catch statements.  
End Try  
```  
  
 <span data-ttu-id="c0d5f-110">사용자 필터 절의 식에는 어떤 제한도 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d5f-110">The expression of the user-filtered clause is not restricted in any way.</span></span> <span data-ttu-id="c0d5f-111">사용자 필터 식을 실행하는 중에 예외가 발생하면 예외는 무시되고 필터 식이 false로 계산된 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0d5f-111">If an exception occurs during execution of the user-filtered expression, that exception is discarded and the filter expression is considered to have evaluated to false.</span></span> <span data-ttu-id="c0d5f-112">이 경우 공용 언어 런타임은 현재 예외에 대한 처리기를 계속 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d5f-112">In this case, the common language runtime continues the search for a handler for the current exception.</span></span>  
  
## <a name="combining-the-specific-exception-and-the-user-filtered-clauses"></a><span data-ttu-id="c0d5f-113">특정 예외 및 사용자 필터 절 조합</span><span class="sxs-lookup"><span data-stu-id="c0d5f-113">Combining the Specific Exception and the User-Filtered Clauses</span></span>  
 <span data-ttu-id="c0d5f-114">Catch 문은 특정 예외와 사용자 필터 절을 모두 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d5f-114">A catch statement can contain both the specific exception and the user-filtered clauses.</span></span> <span data-ttu-id="c0d5f-115">런타임은 특정 예외를 먼저 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d5f-115">The runtime tests the specific exception first.</span></span> <span data-ttu-id="c0d5f-116">특정 예외가 성공하면 런타임은 사용자 필터를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c0d5f-116">If the specific exception succeeds, the runtime executes the user filter.</span></span> <span data-ttu-id="c0d5f-117">일반 필터에는 클래스 필터에 선언된 변수에 대한 참조가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d5f-117">The generic filter can contain a reference to the variable declared in the class filter.</span></span> <span data-ttu-id="c0d5f-118">두 필터 절의 순서는 바꿀 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c0d5f-118">Note that the order of the two filter clauses cannot be reversed.</span></span>  
  
 <span data-ttu-id="c0d5f-119">다음 Visual Basic 예제에서는 **When** 키워드를 사용하는 사용자 필터 절 뿐만 아니라 **Catch** 문의 특정 예외 `ClassLoadException`을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c0d5f-119">The following Visual Basic example shows the specific exception `ClassLoadException` in the **Catch** statement as well as the user-filtered clause using the **When** keyword.</span></span>  
  
```  
Try  
      'Try statements.  
   Catch cle As ClassLoadException When cle.IsRecoverable()  
      'Catch statements.  
End Try  
```  

## <a name="see-also"></a><span data-ttu-id="c0d5f-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c0d5f-120">See Also</span></span>
[<span data-ttu-id="c0d5f-121">예외</span><span class="sxs-lookup"><span data-stu-id="c0d5f-121">Exceptions</span></span>](index.md)
