---
title: "XAML의 xml:space 처리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], whitespace processing
- xml:space attribute [XAML Services]
- whitespace processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
caps.latest.revision: "15"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8b8356cdb47b6b834e8d9a6bb84b26445af6d865
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="xmlspace-handling-in-xaml"></a><span data-ttu-id="d691a-102">XAML의 xml:space 처리</span><span class="sxs-lookup"><span data-stu-id="d691a-102">xml:space Handling in XAML</span></span>
<span data-ttu-id="d691a-103">`xml:space` 특성은 object 요소 내에서 공백 처리 동작을 선언 하는 XML로 정의 된 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d691a-103">The `xml:space` attribute is an XML-defined attribute that declares the significant whitespace processing behavior within an object element.</span></span> <span data-ttu-id="d691a-104">이 동작은 요소 내에 포함 된 모든 콘텐츠 (내부 텍스트)와 관련이 있는 `xml:space` 선언 되 고 범위 자식 요소를 합니다.</span><span class="sxs-lookup"><span data-stu-id="d691a-104">This behavior is relevant for all content (inner text) contained within the element where `xml:space` is declared, and also scopes to child elements.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="d691a-105">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="d691a-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 <span data-ttu-id="d691a-106">\- 또는 -</span><span class="sxs-lookup"><span data-stu-id="d691a-106">\- or -</span></span>  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a><span data-ttu-id="d691a-107">설명</span><span class="sxs-lookup"><span data-stu-id="d691a-107">Remarks</span></span>  
 <span data-ttu-id="d691a-108">에 대 한 정의 `xml:space` 가능한 두 값을 포함 하 여 XAML의 특성에서 파생 된 `xml:space` XML에 대 한 W3C 사양에 "특수 특성"으로 정의 된 대로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d691a-108">The definition for the `xml:space` attribute in XAML including its two possible values is derived from `xml:space` as defined as a "special attribute" by W3C specifications for XML.</span></span>  
  
 <span data-ttu-id="d691a-109">기본값은 `xml:space` 특성은 리터럴 값 `"default"`합니다.</span><span class="sxs-lookup"><span data-stu-id="d691a-109">The default value of the `xml:space` attribute is the literal value `"default"`.</span></span> <span data-ttu-id="d691a-110">값에 대 한 `"default"`, if 또는 `xml:space` 항목에 정의 된 공백을 구문 분석의 동작은 기본 처리 전혀 표시 되지 않습니다 [XAML의 공백 처리](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d691a-110">For the value `"default"`, or if `xml:space` is not indicated at all, the behavior of significant whitespace parsing is the default handling, as defined in the topic [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span></span>  
  
 <span data-ttu-id="d691a-111">개체 요소 콘텐츠 내에서 공백을 유지 하기 위해 지정 `xml:space="preserve"` 개체 요소의 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d691a-111">To preserve whitespace within object element content, specify `xml:space="preserve"` on that object element.</span></span>  
  
 <span data-ttu-id="d691a-112">대부분의 해석 된 `xml:space` 특성 효과 및 특성의 값을 자식 요소 범위가 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d691a-112">Under most interpretations, the `xml:space` attribute effects and the value of the attribute are scoped to child elements.</span></span>  
  
 <span data-ttu-id="d691a-113">XAML의 공백 처리에 대 한 자세한 내용은 참조 하십시오. [XAML의 공백 처리](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d691a-113">For a complete discussion of whitespace processing in XAML, see [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d691a-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d691a-114">See Also</span></span>  
 [<span data-ttu-id="d691a-115">XAML의 공백 처리</span><span class="sxs-lookup"><span data-stu-id="d691a-115">Whitespace Processing in XAML</span></span>](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)  
 [<span data-ttu-id="d691a-116">XAML 개요(WPF)</span><span class="sxs-lookup"><span data-stu-id="d691a-116">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
