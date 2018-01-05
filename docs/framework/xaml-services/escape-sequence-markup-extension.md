---
title: "{} 이스케이프 시퀀스 태그 확장"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: '{}'
helpviewer_keywords:
- XAML [XAML Services], quotation mark (")
- '{} escape sequence [XAML Services]'
- XAML [XAML Services], {} escape sequence
- XAML [XAML Services], escape sequence
- quotation mark (") [XAML Services]
- escape sequence [XAML Services]
ms.assetid: 3ce3e2ad-a868-43f9-9c98-b29561cb146e
caps.latest.revision: "21"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8419a1e89d5e94b9868b0fd1fb81540253efca5d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="-escape-sequence--markup-extension"></a><span data-ttu-id="a91c7-102">{} 이스케이프 시퀀스 / 태그 확장명</span><span class="sxs-lookup"><span data-stu-id="a91c7-102">{} Escape Sequence / Markup Extension</span></span>
<span data-ttu-id="a91c7-103">특성 값에 대 한 XAML 이스케이프 시퀀스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a91c7-103">Provides the XAML escape sequence for attribute values.</span></span> <span data-ttu-id="a91c7-104">이스케이프 시퀀스는 리터럴로 해석 될 특성에 이후 값을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a91c7-104">The escape sequence allows the subsequent values in the attribute to be interpreted as a literal.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="a91c7-105">XAML 특성 사용</span><span class="sxs-lookup"><span data-stu-id="a91c7-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{} literalValue" .../>  
```  
  
## <a name="xaml-property-element-usage"></a><span data-ttu-id="a91c7-106">XAML 속성 요소 사용</span><span class="sxs-lookup"><span data-stu-id="a91c7-106">XAML Property Element Usage</span></span>  
  
```  
<object>  
  <object.property>  
    {} literalValue  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="a91c7-107">XAML 값</span><span class="sxs-lookup"><span data-stu-id="a91c7-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a91c7-108">*literalValue*</span><span class="sxs-lookup"><span data-stu-id="a91c7-108">*literalValue*</span></span>|<span data-ttu-id="a91c7-109">뒤에 오는 이스케이프 시퀀스는 리터럴 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a91c7-109">The literal string that follows the escape sequence.</span></span> <span data-ttu-id="a91c7-110">일반적으로이 문자열 포함 열기 / 닫기 중괄호 ({또는}).</span><span class="sxs-lookup"><span data-stu-id="a91c7-110">Typically this string contains an open or close brace ({ or }).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a91c7-111">설명</span><span class="sxs-lookup"><span data-stu-id="a91c7-111">Remarks</span></span>  
 <span data-ttu-id="a91c7-112">이스케이프 시퀀스 ({) 중괄호 ({) XAML에서 리터럴 문자로 사용 될 수 있도록 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a91c7-112">The escape sequence ({}) is used so that an open brace ({)can be used as a literal character in XAML.</span></span>  
  
 <span data-ttu-id="a91c7-113">일반적으로 XAML 판독기를 태그 확장의 진입점을 나타내는 중괄호 ({})을 사용 합니다; 그러나 다음 문자는 닫는 중괄호 (}) 되는지 확인 하려면 먼저 체크</span><span class="sxs-lookup"><span data-stu-id="a91c7-113">XAML readers typically use the open brace ({) to denote the entry point of a markup extension; however, they first check the next character to determine whether it is a closing brace (}).</span></span> <span data-ttu-id="a91c7-114">두 중괄호 ({})가 인접 한 경우에 이스케이프 시퀀스를 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a91c7-114">Only when the two braces ({}) are adjacent, are they considered an escape sequence.</span></span>  
  
 <span data-ttu-id="a91c7-115">이스케이프 시퀀스가 발생 하는 XAML 판독기는 문자열로 서 문자열의 나머지 부분을 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a91c7-115">If the escape sequence is encountered, the XAML reader should process the remainder of the string as a string.</span></span> <span data-ttu-id="a91c7-116">그러나 이스케이프 시퀀스는 형식 변환기가 멤버에 적용 하는 XAML 작성기에 의해 해석 될 때 문자열 형식 변환을 거쳐야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a91c7-116">However, if the escape sequence is applied to a member that has a type converter, the string might undergo type conversion when it is interpreted by a XAML writer.</span></span>  
  
 <span data-ttu-id="a91c7-117">이스케이프 시퀀스는 태그 확장 아니며 클래스에 기반 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a91c7-117">The escape sequence is not a markup extension and is not backed by a class.</span></span> <span data-ttu-id="a91c7-118">그러나 하는 XAML 판독기 (사용자 지정 XAML 판독기 포함)을 준수 해야 하는 변환입니다.</span><span class="sxs-lookup"><span data-stu-id="a91c7-118">However, it is a convention that XAML readers (including custom XAML readers) should respect.</span></span>  
  
 <span data-ttu-id="a91c7-119">이런이 방식으로 이스케이프 시퀀스로 따옴표 (")를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a91c7-119">A quotation mark (") cannot be used as an escape sequence in this manner.</span></span> <span data-ttu-id="a91c7-120">콘텐츠가 아닌 속성에 대 한 속성 값으로는 따옴표를 설정 해야 속성 요소 구문을 사용 및 property 요소 내의 문자열로 큰따옴표를 배치 하거나 XML 문자 엔터티를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a91c7-120">If you need to set a quotation mark as a property value for a noncontent property, use property element syntax and place the quotation mark as a string inside the property element, or use an XML character entity.</span></span> <span data-ttu-id="a91c7-121">콘텐츠 속성의 경우: 따옴표 전체가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a91c7-121">For a content property, the quotation mark can be the entire content.</span></span>  
  
 <span data-ttu-id="a91c7-122">이스케이프 시퀀스 ({})는 XAML 태그 확장 나타나는 위치에 네임 스페이스 한정자를 포함 해야 하는 XML 형식을 지정 하는 경우 필요한 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a91c7-122">The escape sequence ({}) is frequently required when specifying an XML type that must include a namespace qualifier in a location where a XAML markup extension might appear.</span></span> <span data-ttu-id="a91c7-123">이 등호 (=) 후 즉시 시작 XAML 특성 값 및 태그 확장에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a91c7-123">This includes the start of a XAML attribute value, and in a markup extension, immediately after an equal sign (=).</span></span> <span data-ttu-id="a91c7-124">다음 예제에서는 XAML 특성 값의 시작 부분에 표시 되는 XML 네임 스페이스에 대 한 이스케이프 시퀀스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a91c7-124">The following example shows escape sequences for an XML namespace that appears at the start of a XAML attribute value.</span></span>  
  
 [!code-xaml[XLINQExample#StackPanelResources](../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
  
## <a name="see-also"></a><span data-ttu-id="a91c7-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a91c7-125">See Also</span></span>  
 [<span data-ttu-id="a91c7-126">XAML을 위한 형식 변환기 및 태그 확장명</span><span class="sxs-lookup"><span data-stu-id="a91c7-126">Type Converters and Markup Extensions for XAML</span></span>](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md)  
 [<span data-ttu-id="a91c7-127">XML 문자 엔터티 및 XAML</span><span class="sxs-lookup"><span data-stu-id="a91c7-127">XML Character Entities and XAML</span></span>](../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md)
