---
title: "#<a name=\"const-directive\"></a>Const 지시문"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.#Const
- '#vb.Const'
- '#Const'
helpviewer_keywords:
- '#Const directive'
- conditional compilation [Visual Basic], directives
- Const directive (#Const)
- Visual Basic compiler, compiler directives
- constants [Visual Basic], Const directive
- constants [Visual Basic], declaring
- Const statement [Visual Basic], directive (#Const)
- 'declaring constants [Visual Basic], #const directive'
ms.assetid: 707669e5-23f9-4f17-8622-a0d534429386
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a6e162b01dc5c99fb7708337d259f9e66ddd6b64
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="const-directive"></a><span data-ttu-id="6ad8c-102">#Const 지시문</span><span class="sxs-lookup"><span data-stu-id="6ad8c-102">#Const Directive</span></span>
<span data-ttu-id="6ad8c-103">Visual basic의 조건부 컴파일러 상수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad8c-103">Defines conditional compiler constants for Visual Basic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ad8c-104">구문</span><span class="sxs-lookup"><span data-stu-id="6ad8c-104">Syntax</span></span>  
  
```  
#Const constname = expression  
```  
  
## <a name="parts"></a><span data-ttu-id="6ad8c-105">요소</span><span class="sxs-lookup"><span data-stu-id="6ad8c-105">Parts</span></span>  
 `constname`  
 <span data-ttu-id="6ad8c-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="6ad8c-106">Required.</span></span> <span data-ttu-id="6ad8c-107">정의 되는 상수의의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6ad8c-107">Name of the constant being defined.</span></span>  
  
 `expression`  
 <span data-ttu-id="6ad8c-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="6ad8c-108">Required.</span></span> <span data-ttu-id="6ad8c-109">리터럴, 다른 조건부 컴파일러 상수 또는 제외 하 고 임의로 또는 모두 산술 또는 논리 연산자를 포함 하는 `Is`합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad8c-109">Literal, other conditional compiler constant, or any combination that includes any or all arithmetic or logical operators except `Is`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ad8c-110">설명</span><span class="sxs-lookup"><span data-stu-id="6ad8c-110">Remarks</span></span>  
 <span data-ttu-id="6ad8c-111">조건부 컴파일러 상수는 항상 표시 되는 파일의 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="6ad8c-111">Conditional compiler constants are always private to the file in which they appear.</span></span> <span data-ttu-id="6ad8c-112">공용 컴파일러 상수를 사용 하 여 만들 수 없습니다는 `#Const` 지시문을 사용 하거나 사용자 인터페이스에서만 만들 수 있습니다;는 `/define` 컴파일러 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="6ad8c-112">You cannot create public compiler constants using the `#Const` directive; you can create them only in the user interface or with the `/define` compiler option.</span></span>  
  
 <span data-ttu-id="6ad8c-113">조건부 컴파일러 상수와 리터럴만 사용할 수 있습니다 `expression`합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad8c-113">You can use only conditional compiler constants and literals in `expression`.</span></span> <span data-ttu-id="6ad8c-114">로 정의 된 표준 상수를 사용 하 여 `Const` 하면 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad8c-114">Using a standard constant defined with `Const` causes an error.</span></span> <span data-ttu-id="6ad8c-115">반대로, 정의 된 상수를 사용할 수 있습니다는 `#Const` 조건부 컴파일에 대 한 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="6ad8c-115">Conversely, you can use constants defined with the `#Const` keyword only for conditional compilation.</span></span> <span data-ttu-id="6ad8c-116">상수를 정의의 값이 있을 경우에서 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad8c-116">Constants can also be undefined, in which case they have a value of `Nothing`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ad8c-117">예제</span><span class="sxs-lookup"><span data-stu-id="6ad8c-117">Example</span></span>  
 <span data-ttu-id="6ad8c-118">이 예제에서는 `#Const` 지시문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ad8c-118">This example uses the `#Const` directive.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#3](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/const-directive_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="6ad8c-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6ad8c-119">See Also</span></span>  
 [<span data-ttu-id="6ad8c-120">/define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6ad8c-120">/define (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/define.md)  
 [<span data-ttu-id="6ad8c-121">#If...Then...#Else 지시문</span><span class="sxs-lookup"><span data-stu-id="6ad8c-121">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="6ad8c-122">Const 문</span><span class="sxs-lookup"><span data-stu-id="6ad8c-122">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
 [<span data-ttu-id="6ad8c-123">조건부 컴파일</span><span class="sxs-lookup"><span data-stu-id="6ad8c-123">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 [<span data-ttu-id="6ad8c-124">If...Then...Else 문</span><span class="sxs-lookup"><span data-stu-id="6ad8c-124">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
