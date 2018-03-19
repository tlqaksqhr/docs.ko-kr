---
title: "XML 형식 지원 구현 참고 사항"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 26b071f3-1261-47ef-8690-0717f5cd93c1
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8c2706782ed1242ecdb5af1fdfab7a3f24e19236
ms.sourcegitcommit: 15316053918995cc1380163a7d7e7edd5c44e6d7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2018
---
# <a name="xml-type-support-implementation-notes"></a><span data-ttu-id="1040f-102">XML 형식 지원 구현 참고 사항</span><span class="sxs-lookup"><span data-stu-id="1040f-102">XML Type Support Implementation Notes</span></span>
<span data-ttu-id="1040f-103">이 항목에서는 자세히 알아야 할 몇 가지 구현 정보에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1040f-103">This topic describes some implementation details that you want to be aware of.</span></span>  
  
## <a name="list-mappings"></a><span data-ttu-id="1040f-104">목록 매핑</span><span class="sxs-lookup"><span data-stu-id="1040f-104">List Mappings</span></span>  
 <span data-ttu-id="1040f-105"><xref:System.Collections.IList>, <xref:System.Collections.ICollection>, <xref:System.Collections.IEnumerable>, **Type[]** 및 <xref:System.String> 형식을 사용하여 XSD(XML 스키마 정의 언어) 목록 형식을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1040f-105">The <xref:System.Collections.IList>, <xref:System.Collections.ICollection>, <xref:System.Collections.IEnumerable>, **Type[]**, and <xref:System.String> types are used to represent XML Schema definition language (XSD) list types.</span></span>  
  
## <a name="union-mappings"></a><span data-ttu-id="1040f-106">통합 매핑</span><span class="sxs-lookup"><span data-stu-id="1040f-106">Union Mappings</span></span>  
 <span data-ttu-id="1040f-107"><xref:System.Xml.Schema.XmlAtomicValue> 또는 <xref:System.String> 형식을 사용하여 통합 형식을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1040f-107">Union types are represented using the <xref:System.Xml.Schema.XmlAtomicValue> or <xref:System.String> type.</span></span> <span data-ttu-id="1040f-108">그러므로 소스 형식 또는 대상 형식은 항상 <xref:System.String> 또는 <xref:System.Xml.Schema.XmlAtomicValue>여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1040f-108">The source type or the destination type must therefore always be either <xref:System.String> or <xref:System.Xml.Schema.XmlAtomicValue>.</span></span>  
  
 <span data-ttu-id="1040f-109"><xref:System.Xml.Schema.XmlSchemaDatatype> 개체가 목록 형식을 나타내는 경우 이 개체는 입력 문자열 값을 하나 이상의 개체 목록으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="1040f-109">If the <xref:System.Xml.Schema.XmlSchemaDatatype> object represents a list type the object converts the input string value to a list of one or more objects.</span></span> <span data-ttu-id="1040f-110"><xref:System.Xml.Schema.XmlSchemaDatatype>이 통합 형식을 나타내는 경우 입력 값을 통합 멤버 형식으로 구문 분석하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="1040f-110">If the <xref:System.Xml.Schema.XmlSchemaDatatype> represents a union type then an attempt is made to parse the input value as a member type of the union.</span></span> <span data-ttu-id="1040f-111">구문 분석이 실패하면 다음 통합 멤버로 변환이 시도되는 등 변환이 성공할 때까지 시도되며 시도할 다른 멤버 형식이 없으면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="1040f-111">If the parse attempt fails then the conversion is attempted with the next member of the union and so on until the conversion is successful, or there are no other member types to try, in which case an exception is thrown.</span></span>  
  
## <a name="differences-between-clr-and-xml-data-types"></a><span data-ttu-id="1040f-112">CLR 형식과 XML 데이터 형식의 차이</span><span class="sxs-lookup"><span data-stu-id="1040f-112">Differences Between CLR and XML Data Types</span></span>  
 <span data-ttu-id="1040f-113">다음에서는 CLR 형식과 XML 데이터 형식 간에 발생할 수 있는 불일치 및 이에 대한 처리 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1040f-113">The following describes certain mismatches that can occur between CLR types and XML data types and how they are handled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1040f-114">`xs` 접두사에 매핑되지는 http://www.w3.org/2001/XMLSchema 및 네임 스페이스 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="1040f-114">The `xs` prefix is mapped to the http://www.w3.org/2001/XMLSchema and namespace URI.</span></span>  
  
### <a name="systemtimespan-and-xsduration"></a><span data-ttu-id="1040f-115">System.TimeSpan 및 xs:duration</span><span class="sxs-lookup"><span data-stu-id="1040f-115">System.TimeSpan and xs:duration</span></span>  
 <span data-ttu-id="1040f-116">다르지만 동등한 특정 기간 값이 있다는 점에서 `xs:duration` 형식은 부분적으로 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="1040f-116">The `xs:duration` type is partially ordered in that there are certain duration values that are different but equivalent.</span></span> <span data-ttu-id="1040f-117">이는 `xs:duration` 형식의 경우 1개월(P1M)과 같은 값은 32일(P32D)보다 작고 27일(P27D)보다 크며 28일, 29일 또는 30일과 같음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="1040f-117">This means that for the `xs:duration` type value such as 1 month (P1M) is less than 32 days (P32D), larger than 27 days (P27D) and equivalent to 28, 29 or 30 days.</span></span>  
  
 <span data-ttu-id="1040f-118"><xref:System.TimeSpan> 클래스는 이러한 부분 정렬을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1040f-118">The <xref:System.TimeSpan> class does not support this partial ordering.</span></span> <span data-ttu-id="1040f-119">대신 이 클래스는 1년과 1개월에 대해 각각 365일과 30일의 특정 일 수를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1040f-119">Instead, it picks a specific number of days for 1 year and 1 month; 365 days and 30 days respectively.</span></span>  
  
 <span data-ttu-id="1040f-120">대 한 자세한 내용은 `xs:duration` 입력 W3C XML 스키마 2 부를 참조 하십시오: Datatypes 권장 사항을에서 http://www.w3.org/TR/xmlschema-2/합니다.</span><span class="sxs-lookup"><span data-stu-id="1040f-120">For more information on the `xs:duration` type, see the W3C XML Schema Part 2: Datatypes Recommendation at http://www.w3.org/TR/xmlschema-2/.</span></span>  
  
### <a name="xstime-gregorian-date-types-and-systemdatetime"></a><span data-ttu-id="1040f-121">xs:time, 양력 날짜 형식 및 System.DateTime</span><span class="sxs-lookup"><span data-stu-id="1040f-121">xs:time, Gregorian Date Types, and System.DateTime</span></span>  
 <span data-ttu-id="1040f-122">`xs:time` 값을 <xref:System.DateTime> 개체에 매핑하면 <xref:System.DateTime.MinValue> 필드를 사용하여 <xref:System.DateTime>, <xref:System.DateTime.Year%2A> 및 <xref:System.DateTime.Month%2A>와 같은 <xref:System.DateTime.Day%2A> 개체의 날짜 속성이 가능한 가장 작은 <xref:System.DateTime> 값으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="1040f-122">When an `xs:time` value is mapped to a <xref:System.DateTime> object, the <xref:System.DateTime.MinValue> field is used to initialize the date properties of the <xref:System.DateTime> object (such as <xref:System.DateTime.Year%2A>, <xref:System.DateTime.Month%2A>, and <xref:System.DateTime.Day%2A>) to the smallest possible <xref:System.DateTime> value.</span></span>  
  
 <span data-ttu-id="1040f-123">마찬가지로 `xs:gMonth`, `xs:gDay`, `xs:gYear`, `xs:gYearMonth` 및 `xs:gMonthDay`의 인스턴스도 <xref:System.DateTime> 개체에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="1040f-123">Similarly, instances of `xs:gMonth`, `xs:gDay`, `xs:gYear`, `xs:gYearMonth` and `xs:gMonthDay` are also mapped to a <xref:System.DateTime> object.</span></span> <span data-ttu-id="1040f-124"><xref:System.DateTime> 개체에서 사용되지 않는 속성은 <xref:System.DateTime.MinValue>의 속성으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="1040f-124">Unused properties on the <xref:System.DateTime> object are initialized to those from <xref:System.DateTime.MinValue>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1040f-125">내용 형식이 <xref:System.DateTime.Year%2A?displayProperty=nameWithType>로 지정된 경우 `xs:gMonthDay` 값을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1040f-125">You cannot rely on the <xref:System.DateTime.Year%2A?displayProperty=nameWithType> value when the content is typed as `xs:gMonthDay`.</span></span> <span data-ttu-id="1040f-126">이 경우 <xref:System.DateTime.Year%2A?displayProperty=nameWithType> 값은 항상 1904로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1040f-126">The <xref:System.DateTime.Year%2A?displayProperty=nameWithType> value is always set to 1904 in this case.</span></span>  
  
### <a name="xsanyuri-and-systemuri"></a><span data-ttu-id="1040f-127">xs:anyURI 및 System.Uri</span><span class="sxs-lookup"><span data-stu-id="1040f-127">xs:anyURI and System.Uri</span></span>  
 <span data-ttu-id="1040f-128">상대 URI를 나타내는 `xs:anyURI`의 인스턴스가 <xref:System.Uri>로 매핑될 경우에는 <xref:System.Uri> 개체에 기본 URI가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1040f-128">When an instance of `xs:anyURI` that represents a relative URI is mapped to a <xref:System.Uri>, the <xref:System.Uri> object does not have a base URI.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1040f-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1040f-129">See Also</span></span>  
 [<span data-ttu-id="1040f-130">System.Xml 클래스의 형식 지원</span><span class="sxs-lookup"><span data-stu-id="1040f-130">Type Support in the System.Xml Classes</span></span>](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md)
