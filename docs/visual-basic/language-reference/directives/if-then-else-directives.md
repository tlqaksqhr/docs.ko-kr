---
title: '#다음과 같은 경우... Then... #Else 지시문'
ms.date: 04/11/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 884c7ed6f0a346f2d35f01006cea23e47907d13f
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ifthenelse-directives"></a><span data-ttu-id="7bddc-102">#If...Then...#Else 지시문</span><span class="sxs-lookup"><span data-stu-id="7bddc-102">#If...Then...#Else Directives</span></span>
<span data-ttu-id="7bddc-103">Visual Basic 코드의 선택 된 블록을 조건부로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="7bddc-103">Conditionally compiles selected blocks of Visual Basic code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bddc-104">구문</span><span class="sxs-lookup"><span data-stu-id="7bddc-104">Syntax</span></span>  
  
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
  
## <a name="parts"></a><span data-ttu-id="7bddc-105">요소</span><span class="sxs-lookup"><span data-stu-id="7bddc-105">Parts</span></span>  
 `expression`  
 <span data-ttu-id="7bddc-106">에 필요한 `#If` 및 `#ElseIf` 문, 선택적 다른 곳입니다.</span><span class="sxs-lookup"><span data-stu-id="7bddc-106">Required for `#If` and `#ElseIf` statements, optional elsewhere.</span></span> <span data-ttu-id="7bddc-107">조건부 컴파일러 상수, 리터럴 및 연산자 계산 되는 하나 이상의 구성 하는 모든 식, `True` 또는 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="7bddc-107">Any expression, consisting exclusively of one or more conditional compiler constants, literals, and operators, that evaluates to `True` or `False`.</span></span>  
  
 `statements`  
 <span data-ttu-id="7bddc-108">에 필요한 `#If` 문 블록에서는 선택적 다른 곳입니다.</span><span class="sxs-lookup"><span data-stu-id="7bddc-108">Required for `#If` statement block, optional elsewhere.</span></span> <span data-ttu-id="7bddc-109">Visual Basic 프로그램 줄 또는 컴파일러 지시문과 관련 된 식은로 평가 되 면 컴파일되는 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="7bddc-109">Visual Basic program lines or compiler directives that are compiled if the associated expression evaluates to `True`.</span></span>  
  
 `#End If`  
 <span data-ttu-id="7bddc-110">종료는 `#If` 문 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="7bddc-110">Terminates the `#If` statement block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7bddc-111">설명</span><span class="sxs-lookup"><span data-stu-id="7bddc-111">Remarks</span></span>  
 <span data-ttu-id="7bddc-112">동작은 화면에는 `#If...Then...#Else` 지시문 동일 하 게의 표시는 `If...Then...Else` 문.</span><span class="sxs-lookup"><span data-stu-id="7bddc-112">On the surface, the behavior of the `#If...Then...#Else` directives appears the same as that of the `If...Then...Else` statements.</span></span> <span data-ttu-id="7bddc-113">그러나는 `#If...Then...#Else` 지시문은 컴파일러에 의해 컴파일되는 내용을 반면 평가 `If...Then...Else` 문 실행 시 조건을 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bddc-113">However, the `#If...Then...#Else` directives evaluate what is compiled by the compiler, whereas the `If...Then...Else` statements evaluate conditions at run time.</span></span>  
  
 <span data-ttu-id="7bddc-114">조건부 컴파일 여러 플랫폼에 대해 동일한 프로그램을 컴파일하는 데 주로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bddc-114">Conditional compilation is typically used to compile the same program for different platforms.</span></span> <span data-ttu-id="7bddc-115">방지 하기 위해 사용 되는 실행 파일에 표시 되는 코드를 디버깅 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bddc-115">It is also used to prevent debugging code from appearing in an executable file.</span></span> <span data-ttu-id="7bddc-116">조건부 컴파일 타임에 제외 된 코드에서에서 완전히 생략 최종 실행 파일 때문에 크기 또는 성능에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bddc-116">Code excluded during conditional compilation is completely omitted from the final executable file, so it has no effect on size or performance.</span></span>  
  
 <span data-ttu-id="7bddc-117">모든 평가 결과 상관 없이 모든 식을 사용 하 여 평가 됩니다 `Option Compare Binary`합니다.</span><span class="sxs-lookup"><span data-stu-id="7bddc-117">Regardless of the outcome of any evaluation, all expressions are evaluated using `Option Compare Binary`.</span></span> <span data-ttu-id="7bddc-118">`Option Compare` 문은 식에 영향을 주지 않습니다 `#If` 및 `#ElseIf` 문.</span><span class="sxs-lookup"><span data-stu-id="7bddc-118">The `Option Compare` statement does not affect expressions in `#If` and `#ElseIf` statements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7bddc-119">한 줄 형식이 없으므로 `#If`, `#Else`, `#ElseIf`, 및 `#End If` 지시문 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bddc-119">No single-line form of the `#If`, `#Else`, `#ElseIf`, and `#End If` directives exists.</span></span> <span data-ttu-id="7bddc-120">다른 코드 지시문와 같은 줄에 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bddc-120">No other code can appear on the same line as any of the directives.</span></span> 

<span data-ttu-id="7bddc-121">조건부 컴파일 블록 내에서 문을 완료 논리 문 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bddc-121">The statements within a conditional compilation block must be complete logical statements.</span></span> <span data-ttu-id="7bddc-122">예를 들어 함수의 특성만 조건에 따라 컴파일할 수 없습니다 하지만 조건에 따라 특성 함께 함수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bddc-122">For example, you cannot conditionally compile only the attributes of a function, but you can conditionally declare the function along with its attributes:</span></span>

```vb
   #If DEBUG Then
   <WebMethod()>
   Public Function SomeFunction() As String
   #Else
   <WebMethod(CacheDuration:=86400)>
   Public Function SomeFunction() As String
   #End If
```

## <a name="example"></a><span data-ttu-id="7bddc-123">예제</span><span class="sxs-lookup"><span data-stu-id="7bddc-123">Example</span></span>
 <span data-ttu-id="7bddc-124">사용 하 여이 예제는 `#If...Then...#Else` 구문을 특정 문의 컴파일 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bddc-124">This example uses the `#If...Then...#Else` construct to determine whether to compile certain statements.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#1](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/if-then-else-directives_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7bddc-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7bddc-125">See Also</span></span>  
[<span data-ttu-id="7bddc-126">#Const 지시문</span><span class="sxs-lookup"><span data-stu-id="7bddc-126">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)  
[<span data-ttu-id="7bddc-127">If...Then...Else 문</span><span class="sxs-lookup"><span data-stu-id="7bddc-127">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
<span data-ttu-id="7bddc-128">[조건부 컴파일](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md) </span><span class="sxs-lookup"><span data-stu-id="7bddc-128">[Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md) </span></span>  
<xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>   


