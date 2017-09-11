---
title: "방법: 새 변수 (Visual Basic) 만들기 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Dim statement
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
caps.latest.revision: 29
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
ms.openlocfilehash: 3b5aa4e5e0b84f41ac3df73bc70d8402d10b21a2
ms.contentlocale: ko-kr
ms.lasthandoff: 05/23/2017

---
# <a name="how-to-create-a-new-variable-visual-basic"></a><span data-ttu-id="7d82f-102">방법: 새 변수 만들기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d82f-102">How to: Create a New Variable (Visual Basic)</span></span>
<span data-ttu-id="7d82f-103">사용 하 여 변수를 만들면는 [Dim](../../../../visual-basic/language-reference/statements/dim-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7d82f-103">You create a variable with a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
### <a name="to-create-a-new-variable"></a><span data-ttu-id="7d82f-104">새 변수를 만들려면</span><span class="sxs-lookup"><span data-stu-id="7d82f-104">To create a new variable</span></span>  
  
1.  <span data-ttu-id="7d82f-105">변수를 선언 하는 `Dim` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="7d82f-105">Declare the variable in a `Dim` statement.</span></span>  
  
    ```  
    Dim newCustomer  
    ```  
  
2.  <span data-ttu-id="7d82f-106">와 같은 변수 특징에 대 한 사양이 포함 [개인](../../../../visual-basic/language-reference/modifiers/private.md), [정적](../../../../visual-basic/language-reference/modifiers/static.md), [그림자](../../../../visual-basic/language-reference/modifiers/shadows.md), 또는 [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7d82f-106">Include specifications for the variable's characteristics, such as [Private](../../../../visual-basic/language-reference/modifiers/private.md), [Static](../../../../visual-basic/language-reference/modifiers/static.md), [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md), or [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md).</span></span> <span data-ttu-id="7d82f-107">자세한 내용은 참조 [선언 요소의 특징](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7d82f-107">For more information, see [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md).</span></span>  
  
    ```  
    Public Static newCustomer  
    ```  
  
     <span data-ttu-id="7d82f-108">원하지 않는 `Dim` 키워드는 선언에 다른 키워드를 사용 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="7d82f-108">You do not need the `Dim` keyword if you use other keywords in the declaration.</span></span>  
  
3.  <span data-ttu-id="7d82f-109">따라야 하는 변수 이름 사양에 따라 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 규칙 및 규칙을 따르십시오.</span><span class="sxs-lookup"><span data-stu-id="7d82f-109">Follow the specifications with the variable's name, which must follow [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] rules and conventions.</span></span> <span data-ttu-id="7d82f-110">자세한 내용은 참조 [선언 요소 이름](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7d82f-110">For more information, see [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
    ```  
    Public Static newCustomer  
    ```  
  
4.  <span data-ttu-id="7d82f-111">이름 뒤에 [으로](../../../../visual-basic/language-reference/statements/as-clause.md) 변수의 데이터 형식을 지정 하는 절.</span><span class="sxs-lookup"><span data-stu-id="7d82f-111">Follow the name with the [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause to specify the variable's data type.</span></span>  
  
    ```  
    Public Static newCustomer As Customer  
    ```  
  
     <span data-ttu-id="7d82f-112">데이터 형식을 지정 하지 않으면 기본값 사용: `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="7d82f-112">If you do not specify the data type, it uses the default: `Object`.</span></span>  
  
5.  <span data-ttu-id="7d82f-113">에 따라는 `As` 등호로 절 (`=`) 등호 변수의 초기 값을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="7d82f-113">Follow the `As` clause with an equal sign (`=`) and follow the equal sign with the variable's initial value.</span></span>  
  
     [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="7d82f-114">실행 될 때마다 지정된 된 값은 변수에 할당 된 `Dim` 문.</span><span class="sxs-lookup"><span data-stu-id="7d82f-114"> assigns the specified value to the variable every time it runs the `Dim` statement.</span></span> <span data-ttu-id="7d82f-115">초기 값을 지정 하지 않으면 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 변수의 데이터 형식에 대 한 초기 기본값을 포함 하는 코드를 처음 실행 될 때 할당는 `Dim` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="7d82f-115">If you do not specify an initial value, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] assigns the default initial value for the variable's data type when it first enters the code that contains the `Dim` statement.</span></span>  
  
     <span data-ttu-id="7d82f-116">변수 참조 형식인 경우를 포함 하 여 해당 클래스의 인스턴스를 만들 수 있습니다는 [New 연산자](../../../../visual-basic/language-reference/operators/new-operator.md) 의 키워드는 `As` 절.</span><span class="sxs-lookup"><span data-stu-id="7d82f-116">If the variable is a reference type, you can create an instance of its class by including the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword in the `As` clause.</span></span> <span data-ttu-id="7d82f-117">사용 하지 않는 경우 `New`, 변수의 초기 값은 [Nothing](../../../../visual-basic/language-reference/nothing.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7d82f-117">If you do not use `New`, the initial value of the variable is [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
    ```  
    Public Static newCustomer As New Customer  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7d82f-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7d82f-118">See Also</span></span>  
 <span data-ttu-id="7d82f-119">[변수](../../../../visual-basic/programming-guide/language-features/variables/index.md) </span><span class="sxs-lookup"><span data-stu-id="7d82f-119">[Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md) </span></span>  
<span data-ttu-id="7d82f-120"> [변수 선언](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="7d82f-120"> [Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span></span>  
<span data-ttu-id="7d82f-121"> [선언된 요소 이름](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span><span class="sxs-lookup"><span data-stu-id="7d82f-121"> [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md) </span></span>  
<span data-ttu-id="7d82f-122"> [선언된 요소의 특징](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span><span class="sxs-lookup"><span data-stu-id="7d82f-122"> [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span></span>  
<span data-ttu-id="7d82f-123"> [값 형식과 참조 형식](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="7d82f-123"> [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md) </span></span>  
<span data-ttu-id="7d82f-124"> [문](../../../../visual-basic/language-reference/statements/index.md) </span><span class="sxs-lookup"><span data-stu-id="7d82f-124"> [Statements](../../../../visual-basic/language-reference/statements/index.md) </span></span>  
<span data-ttu-id="7d82f-125"> [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span><span class="sxs-lookup"><span data-stu-id="7d82f-125"> [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span></span>  
<span data-ttu-id="7d82f-126"> [Option Infer 문](../../../../visual-basic/language-reference/statements/option-infer-statement.md)</span><span class="sxs-lookup"><span data-stu-id="7d82f-126"> [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md)</span></span>

