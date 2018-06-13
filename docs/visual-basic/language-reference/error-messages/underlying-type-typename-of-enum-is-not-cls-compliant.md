---
title: 내부 형식 &lt;typename&gt; 열거형의는 CLS 규격이 아닙니다
ms.date: 07/20/2015
f1_keywords:
- vbc40032
- bc40032
helpviewer_keywords:
- BC40032
ms.assetid: 32bf1949-fd73-456c-a323-bf1ffe1320ed
ms.openlocfilehash: 876a59d1441c1ba4c5057556d5ef2fb2ecb43af6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33596621"
---
# <a name="underlying-type-lttypenamegt-of-enum-is-not-cls-compliant"></a><span data-ttu-id="cd9b7-102">내부 형식 &lt;typename&gt; 열거형의는 CLS 규격이 아닙니다</span><span class="sxs-lookup"><span data-stu-id="cd9b7-102">Underlying type &lt;typename&gt; of Enum is not CLS-compliant</span></span>
<span data-ttu-id="cd9b7-103">이 열거형은 하지에 대해 지정 된 데이터 형식에 속하지는 [언어 독립성 및 언어 독립적 구성 요소](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span><span class="sxs-lookup"><span data-stu-id="cd9b7-103">The data type specified for this enumeration is not part of the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span> <span data-ttu-id="cd9b7-104">때문에 사용자 구성 요소에서 오류는는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 및 Visual Basic에는이 데이터 형식을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd9b7-104">This is not an error within your component, because the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] and Visual Basic support this data type.</span></span> <span data-ttu-id="cd9b7-105">그러나 엄격 하 게 CLS 규격 코드 작성 된 다른 구성 요소는이 데이터 형식을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd9b7-105">However, another component written in strictly CLS-compliant code might not support this data type.</span></span> <span data-ttu-id="cd9b7-106">이러한 구성 요소를 성공적으로 구성 요소와 상호 작용할 수 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd9b7-106">Such a component might not be able to interact successfully with your component.</span></span>  
  
 <span data-ttu-id="cd9b7-107">다음 Visual Basic 데이터 형식 CLS 호환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd9b7-107">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="cd9b7-108">SByte 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="cd9b7-108">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="cd9b7-109">UInteger 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="cd9b7-109">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="cd9b7-110">ULong 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="cd9b7-110">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="cd9b7-111">UShort 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="cd9b7-111">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="cd9b7-112">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="cd9b7-112">By default, this message is a warning.</span></span> <span data-ttu-id="cd9b7-113">경고를 숨기 거 나 경고를 오류로 처리 하는 방법에 대 한 자세한 내용은 참조 하십시오. [Visual Basic에서 경고 구성](/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="cd9b7-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="cd9b7-114">**오류 ID:** BC40032</span><span class="sxs-lookup"><span data-stu-id="cd9b7-114">**Error ID:** BC40032</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cd9b7-115">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="cd9b7-115">To correct this error</span></span>  
  
-   <span data-ttu-id="cd9b7-116">구성 요소가 다른만 상호 작용 하는 경우 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 구성 요소 또는 다른 모든 구성 요소와 인터페이스 하지, 아무 것도 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cd9b7-116">If your component interfaces only with other [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] components, or does not interface with any other components, you do not need to change anything.</span></span>  
  
-   <span data-ttu-id="cd9b7-117">대해 작성 되지 않은 구성 요소와 조작 하는 경우는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], 결정, 리플렉션을 통해 수 있습니다 또는 문서에서 지원 하는지 여부이 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="cd9b7-117">If you are interfacing with a component not written for the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], you might be able to determine, either through reflection or from documentation, whether it supports this data type.</span></span> <span data-ttu-id="cd9b7-118">그렇지 않으면 아무 것도 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cd9b7-118">If it does, you do not need to change anything.</span></span>  
  
-   <span data-ttu-id="cd9b7-119">이 데이터 형식을 지원 하지 않는 구성 요소와 같이 하는 경우에 가장 가까운 CLS 규격 형식으로 대체 해야 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd9b7-119">If you are interfacing with a component that does not support this data type, you must replace it with the closest CLS-compliant type.</span></span> <span data-ttu-id="cd9b7-120">예를 들어 2,147,483,647을 초과하는 값 범위가 필요하지 않은 경우 `UInteger` 대신 `Integer` 을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd9b7-120">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="cd9b7-121">확장된 범위가 필요한 경우 `UInteger` 를 `Long`으로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd9b7-121">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="cd9b7-122">자동화 또는 COM 개체와 상호 작용하는 경우 일부 형식의 데이터 너비가 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]와 다르다는 점을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd9b7-122">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="cd9b7-123">예를 들어 `uint`는 다른 환경에서 16비트인 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="cd9b7-123">For example, `uint` is often 16 bits in other environments.</span></span> <span data-ttu-id="cd9b7-124">이러한 구성 요소를 16 비트 인수를 전달 하는 경우로 선언 `UShort` 대신 `UInteger` 관리 되는 Visual Basic 코드에서.</span><span class="sxs-lookup"><span data-stu-id="cd9b7-124">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed Visual Basic code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd9b7-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cd9b7-125">See Also</span></span>  
 [<span data-ttu-id="cd9b7-126">리플렉션(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cd9b7-126">Reflection (Visual Basic)</span></span>](../../programming-guide/concepts/reflection.md)  
 [<span data-ttu-id="cd9b7-127">리플렉션</span><span class="sxs-lookup"><span data-stu-id="cd9b7-127">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)  
 
