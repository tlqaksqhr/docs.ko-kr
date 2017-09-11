---
title: "Visual Basic의 변수 문제 해결 | Microsoft 문서"
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
- troubleshooting [Visual Basic], variables
- variables [Visual Basic], troubleshooting
ms.assetid: 928a2dc8-e565-4ae4-8ba3-80cc0cb50090
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ccf7ee3b0205dcd85d82c06e1822c4d3f9296a1c
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="troubleshooting-variables-in-visual-basic"></a><span data-ttu-id="23917-102">Visual Basic의 변수 문제 해결</span><span class="sxs-lookup"><span data-stu-id="23917-102">Troubleshooting Variables in Visual Basic</span></span>
<span data-ttu-id="23917-103">이 페이지의 변수를 사용할 때 발생할 수 있는 몇 가지 일반적인 문제를 나열 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="23917-103">This page lists some common problems that can occur when working with variables in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
## <a name="unable-to-access-members-of-an-object"></a><span data-ttu-id="23917-104">개체의 멤버에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="23917-104">Unable to Access Members of an Object</span></span>  
 <span data-ttu-id="23917-105">코드에서 개체의 속성이나 메서드에 액세스하려고 하면 다음과 같은 두 가지 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23917-105">If your code attempts to access a property or method on an object, there are two possible error outcomes:</span></span>  
  
-   <span data-ttu-id="23917-106">개체 변수를 특정 형식으로 선언한 다음 해당 형식으로 정의되지 않은 멤버를 참조하면 컴파일러에서 오류 메시지가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="23917-106">The compiler can generate an error message if you declare the object variable to be of a specific type and then refer to a member not defined by that type.</span></span>  
  
-   <span data-ttu-id="23917-107">런타임에 <xref:System.MemberAccessException>경우에 개체 변수 할당 된 개체가 코드에 액세스 하려고 하는 멤버를 노출 하지 않습니다.</xref:System.MemberAccessException></span><span class="sxs-lookup"><span data-stu-id="23917-107">A run-time <xref:System.MemberAccessException> occurs when the object assigned to an object variable does not expose the member your code is trying to access.</span></span> <span data-ttu-id="23917-108">변수 [Object 데이터 형식](../../../../visual-basic/language-reference/data-types/object-data-type.md), 멤버가 되지 않는 경우에이 예외를 얻을 수 있습니다 `Public`합니다.</span><span class="sxs-lookup"><span data-stu-id="23917-108">In the case of a variable of [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md), you can also get this exception if the member is not `Public`.</span></span> <span data-ttu-id="23917-109">그 이유는 런타임 바인딩에서는 `Public` 멤버에만 액세스할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="23917-109">This is because late binding allows access only to `Public` members.</span></span>  
  
 <span data-ttu-id="23917-110">경우는 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md) 집합 형식 검사 `On`, 메서드 및 속성 선언 된 클래스의 개체 변수에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23917-110">When the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) sets type checking `On`, an object variable can access only the methods and properties of the class with which you declare it.</span></span> <span data-ttu-id="23917-111">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="23917-111">The following example illustrates this.</span></span>  

 <span data-ttu-id="23917-112">[!code-vb[VbVbalrVariables #&2;](../../../../visual-basic/programming-guide/language-features/variables/codesnippet/VisualBasic/troubleshooting-variables_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="23917-112">[!code-vb[VbVbalrVariables#2](../../../../visual-basic/programming-guide/language-features/variables/codesnippet/VisualBasic/troubleshooting-variables_1.vb)]</span></span>  
  
 <span data-ttu-id="23917-113">이 예제에서는 `p` 의 멤버에만 사용할 수는 <xref:System.Object>포함 하지 않는 클래스 자체는 `Left` 속성.</xref:System.Object></span><span class="sxs-lookup"><span data-stu-id="23917-113">In this example, `p` can use only the members of the <xref:System.Object> class itself, which do not include the `Left` property.</span></span> <span data-ttu-id="23917-114">반면에 `q` 형식으로 선언 된 <xref:System.Windows.Forms.Label>모든 메서드와 속성을 사용할 수는 <xref:System.Windows.Forms.Label>클래스에 <xref:System.Windows.Forms>네임 스페이스.</xref:System.Windows.Forms> </xref:System.Windows.Forms.Label> </xref:System.Windows.Forms.Label></span><span class="sxs-lookup"><span data-stu-id="23917-114">On the other hand, `q` was declared to be of type <xref:System.Windows.Forms.Label>, so it can use all the methods and properties of the <xref:System.Windows.Forms.Label> class in the <xref:System.Windows.Forms> namespace.</span></span>  
  
### <a name="correct-approach"></a><span data-ttu-id="23917-115">해결 방법</span><span class="sxs-lookup"><span data-stu-id="23917-115">Correct Approach</span></span>  
 <span data-ttu-id="23917-116">특정 클래스 개체의 모든 멤버에 액세스하려면 개체 변수를 해당 클래스의 형식으로 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="23917-116">To be able to access all the members of an object of a particular class, declare the object variable to be of the type of that class when possible.</span></span> <span data-ttu-id="23917-117">예를 들어 개체 컴파일 타임에 형식을 알 수 없는 경우이 수행할 수 없습니다, 경우에 설정 해야 `Option Strict` 를 `Off` 변수를 선언 하 고는 [Object 데이터 형식](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="23917-117">If you cannot do this, for example if you do not know the object type at compile time, you must set `Option Strict` to `Off` and declare the variable to be of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span> <span data-ttu-id="23917-118">그러면 모든 형식의 개체가 변수에 할당될 수 있으므로 현재 할당된 개체의 형식이 적합한지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23917-118">This allows objects of any type to be assigned to the variable, and you should take steps to ensure that the currently assigned object is of an acceptable type.</span></span> <span data-ttu-id="23917-119">사용할 수는 [TypeOf 연산자](../../../../visual-basic/language-reference/operators/typeof-operator.md) 이 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="23917-119">You can use the [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) to make this determination.</span></span>  
  
## <a name="other-components-cannot-access-your-variable"></a><span data-ttu-id="23917-120">다른 구성 요소에서 사용자 변수에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="23917-120">Other Components Cannot Access Your Variable</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="23917-121">이름은 *대/소문자 구분*합니다.</span><span class="sxs-lookup"><span data-stu-id="23917-121"> names are *case-insensitive*.</span></span> <span data-ttu-id="23917-122">따라서 컴파일러에서는 대/소문자만 다른 두 이름을 동일한 이름으로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="23917-122">If two names differ in alphabetic case only, the compiler interprets them as the same name.</span></span> <span data-ttu-id="23917-123">예를 들어, `ABC` 와 `abc` 는 동일한 선언 요소를 참조하는 것으로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="23917-123">For example, it considers `ABC` and `abc` to refer to the same declared element.</span></span>  
  
 <span data-ttu-id="23917-124">그러나, CLR(공용 언어 런타임)에서는 *대/소문자를 구분하는* 바인딩을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="23917-124">However, the common language runtime (CLR) uses *case-sensitive* binding.</span></span> <span data-ttu-id="23917-125">그러므로, 어셈블리나 DLL을 작성하여 다른 어셈블리에서 이를 사용하게 되면 이름의 대/소문자가 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="23917-125">Therefore, when you produce an assembly or a DLL and make it available to other assemblies, your names are no longer case-insensitive.</span></span> <span data-ttu-id="23917-126">예를 들어, `ABC`라는 이름의 요소를 포함하는 클래스를 정의하고 다른 어셈블리에서 공용 언어 런타임을 통해 이 클래스를 사용할 경우 해당 어셈블리에서 이 요소를 `ABC`로 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23917-126">For example, if you define a class with an element called `ABC`, and other assemblies make use of your class through the common language runtime, they must refer to the element as `ABC`.</span></span> <span data-ttu-id="23917-127">클래스를 다시 컴파일하고 요소 이름을 `abc`로 변경하면 이 클래스를 사용하는 다른 어셈블리가 더 이상 이 요소에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="23917-127">If you subsequently recompile your class and change the element's name to `abc`, the other assemblies using your class can no longer access that element.</span></span> <span data-ttu-id="23917-128">따라서, 어셈블리를 업데이트하여 릴리스하는 경우 공용 요소의 알파벳 대/소문자를 변경하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23917-128">Therefore, when you release an updated version of an assembly, you should not change the alphabetic case of any public elements.</span></span>  
  
 <span data-ttu-id="23917-129">자세한 내용은 참조 [공용 언어 런타임](http://msdn.microsoft.com/library/059a624e-f7db-4134-ba9f-08b676050482)합니다.</span><span class="sxs-lookup"><span data-stu-id="23917-129">For more information, see [Common Language Runtime](http://msdn.microsoft.com/library/059a624e-f7db-4134-ba9f-08b676050482).</span></span>  
  
### <a name="correct-approach"></a><span data-ttu-id="23917-130">해결 방법</span><span class="sxs-lookup"><span data-stu-id="23917-130">Correct Approach</span></span>  
 <span data-ttu-id="23917-131">다른 구성 요소에서 사용자 변수에 액세스할 수 있도록 하려면 이름의 대/소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="23917-131">To allow other components to access your variables, treat their names as if they were case-sensitive.</span></span> <span data-ttu-id="23917-132">클래스나 모듈을 테스트하는 경우에는 다른 어셈블리가 원하는 변수에 바인딩되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="23917-132">When you are testing your class or module, make sure other assemblies are binding to the variables you expect them to.</span></span> <span data-ttu-id="23917-133">구성 요소를 게시한 경우에는 대/소문자 변경을 포함하여 기존 변수 이름을 수정하는 어떤 작업도 수행하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="23917-133">Once you have published a component, do not make any modifications to existing variable names, including changing their cases.</span></span>  
  
## <a name="wrong-variable-being-used"></a><span data-ttu-id="23917-134">잘못된 변수 사용</span><span class="sxs-lookup"><span data-stu-id="23917-134">Wrong Variable Being Used</span></span>  
 <span data-ttu-id="23917-135">동일한 이름의 변수가 두 개 이상의 경우는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러 해당 이름에 대 한 각 참조를 확인 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="23917-135">When you have more than one variable with the same name, the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler attempts to resolve each reference to that name.</span></span> <span data-ttu-id="23917-136">변수 범위가 다른 경우 컴파일러에서는 범위가 가장 작은 선언에 대한 참조를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="23917-136">If the variables have different scope, the compiler resolves a reference to the declaration with the narrowest scope.</span></span> <span data-ttu-id="23917-137">변수 범위가 같은 경우에는 확인에 실패하고 컴파일러에서 오류를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="23917-137">If they have the same scope, the resolution fails and the compiler signals an error.</span></span> <span data-ttu-id="23917-138">자세한 내용은 참조 [선언 된 요소에 대 한 참조](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="23917-138">For more information, see [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
### <a name="correct-approach"></a><span data-ttu-id="23917-139">해결 방법</span><span class="sxs-lookup"><span data-stu-id="23917-139">Correct Approach</span></span>  
 <span data-ttu-id="23917-140">이름은 같지만 범위가 다른 변수를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23917-140">Avoid using variables with the same name but different scope.</span></span> <span data-ttu-id="23917-141">다른 어셈블리나 프로젝트를 사용하는 경우에는 가능하면 이러한 외부 구성 요소에 정의된 이름을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23917-141">If you are using other assemblies or projects, avoid using any names defined in those external components as much as possible.</span></span> <span data-ttu-id="23917-142">이름이 같은 변수가 두 개 이상 있는 경우 모든 참조를 해당 이름으로 한정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23917-142">If you have more than one variable with the same name, be sure you qualify every reference to it.</span></span> <span data-ttu-id="23917-143">자세한 내용은 참조 [선언 된 요소에 대 한 참조](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="23917-143">For more information, see [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23917-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="23917-144">See Also</span></span>  
 <span data-ttu-id="23917-145">[변수](../../../../visual-basic/programming-guide/language-features/variables/index.md) </span><span class="sxs-lookup"><span data-stu-id="23917-145">[Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md) </span></span>  
<span data-ttu-id="23917-146"> [변수 선언](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="23917-146"> [Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span></span>  
<span data-ttu-id="23917-147"> [개체 변수](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md) </span><span class="sxs-lookup"><span data-stu-id="23917-147"> [Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md) </span></span>  
<span data-ttu-id="23917-148"> [개체 변수 선언](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="23917-148"> [Object Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md) </span></span>  
<span data-ttu-id="23917-149"> [방법: 개체의 멤버에 액세스](../../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md) </span><span class="sxs-lookup"><span data-stu-id="23917-149"> [How to: Access Members of an Object](../../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md) </span></span>  
<span data-ttu-id="23917-150"> [개체 변수 값](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md) </span><span class="sxs-lookup"><span data-stu-id="23917-150"> [Object Variable Values](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md) </span></span>  
<span data-ttu-id="23917-151"> [방법: 개체 변수가 참조 하는 형식 확인](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md) </span><span class="sxs-lookup"><span data-stu-id="23917-151"> [How to: Determine What Type an Object Variable Refers To](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md) </span></span>  
<span data-ttu-id="23917-152"> [선언 된 요소에 대 한 참조](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) </span><span class="sxs-lookup"><span data-stu-id="23917-152"> [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) </span></span>  
<span data-ttu-id="23917-153"> [선언 요소 이름](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)</span><span class="sxs-lookup"><span data-stu-id="23917-153"> [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)</span></span>
