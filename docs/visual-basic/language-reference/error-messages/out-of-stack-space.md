---
title: "스택 공간이 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID28
dev_langs:
- VB
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
caps.latest.revision: 8
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
ms.openlocfilehash: 256ef0c7fcb3632e0c13d12737d438225343884f
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="out-of-stack-space-visual-basic"></a><span data-ttu-id="575c2-102">스택 공간이 부족합니다(Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="575c2-102">Out of stack space (Visual Basic)</span></span>
<span data-ttu-id="575c2-103">실행 중인 프로그램의 요구와 동적으로 확장 및 축소 하는 메모리의 작업 영역 않습니다.</span><span class="sxs-lookup"><span data-stu-id="575c2-103">The stack is a working area of memory that grows and shrinks dynamically with the demands of your executing program.</span></span> <span data-ttu-id="575c2-104">제한은 초과 했습니다.</span><span class="sxs-lookup"><span data-stu-id="575c2-104">Its limits have been exceeded.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="575c2-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="575c2-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="575c2-106">프로시저 너무 많이 중첩 되지 않은 것을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="575c2-106">Check that procedures are not nested too deeply.</span></span>  
  
2.  <span data-ttu-id="575c2-107">재귀 프로시저 올바르게 종료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="575c2-107">Make sure recursive procedures terminate properly.</span></span>  
  
3.  <span data-ttu-id="575c2-108">지역 변수 공간이 사용 가능한 것 보다 모듈 수준에서 일부 변수를 선언 해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="575c2-108">If local variables require more local variable space than is available, try declaring some variables at the module level.</span></span> <span data-ttu-id="575c2-109">또한 변수를 선언할 수 모든 절차에서 정적 앞는 `Property`, `Sub`, 또는 `Function` 키워드를 함께 `Static`합니다.</span><span class="sxs-lookup"><span data-stu-id="575c2-109">You can also declare all variables in the procedure static by preceding the `Property`, `Sub`, or `Function` keyword with `Static`.</span></span> <span data-ttu-id="575c2-110">또는 사용할 수는 `Static` 문을 프로시저 내에서 개별 정적 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="575c2-110">Or you can use the `Static` statement to declare individual static variables within procedures.</span></span>  
  
4.  <span data-ttu-id="575c2-111">고정 길이 문자열 가변 길이 문자열 보다 더 많은 스택 공간을 사용 하 여 다양 한 길이의 문자열로 고정 길이 문자열의 일부를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="575c2-111">Redefine some of your fixed-length strings as variable-length strings, as fixed-length strings use more stack space than variable-length strings.</span></span> <span data-ttu-id="575c2-112">또한 모듈 수준 스택 공간이 없는 필요 위치에서 문자열을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="575c2-112">You can also define the string at module level where it requires no stack space.</span></span>  
  
5.  <span data-ttu-id="575c2-113">수를 확인 하십시오 중첩 `DoEvents` 를 사용 하 여 함수 호출의 `Calls` 스택에 활성화 되어 있는 프로시저 보기 대화 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="575c2-113">Check the number of nested `DoEvents` function calls, by using the `Calls` dialog box to view which procedures are active on the stack.</span></span>  
  
6.  <span data-ttu-id="575c2-114">이미 스택에 이벤트 프로시저를 호출 하는 이벤트를 트리거하여 "이벤트 캐스케이딩"이 발생 하지 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="575c2-114">Make sure you did not cause an "event cascade" by triggering an event that calls an event procedure already on the stack.</span></span> <span data-ttu-id="575c2-115">이벤트 캐스케이딩은 종료 되지 않은 재귀 프로시저 호출과 유사 하지만 덜 확실 한 하 여 호출 되므로 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 코드에서 명시적으로 호출 하는 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="575c2-115">An event cascade is similar to an unterminated recursive procedure call, but it is less obvious, since the call is made by [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] rather than an explicit call in the code.</span></span> <span data-ttu-id="575c2-116">사용 된 `Calls`스택에 활성화 되어 있는 프로시저 보기 대화 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="575c2-116">Use the `Calls`dialog box to view which procedures are active on the stack.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="575c2-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="575c2-117">See Also</span></span>  
 [<span data-ttu-id="575c2-118">메모리 창</span><span class="sxs-lookup"><span data-stu-id="575c2-118">Memory Windows</span></span>](https://docs.microsoft.com/visualstudio/debugger/memory-windows)
