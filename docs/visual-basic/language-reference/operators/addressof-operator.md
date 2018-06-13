---
title: AddressOf 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
ms.openlocfilehash: 7c229c32a3b295b4dbfe50ca2abc60d4ad5f2145
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33597789"
---
# <a name="addressof-operator-visual-basic"></a><span data-ttu-id="0da2b-102">AddressOf 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0da2b-102">AddressOf Operator (Visual Basic)</span></span>
<span data-ttu-id="0da2b-103">특정 프로시저를 참조 하는 프로시저 대리자 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0da2b-103">Creates a procedure delegate instance that references the specific procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0da2b-104">구문</span><span class="sxs-lookup"><span data-stu-id="0da2b-104">Syntax</span></span>  
  
```  
AddressOf procedurename  
```  
  
## <a name="parts"></a><span data-ttu-id="0da2b-105">요소</span><span class="sxs-lookup"><span data-stu-id="0da2b-105">Parts</span></span>  
 `procedurename`  
 <span data-ttu-id="0da2b-106">필수.</span><span class="sxs-lookup"><span data-stu-id="0da2b-106">Required.</span></span> <span data-ttu-id="0da2b-107">새로 만든된 프로시저 대리자가 참조 하는 절차를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0da2b-107">Specifies the procedure to be referenced by the newly created procedure delegate.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0da2b-108">설명</span><span class="sxs-lookup"><span data-stu-id="0da2b-108">Remarks</span></span>  
 <span data-ttu-id="0da2b-109">`AddressOf` 연산자에 지정 된 함수를 가리키는 함수 대리자를 만듭니다. `procedurename`합니다.</span><span class="sxs-lookup"><span data-stu-id="0da2b-109">The `AddressOf` operator creates a function delegate that points to the function specified by `procedurename`.</span></span> <span data-ttu-id="0da2b-110">지정한 프로시저 경우 인스턴스 메서드 이면 함수 대리자는 인스턴스와 메서드를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="0da2b-110">When the specified procedure is an instance method then the function delegate refers to both the instance and the method.</span></span> <span data-ttu-id="0da2b-111">그런 다음 함수 대리자를 호출 하면 지정 된 인스턴스의 지정된 된 메서드 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0da2b-111">Then, when the function delegate is invoked the specified method of the specified instance is called.</span></span>  
  
 <span data-ttu-id="0da2b-112">`AddressOf` 연산자는 대리자 생성자의 피연산자로 사용할 수 있습니다 또는 컴파일러는 대리자의 형식을 결정 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0da2b-112">The `AddressOf` operator can be used as the operand of a delegate constructor or it can be used in a context in which the type of the delegate can be determined by the compiler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0da2b-113">예제</span><span class="sxs-lookup"><span data-stu-id="0da2b-113">Example</span></span>  
 <span data-ttu-id="0da2b-114">사용 하 여이 예제는 `AddressOf` 처리 하는 대리자를 지정 하는 연산자는 `Click` 단추 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="0da2b-114">This example uses the `AddressOf` operator to designate a delegate to handle the `Click` event of a button.</span></span>  
  
 [!code-vb[VbVbalrDelegates#8](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="0da2b-115">예제</span><span class="sxs-lookup"><span data-stu-id="0da2b-115">Example</span></span>  
 <span data-ttu-id="0da2b-116">다음 예제에서는 `AddressOf` 스레드에 대 한 시작 함수를 지정 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="0da2b-116">The following example uses the `AddressOf` operator to designate the startup function for a thread.</span></span>  
  
 [!code-vb[VbVbalrDelegates#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="0da2b-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0da2b-117">See Also</span></span>  
 [<span data-ttu-id="0da2b-118">Declare 문</span><span class="sxs-lookup"><span data-stu-id="0da2b-118">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [<span data-ttu-id="0da2b-119">Function 문</span><span class="sxs-lookup"><span data-stu-id="0da2b-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="0da2b-120">Sub 문</span><span class="sxs-lookup"><span data-stu-id="0da2b-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="0da2b-121">대리자</span><span class="sxs-lookup"><span data-stu-id="0da2b-121">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
