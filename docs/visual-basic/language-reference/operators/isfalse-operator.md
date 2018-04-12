---
title: IsFalse 연산자(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d85fc51a75f82c65cf226b8239a8eee6585bd18a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="isfalse-operator-visual-basic"></a><span data-ttu-id="7566b-102">IsFalse 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7566b-102">IsFalse Operator (Visual Basic)</span></span>
<span data-ttu-id="7566b-103">식이 인지 결정 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="7566b-103">Determines whether an expression is `False`.</span></span>  
  
 <span data-ttu-id="7566b-104">호출할 수 없습니다 `IsFalse` 명시적으로 코드 하지만 Visual Basic에서 컴파일러 있습니다 사용할에서 코드를 생성할 `AndAlso` 절.</span><span class="sxs-lookup"><span data-stu-id="7566b-104">You cannot call `IsFalse` explicitly in your code, but the Visual Basic compiler can use it to generate code from `AndAlso` clauses.</span></span> <span data-ttu-id="7566b-105">클래스 또는 구조체 정의 다음에 해당 형식의 변수를 사용 하는 경우는 `AndAlso` 정의 해야 절 `IsFalse` 해당 클래스 또는 구조체에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="7566b-105">If you define a class or structure and then use a variable of that type in an `AndAlso` clause, you must define `IsFalse` on that class or structure.</span></span>  
  
 <span data-ttu-id="7566b-106">컴파일러 있다고 간주는 `IsFalse` 및 `IsTrue` 으로 연산자는 *일치 하는 쌍*합니다.</span><span class="sxs-lookup"><span data-stu-id="7566b-106">The compiler considers the `IsFalse` and `IsTrue` operators as a *matched pair*.</span></span> <span data-ttu-id="7566b-107">이 둘 중 하나를 정의 하는 경우도 정의 해야 다른 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="7566b-107">This means that if you define one of them, you must also define the other one.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7566b-108">`IsFalse` 연산자 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할의 동작에 해당 클래스 또는 구조체의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7566b-108">The `IsFalse` operator can be *overloaded*, which means that a class or structure can redefine its behavior when its operand has the type of that class or structure.</span></span> <span data-ttu-id="7566b-109">이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7566b-109">If your code uses this operator on such a class or structure, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="7566b-110">자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7566b-110">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7566b-111">예제</span><span class="sxs-lookup"><span data-stu-id="7566b-111">Example</span></span>  
 <span data-ttu-id="7566b-112">다음 코드 예제에 대 한 정의 포함 하는 구조체의 개요를 정의 고 `IsFalse` 및 `IsTrue` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="7566b-112">The following code example defines the outline of a structure that includes definitions for the `IsFalse` and `IsTrue` operators.</span></span>  
  
 [!code-vb[VbVbalrOperators#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/isfalse-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7566b-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7566b-113">See Also</span></span>  
 [<span data-ttu-id="7566b-114">IsTrue 연산자</span><span class="sxs-lookup"><span data-stu-id="7566b-114">IsTrue Operator</span></span>](../../../visual-basic/language-reference/operators/istrue-operator.md)  
 [<span data-ttu-id="7566b-115">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="7566b-115">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="7566b-116">AndAlso 연산자</span><span class="sxs-lookup"><span data-stu-id="7566b-116">AndAlso Operator</span></span>](../../../visual-basic/language-reference/operators/andalso-operator.md)
