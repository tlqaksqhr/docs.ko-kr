---
title: "유형의 멤버 &#39; &lt;membername&gt;&#39; CLS 규격이 아닙니다"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc40025
- vbc40025
helpviewer_keywords:
- BC40025
ms.assetid: adbd34bb-43d2-4266-90e7-cd1afaf49b4e
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bc82714d25efbe9d379fff36f92261cf25a78862
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="type-of-member-39ltmembernamegt39-is-not-cls-compliant"></a><span data-ttu-id="c1a52-102">유형의 멤버 &#39; &lt;membername&gt;&#39; CLS 규격이 아닙니다</span><span class="sxs-lookup"><span data-stu-id="c1a52-102">Type of member &#39;&lt;membername&gt;&#39; is not CLS-compliant</span></span>
<span data-ttu-id="c1a52-103">이 멤버는 없습니다에 대해 지정 된 데이터 형식에 속하지는 [언어 독립성 및 언어 독립적 구성 요소](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span><span class="sxs-lookup"><span data-stu-id="c1a52-103">The data type specified for this member is not part of the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span> <span data-ttu-id="c1a52-104">때문에 사용자 구성 요소에서 오류는는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 및 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 이 데이터 형식을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a52-104">This is not an error within your component, because the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] and [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] support this data type.</span></span> <span data-ttu-id="c1a52-105">그러나 엄격 하 게 CLS 규격 코드 작성 된 다른 구성 요소는이 데이터 형식을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a52-105">However, another component written in strictly CLS-compliant code might not support this data type.</span></span> <span data-ttu-id="c1a52-106">이러한 구성 요소를 성공적으로 구성 요소와 상호 작용할 수 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a52-106">Such a component might not be able to interact successfully with your component.</span></span>  
  
 <span data-ttu-id="c1a52-107">다음 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 데이터 형식은 CLS 규격이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c1a52-107">The following [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] data types are not CLS-compliant:</span></span>  
  
-   [<span data-ttu-id="c1a52-108">SByte 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c1a52-108">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [<span data-ttu-id="c1a52-109">UInteger 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c1a52-109">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [<span data-ttu-id="c1a52-110">ULong 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c1a52-110">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [<span data-ttu-id="c1a52-111">UShort 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c1a52-111">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="c1a52-112">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="c1a52-112">By default, this message is a warning.</span></span> <span data-ttu-id="c1a52-113">경고를 숨기 거 나 경고를 오류로 처리 하는 방법에 대 한 자세한 내용은 참조 하십시오. [Visual Basic에서 경고 구성](/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a52-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="c1a52-114">**오류 ID:** BC40025</span><span class="sxs-lookup"><span data-stu-id="c1a52-114">**Error ID:** BC40025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c1a52-115">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="c1a52-115">To correct this error</span></span>  
  
-   <span data-ttu-id="c1a52-116">구성 요소가 다른만 상호 작용 하는 경우 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 구성 요소 또는 다른 모든 구성 요소와 인터페이스 하지, 아무 것도 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a52-116">If your component interfaces only with other [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] components, or does not interface with any other components, you do not need to change anything.</span></span>  
  
-   <span data-ttu-id="c1a52-117">대해 작성 되지 않은 구성 요소와 조작 하는 경우는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], 결정, 리플렉션을 통해 수 있습니다 또는 문서에서 지원 하는지 여부이 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c1a52-117">If you are interfacing with a component not written for the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], you might be able to determine, either through reflection or from documentation, whether it supports this data type.</span></span> <span data-ttu-id="c1a52-118">그렇지 않으면 아무 것도 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a52-118">If it does, you do not need to change anything.</span></span>  
  
-   <span data-ttu-id="c1a52-119">이 데이터 형식을 지원 하지 않는 구성 요소와 같이 하는 경우에 가장 가까운 CLS 규격 형식으로 대체 해야 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a52-119">If you are interfacing with a component that does not support this data type, you must replace it with the closest CLS-compliant type.</span></span> <span data-ttu-id="c1a52-120">예를 들어 2,147,483,647을 초과하는 값 범위가 필요하지 않은 경우 `UInteger` 대신 `Integer` 을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a52-120">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="c1a52-121">확장된 범위가 필요한 경우 `UInteger` 를 `Long`으로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a52-121">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
-   <span data-ttu-id="c1a52-122">자동화 또는 COM 개체와 상호 작용하는 경우 일부 형식의 데이터 너비가 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]와 다르다는 점을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1a52-122">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="c1a52-123">예를 들어 `uint`는 다른 환경에서 16비트인 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="c1a52-123">For example, `uint` is often 16 bits in other environments.</span></span> <span data-ttu-id="c1a52-124">이러한 구성 요소를 16 비트 인수를 전달 하는 경우로 선언 `UShort` 대신 `UInteger` 관리 되는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c1a52-124">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1a52-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c1a52-125">See Also</span></span>  
 [<span data-ttu-id="c1a52-126">리플렉션</span><span class="sxs-lookup"><span data-stu-id="c1a52-126">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)  
 
