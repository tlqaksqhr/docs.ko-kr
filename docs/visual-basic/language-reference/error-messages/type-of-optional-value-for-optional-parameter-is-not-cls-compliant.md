---
title: "선택적 매개 변수에 대 한 선택적 값의 형식이 &lt;parametername&gt; CLS 규격이 아닙니다"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- BC40042
- vbc40042
helpviewer_keywords: BC40042
ms.assetid: 1d6eae29-4ad3-4434-bde4-a53b6051adf5
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 442ff2e4b582287e03f425dad98128726fe18c43
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="type-of-optional-value-for-optional-parameter-ltparameternamegt-is-not-cls-compliant"></a><span data-ttu-id="89b61-102">선택적 매개 변수에 대 한 선택적 값의 형식이 &lt;parametername&gt; CLS 규격이 아닙니다</span><span class="sxs-lookup"><span data-stu-id="89b61-102">Type of optional value for optional parameter &lt;parametername&gt; is not CLS-compliant</span></span>
<span data-ttu-id="89b61-103">프로시저는 `<CLSCompliant(True)>`로 표시되지만 비규격 형식의 기본값을 가진 [선택적](../../../visual-basic/language-reference/modifiers/optional.md) 매개 변수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="89b61-103">A procedure is marked as `<CLSCompliant(True)>` but declares an [Optional](../../../visual-basic/language-reference/modifiers/optional.md) parameter with default value of a noncompliant type.</span></span>  
  
 <span data-ttu-id="89b61-104">프로시저가 [언어 독립성 및 언어 독립적 구성 요소](https://msdn.microsoft.com/library/12a7a7h3)(CLS)와 호환되려면 CLS 규격 형식만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b61-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="89b61-105">이는 매개 변수 형식, 반환 형식 및 모든 로컬 변수 형식에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="89b61-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span> <span data-ttu-id="89b61-106">또한 선택적 매개 변수의 기본값에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="89b61-106">It also applies to the default values of optional parameters.</span></span>  
  
 <span data-ttu-id="89b61-107">다음 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 데이터 형식은 CLS 규격이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="89b61-107">The following [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="89b61-108">SByte 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="89b61-108">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="89b61-109">UInteger 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="89b61-109">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="89b61-110">ULong 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="89b61-110">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="89b61-111">UShort 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="89b61-111">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="89b61-112"><xref:System.CLSCompliantAttribute> 특성을 프로그래밍 요소에 적용하는 경우 특성의 `isCompliant` 매개 변수를 `True` 또는 `False` 로 설정하여 준수 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="89b61-112">When you apply the <xref:System.CLSCompliantAttribute> attribute to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="89b61-113">이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b61-113">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="89b61-114">요소에 <xref:System.CLSCompliantAttribute> 를 적용하지 않으면 비규격인 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="89b61-114">If you do not apply <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="89b61-115">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="89b61-115">By default, this message is a warning.</span></span> <span data-ttu-id="89b61-116">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89b61-116">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="89b61-117">**오류 ID:** BC40042</span><span class="sxs-lookup"><span data-stu-id="89b61-117">**Error ID:** BC40042</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="89b61-118">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="89b61-118">To correct this error</span></span>  
  
-   <span data-ttu-id="89b61-119">선택적 매개 변수가 기본값인이 특정 형식을 사용 해야 하는 경우 제거 <xref:System.CLSCompliantAttribute>합니다.</span><span class="sxs-lookup"><span data-stu-id="89b61-119">If the optional parameter must have a default value of this particular type, remove <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="89b61-120">프로시저는 CLS 규격일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="89b61-120">The procedure cannot be CLS-compliant.</span></span>  
  
-   <span data-ttu-id="89b61-121">프로시저가 CLS 규격이어야 하는 경우 이 기본값의 형식을 가장 가까운 CLS 규격 형식으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="89b61-121">If the procedure must be CLS-compliant, change the type of this default value to the closest CLS-compliant type.</span></span> <span data-ttu-id="89b61-122">예를 들어 2,147,483,647을 초과하는 값 범위가 필요하지 않은 경우 `UInteger` 대신 `Integer` 을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b61-122">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="89b61-123">확장된 범위가 필요한 경우 `UInteger` 를 `Long`으로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89b61-123">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="89b61-124">자동화 또는 COM 개체와 상호 작용하는 경우 일부 형식의 데이터 너비가 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]와 다르다는 점을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89b61-124">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="89b61-125">예를 들어 `int`는 다른 환경에서 16비트인 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="89b61-125">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="89b61-126">이러한 구성 요소에서 16비트 정수를 수락할 경우 관리되는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 코드에서 `Integer` 대신 `Short`으로 선언하세요.</span><span class="sxs-lookup"><span data-stu-id="89b61-126">If you are accepting a 16-bit integer from such a component, declare it as `Short` instead of `Integer` in your managed [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89b61-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="89b61-127">See Also</span></span>  
 [<span data-ttu-id="89b61-128">\<통해 PAVE > CLS 규격 코드 작성</span><span class="sxs-lookup"><span data-stu-id="89b61-128">\<PAVE OVER> Writing CLS-Compliant Code</span></span>](http://msdn.microsoft.com/en-us/4c705105-69a2-4e5e-b24e-0633bc32c7f3)
