---
title: Narrowing(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.narrowing
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Narrowing keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: a207ee91-aca4-4771-b4e2-713f029bf2bb
ms.openlocfilehash: 54a18d0cc10e42829b48b0ef75bb77ab0d47b45f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33597460"
---
# <a name="narrowing-visual-basic"></a><span data-ttu-id="f68de-102">Narrowing(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f68de-102">Narrowing (Visual Basic)</span></span>
<span data-ttu-id="f68de-103">나타냅니다 변환 연산자 (`CType`) 클래스 또는 구조체를 원래 클래스 또는 구조체의 가능한 값의 일부를 저장 하지 않을 수 있는 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f68de-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that might not be able to hold some of the possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-narrowing-keyword"></a><span data-ttu-id="f68de-104">축소 키워드와 함께 변환</span><span class="sxs-lookup"><span data-stu-id="f68de-104">Converting with the Narrowing Keyword</span></span>  
 <span data-ttu-id="f68de-105">변환 프로시저를 지정 해야 `Public Shared` 외에 `Narrowing`합니다.</span><span class="sxs-lookup"><span data-stu-id="f68de-105">The conversion procedure must specify `Public Shared` in addition to `Narrowing`.</span></span>  
  
 <span data-ttu-id="f68de-106">축소 변환 않는 항상 실행 시 성공 및 실패 하거나 하 데이터 손실이 발생할 합니다.</span><span class="sxs-lookup"><span data-stu-id="f68de-106">Narrowing conversions do not always succeed at run time, and can fail or incur data loss.</span></span> <span data-ttu-id="f68de-107">예로 `Long` 를 `Integer`, `String` 를 `Date`, 파생된 형식에 기본 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f68de-107">Examples are `Long` to `Integer`, `String` to `Date`, and a base type to a derived type.</span></span> <span data-ttu-id="f68de-108">기본 형식이 파생 된 형식의 모든 멤버를 포함 하지 않을 수 있고 파생 형식의 인스턴스를 따라서는 축소이 마지막 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f68de-108">This last conversion is narrowing because the base type might not contain all the members of the derived type and thus is not an instance of the derived type.</span></span>  
  
 <span data-ttu-id="f68de-109">경우 `Option Strict` 은 `On`, 사용 하는 코드가 사용 해야 `CType` 모든 축소 변환에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="f68de-109">If `Option Strict` is `On`, the consuming code must use `CType` for all narrowing conversions.</span></span>  
  
 <span data-ttu-id="f68de-110">`Narrowing` 키워드는이 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f68de-110">The `Narrowing` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="f68de-111">Operator 문</span><span class="sxs-lookup"><span data-stu-id="f68de-111">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="f68de-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f68de-112">See Also</span></span>  
 [<span data-ttu-id="f68de-113">Operator 문</span><span class="sxs-lookup"><span data-stu-id="f68de-113">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="f68de-114">확장</span><span class="sxs-lookup"><span data-stu-id="f68de-114">Widening</span></span>](../../../visual-basic/language-reference/modifiers/widening.md)  
 [<span data-ttu-id="f68de-115">확대 변환과 축소 변환</span><span class="sxs-lookup"><span data-stu-id="f68de-115">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="f68de-116">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="f68de-116">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="f68de-117">CType 함수</span><span class="sxs-lookup"><span data-stu-id="f68de-117">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)  
 [<span data-ttu-id="f68de-118">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="f68de-118">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
