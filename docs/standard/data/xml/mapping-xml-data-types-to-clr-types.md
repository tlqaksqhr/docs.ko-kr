---
title: CLR 형식에 XML 데이터 형식 매핑
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: cabdfcad-f359-479b-b71c-8b2fad42ca49
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d06876b91c72b939768d480e40631a8e85170bc9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="mapping-xml-data-types-to-clr-types"></a><span data-ttu-id="c3f52-102">CLR 형식에 XML 데이터 형식 매핑</span><span class="sxs-lookup"><span data-stu-id="c3f52-102">Mapping XML Data Types to CLR Types</span></span>
<span data-ttu-id="c3f52-103">다음 표에서는 XML 데이터 형식과 CLR(공용 언어 런타임) 형식 간의 기본 매핑에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c3f52-103">The following table describes the default mapping between the XML data types and the common language runtime (CLR) types.</span></span>  
  
## <a name="the-following-table-describes-the-default-mappings-of-an-xml-data-type-to-a-clr-type"></a><span data-ttu-id="c3f52-104">다음 표에서는 XML 데이터 형식을 CLR 형식으로 매핑하는 기본 매핑에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c3f52-104">The following table describes the default mappings of an XML data type to a CLR type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c3f52-105">`xs` 및 `xdt` 접두사는 각각 http://www.w3.org/2001/XMLSchema 및 http://www.w3.org/2003/05/xpath-datatypes 네임스페이스 URI로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3f52-105">The `xs` and the `xdt` prefixes are mapped to the http://www.w3.org/2001/XMLSchema and the http://www.w3.org/2003/05/xpath-datatypes namespace URIs respectively.</span></span>  
  
|<span data-ttu-id="c3f52-106">XML 형식</span><span class="sxs-lookup"><span data-stu-id="c3f52-106">XML Type</span></span>|<span data-ttu-id="c3f52-107">CLR 형식</span><span class="sxs-lookup"><span data-stu-id="c3f52-107">CLR Type</span></span>|  
|--------------|--------------|  
|`xs:anyURI`|<xref:System.Uri>|  
|`xs:base64Binary`|`Byte[]`|  
|`xs:boolean`|<xref:System.Boolean>|  
|`xs:byte`|<xref:System.SByte>|  
|`xs:date`|<xref:System.DateTime>|  
|`xs:dateTime`|<xref:System.DateTime>|  
|`xs:decimal`|<xref:System.Decimal>|  
|`xs:double`|<xref:System.Double>|  
|`xs:duration`|<xref:System.TimeSpan>|  
|`xs:ENTITIES`|`String[]`|  
|`xs:ENTITY`|<xref:System.String>|  
|`xs:float`|<xref:System.Single>|  
|`xs:gDay`|<xref:System.DateTime>|  
|`xs:gMonthDay`|<xref:System.DateTime>|  
|`xs:gYear`|<xref:System.DateTime>|  
|`xs:gYearMonth`|<xref:System.DateTime>|  
|`xs:hexBinary`|`Byte[]`|  
|`xs:ID`|<xref:System.String>|  
|`xs:IDREF`|<xref:System.String>|  
|`xs:IDREFS`|`String[]`|  
|`xs:int`|<xref:System.Int32>|  
|`xs:integer`|<xref:System.Decimal>|  
|`xs:language`|<xref:System.String>|  
|`xs:long`|<xref:System.Int64>|  
|`xs:gMmonth`|<xref:System.DateTime>|  
|`xs:Name`|<xref:System.String>|  
|`xs:NCName`|<xref:System.String>|  
|`xs:negativeInteger`|<xref:System.Decimal>|  
|`xs:NMTOKEN`|<xref:System.String>|  
|`xs:NMTOKENS`|`String[]`|  
|`xs:nonNegativeInteger`|<xref:System.Decimal>|  
|`xs:nonPositiveInteger`|<xref:System.Decimal>|  
|`xs:normalizedString`|<xref:System.String>|  
|`xs:NOTATION`|<xref:System.Xml.XmlQualifiedName>|  
|`xs:positiveInteger`|<xref:System.Decimal>|  
|`xs:QName`|<xref:System.Xml.XmlQualifiedName>|  
|`xs:short`|<xref:System.Int16>|  
|`xs:string`|<xref:System.String>|  
|`xs:time`|<xref:System.DateTime>|  
|`xs:token`|<xref:System.String>|  
|`xs:unsignedByte`|<xref:System.Byte>|  
|`xs:unsignedInt`|<xref:System.UInt32>|  
|`xs:unsignedLong`|<xref:System.UInt64>|  
|`xs:unsignedShort`|<xref:System.UInt16>|  
|`xdt:dayTimeDuration`|<xref:System.TimeSpan>|  
|`xdt:yearMonthDuration`|<xref:System.TimeSpan>|  
|`xdt:untypedAtomic`|<xref:System.String>|  
|`xdt:anyAtomicType`|<xref:System.Object>|  
|`xs:anySimpleType`|<xref:System.String>|  
|<span data-ttu-id="c3f52-108">문서 노드</span><span class="sxs-lookup"><span data-stu-id="c3f52-108">Document node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|  
|<span data-ttu-id="c3f52-109">요소 노드</span><span class="sxs-lookup"><span data-stu-id="c3f52-109">Element node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|  
|<span data-ttu-id="c3f52-110">특성 노드</span><span class="sxs-lookup"><span data-stu-id="c3f52-110">Attribute node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|  
|<span data-ttu-id="c3f52-111">네임스페이스 노드</span><span class="sxs-lookup"><span data-stu-id="c3f52-111">Namespace node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|  
|<span data-ttu-id="c3f52-112">텍스트 노드</span><span class="sxs-lookup"><span data-stu-id="c3f52-112">Text node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|  
|<span data-ttu-id="c3f52-113">주석 노드</span><span class="sxs-lookup"><span data-stu-id="c3f52-113">Comment node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|  
|<span data-ttu-id="c3f52-114">처리 명령 노드</span><span class="sxs-lookup"><span data-stu-id="c3f52-114">Processing instruction node</span></span>|<xref:System.Xml.XPath.XPathNavigator>|  
  
## <a name="see-also"></a><span data-ttu-id="c3f52-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c3f52-115">See Also</span></span>  
 [<span data-ttu-id="c3f52-116">System.Xml 클래스의 형식 지원</span><span class="sxs-lookup"><span data-stu-id="c3f52-116">Type Support in the System.Xml Classes</span></span>](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md)
