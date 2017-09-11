---
title: "AddressOf 연산자 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- AddressOf
- vb.AddressOf
dev_langs:
- VB
helpviewer_keywords:
- AddressOf operator
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
caps.latest.revision: 11
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
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: e29b7ae2a6f6040cfc8c6e0cd0c9eb055a6694e9
ms.contentlocale: ko-kr
ms.lasthandoff: 05/23/2017

---
# <a name="addressof-operator-visual-basic"></a><span data-ttu-id="54993-102">AddressOf 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="54993-102">AddressOf Operator (Visual Basic)</span></span>
<span data-ttu-id="54993-103">특정 절차를 참조 하는 프로시저 대리자 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="54993-103">Creates a procedure delegate instance that references the specific procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54993-104">구문</span><span class="sxs-lookup"><span data-stu-id="54993-104">Syntax</span></span>  
  
```  
AddressOf procedurename  
```  
  
## <a name="parts"></a><span data-ttu-id="54993-105">요소</span><span class="sxs-lookup"><span data-stu-id="54993-105">Parts</span></span>  
 `procedurename`  
 <span data-ttu-id="54993-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="54993-106">Required.</span></span> <span data-ttu-id="54993-107">새로 만든된 프로시저 대리자가 참조 하는 절차를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="54993-107">Specifies the procedure to be referenced by the newly created procedure delegate.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54993-108">설명</span><span class="sxs-lookup"><span data-stu-id="54993-108">Remarks</span></span>  
 <span data-ttu-id="54993-109">`AddressOf` 연산자는 함수 대리자에 지정 된 함수를 가리키는 만듭니다 `procedurename`합니다.</span><span class="sxs-lookup"><span data-stu-id="54993-109">The `AddressOf` operator creates a function delegate that points to the function specified by `procedurename`.</span></span> <span data-ttu-id="54993-110">지정 된 프로시저를 때 인스턴스 메서드는 함수 대리자는 인스턴스와 메서드를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="54993-110">When the specified procedure is an instance method then the function delegate refers to both the instance and the method.</span></span> <span data-ttu-id="54993-111">그런 다음 함수 대리자가 호출 되 면 지정 된 인스턴스의 지정된 된 메서드 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="54993-111">Then, when the function delegate is invoked the specified method of the specified instance is called.</span></span>  
  
 <span data-ttu-id="54993-112">`AddressOf` 는 대리자 생성자의 피연산자와 연산자를 사용할 수 있습니다 또는 컴파일러는 대리자의 형식을 결정 하는 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54993-112">The `AddressOf` operator can be used as the operand of a delegate constructor or it can be used in a context in which the type of the delegate can be determined by the compiler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54993-113">예제</span><span class="sxs-lookup"><span data-stu-id="54993-113">Example</span></span>  
 <span data-ttu-id="54993-114">사용 하 여이 예제는 `AddressOf` 처리 하는 대리자를 지정 하는 연산자는 `Click` 단추의 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="54993-114">This example uses the `AddressOf` operator to designate a delegate to handle the `Click` event of a button.</span></span>  
  
 <span data-ttu-id="54993-115">[!code-vb[VbVbalrDelegates #&8;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="54993-115">[!code-vb[VbVbalrDelegates#8](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_1.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="54993-116">예제</span><span class="sxs-lookup"><span data-stu-id="54993-116">Example</span></span>  
 <span data-ttu-id="54993-117">다음 예제에서는 `AddressOf` 연산자를 사용 하는 스레드에 대 한 시작 함수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="54993-117">The following example uses the `AddressOf` operator to designate the startup function for a thread.</span></span>  
  
 <span data-ttu-id="54993-118">[!code-vb[VbVbalrDelegates #&9;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="54993-118">[!code-vb[VbVbalrDelegates#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54993-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="54993-119">See Also</span></span>  
 <span data-ttu-id="54993-120">[Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md) </span><span class="sxs-lookup"><span data-stu-id="54993-120">[Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) </span></span>  
<span data-ttu-id="54993-121"> [Function 문](../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="54993-121"> [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="54993-122"> [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="54993-122"> [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="54993-123"> [대리자](../../../visual-basic/programming-guide/language-features/delegates/index.md)</span><span class="sxs-lookup"><span data-stu-id="54993-123"> [Delegates](../../../visual-basic/programming-guide/language-features/delegates/index.md)</span></span>

