---
title: "XmlSchemaCollection 스키마 컴파일"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 76f28770-7126-428f-9ed5-7b5ae8bad5ee
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 901c3fdc8fdc80cc7c3bf13170646de857a5e009
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="xmlschemacollection-schema-compilation"></a><span data-ttu-id="88efb-102">XmlSchemaCollection 스키마 컴파일</span><span class="sxs-lookup"><span data-stu-id="88efb-102">XmlSchemaCollection Schema Compilation</span></span>
<span data-ttu-id="88efb-103">**XmlSchemaCollection** 캐시 또는 라이브러리 Xml-data Reduced (XDR) 및 XML 스키마 정의 언어 (XSD) 스키마를 저장 및 유효성을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88efb-103">The **XmlSchemaCollection** is a cache or library where XML-Data Reduced (XDR) and XML Schema definition language (XSD) schemas can be stored and validated.</span></span> <span data-ttu-id="88efb-104">**XmlSchemaCollection** 스키마를 파일 또는 URL에 액세스 하는 대신 메모리에 캐시 하 여 성능을 향상 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="88efb-104">**XmlSchemaCollection** improves performance by caching schemas in memory instead of accessing them from a file or URL.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="88efb-105">하지만 **XmlSchemaCollection** 클래스 XDR 스키마와 모든 메서드 및 속성 사용 하거나 반환 하는 XML 스키마를 저장 한 **XmlSchema** 개체가 지 원하는 XML 스키마입니다.</span><span class="sxs-lookup"><span data-stu-id="88efb-105">Although the **XmlSchemaCollection** class stores both XDR schemas and XML Schemas, any method and property that takes or returns an **XmlSchema** object supports XML Schemas only.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="88efb-106">이제 <xref:System.Xml.Schema.XmlSchemaCollection> 클래스는 사용되지 않으며 <xref:System.Xml.Schema.XmlSchemaSet> 클래스로 대체되었습니다.</span><span class="sxs-lookup"><span data-stu-id="88efb-106">The <xref:System.Xml.Schema.XmlSchemaCollection> class is now obsolete and has been replaced with the <xref:System.Xml.Schema.XmlSchemaSet> class.</span></span> <span data-ttu-id="88efb-107">에 대 한 자세한 내용은 <xref:System.Xml.Schema.XmlSchemaSet> 클래스 참조 [스키마 컴파일을 위한 XmlSchemaSet](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="88efb-107">For more information about the <xref:System.Xml.Schema.XmlSchemaSet> class see, [XmlSchemaSet for Schema Compilation](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md).</span></span>  
  
## <a name="add-schemas-to-the-collection"></a><span data-ttu-id="88efb-108">컬렉션에 스키마 추가</span><span class="sxs-lookup"><span data-stu-id="88efb-108">Add Schemas to the Collection</span></span>  
 <span data-ttu-id="88efb-109">스키마가 사용 하 여 컬렉션에 로드는 **추가** 방식의 **XmlSchemaCollection**, 될 때 스키마가 네임 스페이스 URI와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="88efb-109">Schemas are loaded to the collection using the **Add** method of **XmlSchemaCollection**, at which time the schema is associated with a namespace URI.</span></span> <span data-ttu-id="88efb-110">XML 스키마의 경우 네임스페이스 URI는 일반적으로 스키마의 대상 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="88efb-110">For XML Schemas, the namespace URI will typically be the target namespace for the schema.</span></span> <span data-ttu-id="88efb-111">XDR 스키마의 경우 네임스페이스 URI는 스키마를 컬렉션에 추가할 때 지정한 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="88efb-111">For XDR schemas, the namespace URI is the namespace specified when the schema was added to the collection.</span></span>  
  
## <a name="check-for-a-schema-in-the-collection"></a><span data-ttu-id="88efb-112">컬렉션의 스키마 확인</span><span class="sxs-lookup"><span data-stu-id="88efb-112">Check for a Schema in the Collection</span></span>  
 <span data-ttu-id="88efb-113">사용 하 여 스키마가 컬렉션에 있는지를 확인할 수 있습니다는 **Contains** 메서드.</span><span class="sxs-lookup"><span data-stu-id="88efb-113">You can check to see if a schema is in the collection by using the **Contains** method.</span></span> <span data-ttu-id="88efb-114">**Contains** 메서드에서 **XmlSchema** (XML 스키마와 XDR 스키마)에 대 한 스키마와 관련 된 (XML 스키마에만 해당)에 대 한 개체 또는 네임 스페이스 URI를 나타내는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="88efb-114">The **Contains** method takes either an **XmlSchema** object (for XML Schemas only) or a string representing the namespace URI associated with the schema (for XML Schemas and XDR schemas).</span></span>  
  
## <a name="retrieve-a-schema-from-the-collection"></a><span data-ttu-id="88efb-115">컬렉션에서 스키마 검색</span><span class="sxs-lookup"><span data-stu-id="88efb-115">Retrieve a Schema from the Collection</span></span>  
 <span data-ttu-id="88efb-116">사용 하 여 컬렉션에서 스키마를 검색할 수는 **항목** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="88efb-116">You can retrieve a schema from the collection by using the **Item** property.</span></span> <span data-ttu-id="88efb-117">**항목** 속성 네임 스페이스 일반적으로 해당 대상 네임 스페이스를 스키마와 연결 된 URI를 나타내는 문자열을 사용 하 고 반환는 **XmlSchema** 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="88efb-117">The **Item** property takes a string representing the namespace URI associated with the schema, typically its target namespace, and returns an **XmlSchema** object.</span></span> <span data-ttu-id="88efb-118">**항목** 만 XML 스키마에 속성이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88efb-118">The **Item** property applies to XML Schemas only.</span></span> <span data-ttu-id="88efb-119">XDR 스키마에는 사용할 수 있는 개체 모델이 없기 때문에 반환 값은 항상 XDR 스키마에 대한 null 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="88efb-119">The return value is always a null reference for XDR schemas because they do not have an object model available.</span></span>  
  
## <a name="validate-xml-documents-using-xmlschemacollection"></a><span data-ttu-id="88efb-120">XmlSchemaCollection을 사용하여 XML 문서의 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="88efb-120">Validate XML Documents Using XmlSchemaCollection</span></span>  
 <span data-ttu-id="88efb-121">XML 인스턴스 문서를 사용 하 여 유효성을 검사할 수 있습니다는 **XmlSchemaCollection** 만들어는 **XmlSchemaCollection** 개체, 스키마를 컬렉션에 추가 하 고 설정 된 **스키마**  속성에는 **XmlValidatingReader** 만든 할당할 **XmlSchemaCollection** 에 **XmlValidatingReader**합니다.</span><span class="sxs-lookup"><span data-stu-id="88efb-121">You can validate an XML instance document using an **XmlSchemaCollection** by creating the **XmlSchemaCollection** object, adding your schemas to the collection, and setting the **Schemas** property on the **XmlValidatingReader** to assign the created **XmlSchemaCollection** to the **XmlValidatingReader**.</span></span>  
  
### <a name="improved-performance"></a><span data-ttu-id="88efb-122">향상된 성능</span><span class="sxs-lookup"><span data-stu-id="88efb-122">Improved Performance</span></span>  
 <span data-ttu-id="88efb-123">것이 좋습니다, 동일한 스키마에 대해 둘 이상의 문서의 유효성을 검사 하는 경우 사용 하는 **XmlSchemaCollection** 메모리의에서 스키마를 캐시 하 여 더 나은 성능을 제공 하기 때문에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88efb-123">It is recommended, if you are validating more than one document against the same schema, that you use the **XmlSchemaCollection** because it provides better performance by caching schemas in memory.</span></span>  
  
 <span data-ttu-id="88efb-124">다음 코드 예제에서는 **XmlSchemaCollection** 개체를 컬렉션에 스키마를 추가 하 고 설정 된 **스키마** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="88efb-124">The following code example creates the **XmlSchemaCollection** object, adds schemas to the collection, and sets the **Schemas** property.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="88efb-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="88efb-125">See Also</span></span>  
 [<span data-ttu-id="88efb-126">XmlSchemaCollection 사용 하 여 XDR 유효성</span><span class="sxs-lookup"><span data-stu-id="88efb-126">XDR Validation with XmlSchemaCollection</span></span>](../../../../docs/standard/data/xml/xdr-validation-with-xmlschemacollection.md)  
 [<span data-ttu-id="88efb-127">XmlSchemaCollection는 XML 스키마 (XSD) 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="88efb-127">XML Schema (XSD) Validation with XmlSchemaCollection</span></span>](../../../../docs/standard/data/xml/xml-schema-xsd-validation-with-xmlschemacollection.md)
