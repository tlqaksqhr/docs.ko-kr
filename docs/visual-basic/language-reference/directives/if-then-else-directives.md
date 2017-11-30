---
title: "#<a name=\"ifthenelse-directives\"></a>다음과 같은 경우... Then... #Else 지시문"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.#EndIf
- '#End If'
- '#Then'
- '#ElseIf'
- vb.#ElseIf
- vb.#Else
- vb.#If
helpviewer_keywords:
- Visual Basic code, compiling
- '#If directive [Visual Basic]'
- conditional compilation [Visual Basic], directives
- '#End if directive [Visual Basic]'
- selective compiling
- else directive (#else)
- '#Else directive [Visual Basic]'
ms.assetid: 10bba104-e3fd-451b-b672-faa472530502
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 77757e441ae937aa86122f237e839d1005644409
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ifthenelse-directives"></a><span data-ttu-id="9e412-102">#If...Then...#Else 지시문</span><span class="sxs-lookup"><span data-stu-id="9e412-102">#If...Then...#Else Directives</span></span>
<span data-ttu-id="9e412-103">Visual Basic 코드의 선택 된 블록을 조건부로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="9e412-103">Conditionally compiles selected blocks of Visual Basic code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e412-104">구문</span><span class="sxs-lookup"><span data-stu-id="9e412-104">Syntax</span></span>  
  
```  
#If expression Then  
   statements  
[ #ElseIf expression Then  
   [ statements ]  
...  
#ElseIf expression Then  
   [ statements ] ]  
[ #Else  
   [ statements ] ]  
#End If  
```  
  
## <a name="parts"></a><span data-ttu-id="9e412-105">요소</span><span class="sxs-lookup"><span data-stu-id="9e412-105">Parts</span></span>  
 `expression`  
 <span data-ttu-id="9e412-106">에 필요한 `#If` 및 `#ElseIf` 문, 선택적 다른 곳입니다.</span><span class="sxs-lookup"><span data-stu-id="9e412-106">Required for `#If` and `#ElseIf` statements, optional elsewhere.</span></span> <span data-ttu-id="9e412-107">조건부 컴파일러 상수, 리터럴 및 연산자 계산 되는 하나 이상의 구성 하는 모든 식, `True` 또는 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="9e412-107">Any expression, consisting exclusively of one or more conditional compiler constants, literals, and operators, that evaluates to `True` or `False`.</span></span>  
  
 `statements`  
 <span data-ttu-id="9e412-108">에 필요한 `#If` 문 블록에서는 선택적 다른 곳입니다.</span><span class="sxs-lookup"><span data-stu-id="9e412-108">Required for `#If` statement block, optional elsewhere.</span></span> <span data-ttu-id="9e412-109">Visual Basic 프로그램 줄 또는 컴파일러 지시문과 관련 된 식은로 평가 되 면 컴파일되는 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="9e412-109">Visual Basic program lines or compiler directives that are compiled if the associated expression evaluates to `True`.</span></span>  
  
 `#End If`  
 <span data-ttu-id="9e412-110">종료는 `#If` 문 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="9e412-110">Terminates the `#If` statement block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e412-111">설명</span><span class="sxs-lookup"><span data-stu-id="9e412-111">Remarks</span></span>  
 <span data-ttu-id="9e412-112">동작은 화면에는 `#If...Then...#Else` 지시문 동일 하 게의 표시는 `If...Then...Else` 문.</span><span class="sxs-lookup"><span data-stu-id="9e412-112">On the surface, the behavior of the `#If...Then...#Else` directives appears the same as that of the `If...Then...Else` statements.</span></span> <span data-ttu-id="9e412-113">그러나는 `#If...Then...#Else` 지시문은 컴파일러에 의해 컴파일되는 내용을 반면 평가 `If...Then...Else` 문 실행 시 조건을 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e412-113">However, the `#If...Then...#Else` directives evaluate what is compiled by the compiler, whereas the `If...Then...Else` statements evaluate conditions at run time.</span></span>  
  
 <span data-ttu-id="9e412-114">조건부 컴파일 여러 플랫폼에 대해 동일한 프로그램을 컴파일하는 데 주로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e412-114">Conditional compilation is typically used to compile the same program for different platforms.</span></span> <span data-ttu-id="9e412-115">방지 하기 위해 사용 되는 실행 파일에 표시 되는 코드를 디버깅 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e412-115">It is also used to prevent debugging code from appearing in an executable file.</span></span> <span data-ttu-id="9e412-116">조건부 컴파일 타임에 제외 된 코드에서에서 완전히 생략 최종 실행 파일 때문에 크기 또는 성능에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e412-116">Code excluded during conditional compilation is completely omitted from the final executable file, so it has no effect on size or performance.</span></span>  
  
 <span data-ttu-id="9e412-117">모든 평가 결과 상관 없이 모든 식을 사용 하 여 평가 됩니다 `Option Compare Binary`합니다.</span><span class="sxs-lookup"><span data-stu-id="9e412-117">Regardless of the outcome of any evaluation, all expressions are evaluated using `Option Compare Binary`.</span></span> <span data-ttu-id="9e412-118">`Option Compare` 문은 식에 영향을 주지 않습니다 `#If` 및 `#ElseIf` 문.</span><span class="sxs-lookup"><span data-stu-id="9e412-118">The `Option Compare` statement does not affect expressions in `#If` and `#ElseIf` statements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e412-119">한 줄 형식이 없으므로 `#If`, `#Else`, `#ElseIf`, 및 `#End If` 지시문 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e412-119">No single-line form of the `#If`, `#Else`, `#ElseIf`, and `#End If` directives exists.</span></span> <span data-ttu-id="9e412-120">다른 코드 지시문와 같은 줄에 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e412-120">No other code can appear on the same line as any of the directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e412-121">예제</span><span class="sxs-lookup"><span data-stu-id="9e412-121">Example</span></span>  
 <span data-ttu-id="9e412-122">사용 하 여이 예제는 `#If...Then...#Else` 구문을 특정 문의 컴파일 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e412-122">This example uses the `#If...Then...#Else` construct to determine whether to compile certain statements.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#1](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/if-then-else-directives_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="9e412-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9e412-123">See Also</span></span>  
 [<span data-ttu-id="9e412-124">#Const 지시문</span><span class="sxs-lookup"><span data-stu-id="9e412-124">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)  
 [<span data-ttu-id="9e412-125">If...Then...Else 문</span><span class="sxs-lookup"><span data-stu-id="9e412-125">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [<span data-ttu-id="9e412-126">조건부 컴파일</span><span class="sxs-lookup"><span data-stu-id="9e412-126">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
