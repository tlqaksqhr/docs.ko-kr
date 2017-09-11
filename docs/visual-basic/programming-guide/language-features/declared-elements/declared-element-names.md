---
title: "선언 된 요소 이름 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- declared elements, case sensitivity
- names, Visual Basic rules
- naming conventions
- element names
- declared elements, identifiers
- declarations, elements
- declared elements, valid names
- '[] escape characters [Visual Basic]'
- names, elements
- declaration statements, declared elements
- declaring elements
- identifiers, declared elements
- case sensitivity, declared element names
- escape characters
- names, declared elements
- declared elements, about declared elements
- escaped names
- declared elements, names
- names, naming conventions
- identifiers, elements
ms.assetid: 09d8843b-c0dc-4afe-9dab-87c439a69e66
caps.latest.revision: 27
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
ms.openlocfilehash: 899bcb2ecc8f5c07fdf4592e15827ff67f55c136
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="declared-element-names-visual-basic"></a><span data-ttu-id="8641e-102">선언된 요소 이름(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8641e-102">Declared Element Names (Visual Basic)</span></span>
<span data-ttu-id="8641e-103">선언 된 모든 요소에 이름이 있는 라고도 *식별자*, 즉, 참조 하는 데 코드 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8641e-103">Every declared element has a name, also called an *identifier*, which is what the code uses to refer to it.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="8641e-104">규칙</span><span class="sxs-lookup"><span data-stu-id="8641e-104">Rules</span></span>  
 <span data-ttu-id="8641e-105">요소 이름은 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 다음 규칙을 준수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8641e-105">An element name in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] must observe the following rules:</span></span>  
  
-   <span data-ttu-id="8641e-106">영문자 또는 밑줄으로 시작 해야 합니다 (`_`).</span><span class="sxs-lookup"><span data-stu-id="8641e-106">It must begin with an alphabetic character or an underscore (`_`).</span></span>  
  
-   <span data-ttu-id="8641e-107">알파벳 문자와&10; 진수 숫자, 밑줄에만 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8641e-107">It must only contain alphabetic characters, decimal digits, and underscores.</span></span>  
  
-   <span data-ttu-id="8641e-108">밑줄로 시작 하는 경우 하나 이상의 영문자 또는&10; 진수 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8641e-108">It must contain at least one alphabetic character or decimal digit if it begins with an underscore.</span></span>  
  
-   <span data-ttu-id="8641e-109">개 이상의 1023 자 아니어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8641e-109">It must not be more than 1023 characters long.</span></span>  
  
 <span data-ttu-id="8641e-110">1023 자 길이 제한에도 적용 됩니다 정규화 된 이름, 전체 문자열 같은 `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`합니다.</span><span class="sxs-lookup"><span data-stu-id="8641e-110">The length limit of 1023 characters also applies to the entire string of a fully qualified name, such as `outerNamespace.middleNamespace.innerNamespace.thisClass.thisElement`.</span></span>  
  
 <span data-ttu-id="8641e-111">다음 예제에서는 올바른 요소 이름을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8641e-111">The following example shows some valid element names.</span></span>  
  
 `aB123__45`  
  
 `_567`  
  
 <span data-ttu-id="8641e-112">다음 예제에서는 잘못 된 요소 이름을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8641e-112">The following example shows some invalid element names.</span></span> <span data-ttu-id="8641e-113">첫 번째는 밑줄만 포함,&10; 진수로 시작 하 고 두 번째 및 세 번째 잘못 된 문자 ($)를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="8641e-113">The first contains only an underscore, the second begins with a decimal digit, and the third contains an invalid character ($).</span></span>  
  
 `' Three INVALID element names`  
  
 `_`  
  
 `12ABC`  
  
 `xyz$wv`  
  
> [!CAUTION]
>  <span data-ttu-id="8641e-114">밑줄로 시작 하는 요소 이름 (`_`)의 일부가 [언어 독립성 및 언어 독립적 구성 요소](https://msdn.microsoft.com/library/12a7a7h3) CLS ()를 CLS 규격 코드에서 해당 이름을 정의 하는 구성 요소를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8641e-114">Element names starting with an underscore (`_`) are not part of the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), so CLS-compliant code cannot use a component that defines such names.</span></span> <span data-ttu-id="8641e-115">그러나 요소 이름에 다른 위치에는 밑줄은 CLS 규격입니다.</span><span class="sxs-lookup"><span data-stu-id="8641e-115">However, an underscore in any other position in an element name is CLS-compliant.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="8641e-116">이름 길이 지침</span><span class="sxs-lookup"><span data-stu-id="8641e-116">Name Length Guidelines</span></span>  
 <span data-ttu-id="8641e-117">명확히 요소의 특성을 식별 하는 동안 사용자 이름은 가능한 한 짧게 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8641e-117">As a practical matter, your name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="8641e-118">이 코드의 가독성을 향상 하 고 줄 길이 소스 파일 크기를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="8641e-118">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="8641e-119">반면에 사용자 이름을 설명 하지는 않습니다 적절 하 게 코드 방법을 사용 하 여 요소 무엇을 나타내는지를 짧은 되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8641e-119">On the other hand, your name should not be so short that it does not adequately describe what the element represents and how your code uses it.</span></span> <span data-ttu-id="8641e-120">이 코드의 가독성을 위해 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8641e-120">This is important for the readability of your code.</span></span> <span data-ttu-id="8641e-121">이해 하려는 다른 사용자 또는 사용자가 직접 찾고 있는 경우에 쓰고 후 오랫동안 적합 한 요소 이름을 상당한 시간이 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8641e-121">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, suitable element names can save a considerable amount of time.</span></span>  
  
## <a name="escaped-names"></a><span data-ttu-id="8641e-122">이스케이프 이름</span><span class="sxs-lookup"><span data-stu-id="8641e-122">Escaped Names</span></span>  
 <span data-ttu-id="8641e-123">일반적으로 요소 이름은 같아서는 안 하 여 예약 된 키워드의 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], 예: `Case` 또는 `Friend`합니다.</span><span class="sxs-lookup"><span data-stu-id="8641e-123">Generally, an element name must not match any of the keywords reserved by [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], such as `Case` or `Friend`.</span></span> <span data-ttu-id="8641e-124">그러나 정의할 수는 *이스케이프 이름*, 괄호로 묶여 있는 (`[ ]`).</span><span class="sxs-lookup"><span data-stu-id="8641e-124">However, you can define an *escaped name*, which is enclosed by brackets (`[ ]`).</span></span> <span data-ttu-id="8641e-125">일치 하는 이스케이프 된 이름 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 키워드를 대괄호 모호성이 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="8641e-125">An escaped name can match any [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] keyword, since the brackets remove any ambiguity.</span></span> <span data-ttu-id="8641e-126">코드에서 이름으로 참조할 때 대괄호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8641e-126">You also use the brackets when you refer to the name later in your code.</span></span>  
  
 <span data-ttu-id="8641e-127">이스케이프 된 이름을 사용 해야 하는 일반적으로 경우에만:</span><span class="sxs-lookup"><span data-stu-id="8641e-127">In general, you should use escaped names only when:</span></span>  
  
-   <span data-ttu-id="8641e-128">코드의 이전 버전에서 마이그레이션된 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 되는 이름으로 사용 되는 키워드를 예약 하지 않은 또는</span><span class="sxs-lookup"><span data-stu-id="8641e-128">Your code has migrated from a previous version of [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] that did not reserve the keyword being used as a name; or</span></span>  
  
-   <span data-ttu-id="8641e-129">지정 된 키워드는 예약 되지 않은 다른 언어로 작성 된 코드를 사용 하 여 작업할 합니다.</span><span class="sxs-lookup"><span data-stu-id="8641e-129">You are working with code written in another language in which the given keyword is not reserved.</span></span>  
  
 <span data-ttu-id="8641e-130">그렇지 않으면 해당 이름이 키워드와 충돌 하는 경우 해당 요소의 이름을 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8641e-130">Otherwise, you should consider renaming the element if its name conflicts with a keyword.</span></span> <span data-ttu-id="8641e-131">통합된 개발 환경 (IDE)이 작업을 수행 하는 쉬운 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8641e-131">The integrated development environment (IDE) provides an easy way to do this.</span></span> <span data-ttu-id="8641e-132">자세한 내용은 참조 [Refactoring](https://docs.microsoft.com/visualstudio/vb-ide/refactoring-vb)합니다.</span><span class="sxs-lookup"><span data-stu-id="8641e-132">For more information, see [Refactoring](https://docs.microsoft.com/visualstudio/vb-ide/refactoring-vb).</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="8641e-133">이름에서 대/소문자 구분</span><span class="sxs-lookup"><span data-stu-id="8641e-133">Case Sensitivity in Names</span></span>  
 <span data-ttu-id="8641e-134">요소 이름은 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 대/소문자 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="8641e-134">Element names in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] are case-insensitive.</span></span> <span data-ttu-id="8641e-135">이 컴파일러에 소문자만 다른 두 이름이 같고, 것으로 해석 동일한 이름을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="8641e-135">This means that when the compiler compares two names that differ in alphabetic case only, it interprets them as the same name.</span></span> <span data-ttu-id="8641e-136">예를 들어, `ABC` 와 `abc` 는 동일한 선언 요소를 참조하는 것으로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="8641e-136">For example, it considers `ABC` and `abc` to refer to the same declared element.</span></span>  
  
 <span data-ttu-id="8641e-137">그러나 공용 언어 런타임 (CLR)에 대/소문자 구분 바인딩을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8641e-137">However, the common language runtime (CLR) uses case-sensitive binding.</span></span> <span data-ttu-id="8641e-138">그러므로, 어셈블리나 DLL을 작성하여 다른 어셈블리에서 이를 사용하게 되면 이름의 대/소문자가 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="8641e-138">Therefore, when you produce an assembly or a DLL and make it available to other assemblies, your names are no longer case-insensitive.</span></span> <span data-ttu-id="8641e-139">예를 들어, `ABC`라는 이름의 요소를 포함하는 클래스를 정의하고 다른 어셈블리에서 공용 언어 런타임을 통해 이 클래스를 사용할 경우 해당 어셈블리에서 이 요소를 `ABC`로 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8641e-139">For example, if you define a class with an element called `ABC`, and other assemblies make use of your class through the common language runtime, they must refer to the element as `ABC`.</span></span> <span data-ttu-id="8641e-140">경우 이후에 클래스를 다시 컴파일한 요소의 이름을 `abc`, 클래스를 사용 하는 다른 어셈블리가 해당 요소를 더 이상 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8641e-140">If you subsequently recompile your class and change the element's name to `abc`, the other assemblies using your class could no longer access that element.</span></span> <span data-ttu-id="8641e-141">따라서, 어셈블리를 업데이트하여 릴리스하는 경우 공용 요소의 알파벳 대/소문자를 변경하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8641e-141">Therefore, when you release an updated version of an assembly, you should not change the alphabetic case of any public elements.</span></span>  
  
## <a name="names-and-locales"></a><span data-ttu-id="8641e-142">이름 및 로캘</span><span class="sxs-lookup"><span data-stu-id="8641e-142">Names and Locales</span></span>  
 <span data-ttu-id="8641e-143">이름 비교는 로캘과 무관 합니다.</span><span class="sxs-lookup"><span data-stu-id="8641e-143">Comparison of names is independent of locale.</span></span> <span data-ttu-id="8641e-144">두 이름이 일치 한 로캘에서 모든 로캘에서 일치 하도록 보장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8641e-144">If two names match in one locale, they are guaranteed to match in all locales.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8641e-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8641e-145">See Also</span></span>  
 <span data-ttu-id="8641e-146">[선언된 요소](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md) </span><span class="sxs-lookup"><span data-stu-id="8641e-146">[Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md) </span></span>  
<span data-ttu-id="8641e-147"> [선언된 요소의 특징](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span><span class="sxs-lookup"><span data-stu-id="8641e-147"> [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span></span>  
<span data-ttu-id="8641e-148"> [선언 된 요소에 대 한 참조](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) </span><span class="sxs-lookup"><span data-stu-id="8641e-148"> [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) </span></span>  
<span data-ttu-id="8641e-149"> [문](../../../../visual-basic/language-reference/statements/index.md)</span><span class="sxs-lookup"><span data-stu-id="8641e-149"> [Statements](../../../../visual-basic/language-reference/statements/index.md)</span></span>
