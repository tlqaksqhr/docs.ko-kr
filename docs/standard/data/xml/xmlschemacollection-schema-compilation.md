---
title: XmlSchemaCollection 스키마 컴파일
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 76f28770-7126-428f-9ed5-7b5ae8bad5ee
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d64443f213603b1f5db9c256acc88e998e3f009a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="xmlschemacollection-schema-compilation"></a><span data-ttu-id="f96f4-102">XmlSchemaCollection 스키마 컴파일</span><span class="sxs-lookup"><span data-stu-id="f96f4-102">XmlSchemaCollection Schema Compilation</span></span>
<span data-ttu-id="f96f4-103">**XmlSchemaCollection**은 XDR(XML 데이터 축소) 및 XSD(XML 스키마 정의 언어) 스키마를 저장하고 유효성 검사를 수행할 수 있는 캐시 또는 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="f96f4-103">The **XmlSchemaCollection** is a cache or library where XML-Data Reduced (XDR) and XML Schema definition language (XSD) schemas can be stored and validated.</span></span> <span data-ttu-id="f96f4-104">**XmlSchemaCollection**에서는 파일이나 URL에서 스키마에 액세스하는 대신 메모리에 있는 스키마를 캐시하여 성능을 향상시킵니다.</span><span class="sxs-lookup"><span data-stu-id="f96f4-104">**XmlSchemaCollection** improves performance by caching schemas in memory instead of accessing them from a file or URL.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f96f4-105">**XmlSchemaCollection** 클래스에서 XDR 스키마와 XML 스키마를 모두 저장하더라도 **XmlSchema** 개체를 사용하거나 반환하는 메서드 및 속성에서는 XML 스키마만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f96f4-105">Although the **XmlSchemaCollection** class stores both XDR schemas and XML Schemas, any method and property that takes or returns an **XmlSchema** object supports XML Schemas only.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f96f4-106">이제 <xref:System.Xml.Schema.XmlSchemaCollection> 클래스는 사용되지 않으며 <xref:System.Xml.Schema.XmlSchemaSet> 클래스로 대체되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f96f4-106">The <xref:System.Xml.Schema.XmlSchemaCollection> class is now obsolete and has been replaced with the <xref:System.Xml.Schema.XmlSchemaSet> class.</span></span> <span data-ttu-id="f96f4-107"><xref:System.Xml.Schema.XmlSchemaSet> 클래스에 대한 자세한 내용은 [스키마 컴파일을 위한 XmlSchemaSet](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f96f4-107">For more information about the <xref:System.Xml.Schema.XmlSchemaSet> class see, [XmlSchemaSet for Schema Compilation](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md).</span></span>  
  
## <a name="add-schemas-to-the-collection"></a><span data-ttu-id="f96f4-108">컬렉션에 스키마 추가</span><span class="sxs-lookup"><span data-stu-id="f96f4-108">Add Schemas to the Collection</span></span>  
 <span data-ttu-id="f96f4-109">스키마가 네임스페이스 URI에 연결될 때 **XmlSchemaCollection**의 **Add** 메서드를 사용하여 스키마가 컬렉션에 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="f96f4-109">Schemas are loaded to the collection using the **Add** method of **XmlSchemaCollection**, at which time the schema is associated with a namespace URI.</span></span> <span data-ttu-id="f96f4-110">XML 스키마의 경우 네임스페이스 URI는 일반적으로 스키마의 대상 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="f96f4-110">For XML Schemas, the namespace URI will typically be the target namespace for the schema.</span></span> <span data-ttu-id="f96f4-111">XDR 스키마의 경우 네임스페이스 URI는 스키마를 컬렉션에 추가할 때 지정한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="f96f4-111">For XDR schemas, the namespace URI is the namespace specified when the schema was added to the collection.</span></span>  
  
## <a name="check-for-a-schema-in-the-collection"></a><span data-ttu-id="f96f4-112">컬렉션의 스키마 확인</span><span class="sxs-lookup"><span data-stu-id="f96f4-112">Check for a Schema in the Collection</span></span>  
 <span data-ttu-id="f96f4-113">**Contains** 메서드를 사용하여 스키마가 컬렉션에 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f96f4-113">You can check to see if a schema is in the collection by using the **Contains** method.</span></span> <span data-ttu-id="f96f4-114">**Contains** 메서드에서는 **XmlSchema** 개체(XML 스키마에만 해당) 또는 스키마와 연결된 네임스페이스 URI를 나타내는 문자열(XML 스키마와 XDR 스키마의 경우)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f96f4-114">The **Contains** method takes either an **XmlSchema** object (for XML Schemas only) or a string representing the namespace URI associated with the schema (for XML Schemas and XDR schemas).</span></span>  
  
## <a name="retrieve-a-schema-from-the-collection"></a><span data-ttu-id="f96f4-115">컬렉션에서 스키마 검색</span><span class="sxs-lookup"><span data-stu-id="f96f4-115">Retrieve a Schema from the Collection</span></span>  
 <span data-ttu-id="f96f4-116">**Item** 속성을 사용하여 컬렉션에서 스키마를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f96f4-116">You can retrieve a schema from the collection by using the **Item** property.</span></span> <span data-ttu-id="f96f4-117">**Item** 속성은 스키마와 연결된 네임스페이스(일반적으로 해당 대상 네임스페이스) URI를 나타내는 문자열을 사용하여 **XmlSchema** 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f96f4-117">The **Item** property takes a string representing the namespace URI associated with the schema, typically its target namespace, and returns an **XmlSchema** object.</span></span> <span data-ttu-id="f96f4-118">**Item** 속성은 XML 스키마에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f96f4-118">The **Item** property applies to XML Schemas only.</span></span> <span data-ttu-id="f96f4-119">XDR 스키마에는 사용할 수 있는 개체 모델이 없기 때문에 반환 값은 항상 XDR 스키마에 대한 null 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="f96f4-119">The return value is always a null reference for XDR schemas because they do not have an object model available.</span></span>  
  
## <a name="validate-xml-documents-using-xmlschemacollection"></a><span data-ttu-id="f96f4-120">XmlSchemaCollection을 사용하여 XML 문서의 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="f96f4-120">Validate XML Documents Using XmlSchemaCollection</span></span>  
 <span data-ttu-id="f96f4-121">생성된 **XmlSchemaCollection**을 **XmlValidatingReader**에 할당하기 위해 **XmlSchemaCollection** 개체를 만들고, 스키마를 컬렉션에 추가하며, **XmlValidatingReader**의 **Schemas** 속성을 설정하여 **XmlSchemaCollection**을 사용하는 XML 인스턴스 문서의 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f96f4-121">You can validate an XML instance document using an **XmlSchemaCollection** by creating the **XmlSchemaCollection** object, adding your schemas to the collection, and setting the **Schemas** property on the **XmlValidatingReader** to assign the created **XmlSchemaCollection** to the **XmlValidatingReader**.</span></span>  
  
### <a name="improved-performance"></a><span data-ttu-id="f96f4-122">향상된 성능</span><span class="sxs-lookup"><span data-stu-id="f96f4-122">Improved Performance</span></span>  
 <span data-ttu-id="f96f4-123">동일한 스키마에서 두 개 이상의 문서에 대한 유효성을 검사하는 경우 메모리의 스키마를 캐시하여 더 나은 성능을 제공하므로 **XmlSchemaCollection**을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f96f4-123">It is recommended, if you are validating more than one document against the same schema, that you use the **XmlSchemaCollection** because it provides better performance by caching schemas in memory.</span></span>  
  
 <span data-ttu-id="f96f4-124">다음 코드 예제에서는 **XmlSchemaCollection** 개체를 만들고, 스키마를 컬렉션에 추가하며, **Schemas** 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f96f4-124">The following code example creates the **XmlSchemaCollection** object, adds schemas to the collection, and sets the **Schemas** property.</span></span>  
  
```vb  
Dim tr as XmlTextReader = new XmlTextReader("Books.xml")  
Dim vr as XmlValidatingReader = new XmlValidatingReader(tr)  
Dim xsc as XmlSchemaCollection = new XmlSchemaCollection  
xsc.Add("urn:bookstore-schema", "Books.xsd")  
vr.Schemas.Add(xsc)  
```  
  
```csharp  
XmlTextReader tr = new XmlTextReader("Books.xml");  
XmlValidatingReader vr = new XmlValidatingReader(tr);  
XmlSchemaCollection xsc = new XmlSchemaCollection();  
xsc.Add("urn:bookstore-schema", "Books.xsd");    
vr.Schemas.Add(xsc);  
```  
  
## <a name="see-also"></a><span data-ttu-id="f96f4-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f96f4-125">See Also</span></span>  
 [<span data-ttu-id="f96f4-126">XmlSchemaCollection을 사용하여 XDR 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="f96f4-126">XDR Validation with XmlSchemaCollection</span></span>](../../../../docs/standard/data/xml/xdr-validation-with-xmlschemacollection.md)  
 [<span data-ttu-id="f96f4-127">XmlSchemaCollection을 사용하여 XSD(XML 스키마) 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="f96f4-127">XML Schema (XSD) Validation with XmlSchemaCollection</span></span>](../../../../docs/standard/data/xml/xml-schema-xsd-validation-with-xmlschemacollection.md)
