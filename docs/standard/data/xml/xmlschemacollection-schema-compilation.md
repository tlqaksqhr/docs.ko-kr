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
# <a name="xmlschemacollection-schema-compilation"></a>XmlSchemaCollection 스키마 컴파일
**XmlSchemaCollection** 캐시 또는 라이브러리 Xml-data Reduced (XDR) 및 XML 스키마 정의 언어 (XSD) 스키마를 저장 및 유효성을 검사할 수 있습니다. **XmlSchemaCollection** 스키마를 파일 또는 URL에 액세스 하는 대신 메모리에 캐시 하 여 성능을 향상 시킵니다.  
  
> [!NOTE]
>  하지만 **XmlSchemaCollection** 클래스 XDR 스키마와 모든 메서드 및 속성 사용 하거나 반환 하는 XML 스키마를 저장 한 **XmlSchema** 개체가 지 원하는 XML 스키마입니다.  
  
> [!IMPORTANT]
>  이제 <xref:System.Xml.Schema.XmlSchemaCollection> 클래스는 사용되지 않으며 <xref:System.Xml.Schema.XmlSchemaSet> 클래스로 대체되었습니다. 에 대 한 자세한 내용은 <xref:System.Xml.Schema.XmlSchemaSet> 클래스 참조 [스키마 컴파일을 위한 XmlSchemaSet](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)합니다.  
  
## <a name="add-schemas-to-the-collection"></a>컬렉션에 스키마 추가  
 스키마가 사용 하 여 컬렉션에 로드는 **추가** 방식의 **XmlSchemaCollection**, 될 때 스키마가 네임 스페이스 URI와 연결 합니다. XML 스키마의 경우 네임스페이스 URI는 일반적으로 스키마의 대상 네임스페이스입니다. XDR 스키마의 경우 네임스페이스 URI는 스키마를 컬렉션에 추가할 때 지정한 네임스페이스입니다.  
  
## <a name="check-for-a-schema-in-the-collection"></a>컬렉션의 스키마 확인  
 사용 하 여 스키마가 컬렉션에 있는지를 확인할 수 있습니다는 **Contains** 메서드. **Contains** 메서드에서 **XmlSchema** (XML 스키마와 XDR 스키마)에 대 한 스키마와 관련 된 (XML 스키마에만 해당)에 대 한 개체 또는 네임 스페이스 URI를 나타내는 문자열입니다.  
  
## <a name="retrieve-a-schema-from-the-collection"></a>컬렉션에서 스키마 검색  
 사용 하 여 컬렉션에서 스키마를 검색할 수는 **항목** 속성입니다. **항목** 속성 네임 스페이스 일반적으로 해당 대상 네임 스페이스를 스키마와 연결 된 URI를 나타내는 문자열을 사용 하 고 반환는 **XmlSchema** 개체입니다. **항목** 만 XML 스키마에 속성이 적용 됩니다. XDR 스키마에는 사용할 수 있는 개체 모델이 없기 때문에 반환 값은 항상 XDR 스키마에 대한 null 참조입니다.  
  
## <a name="validate-xml-documents-using-xmlschemacollection"></a>XmlSchemaCollection을 사용하여 XML 문서의 유효성 검사  
 XML 인스턴스 문서를 사용 하 여 유효성을 검사할 수 있습니다는 **XmlSchemaCollection** 만들어는 **XmlSchemaCollection** 개체, 스키마를 컬렉션에 추가 하 고 설정 된 **스키마**  속성에는 **XmlValidatingReader** 만든 할당할 **XmlSchemaCollection** 에 **XmlValidatingReader**합니다.  
  
### <a name="improved-performance"></a>향상된 성능  
 것이 좋습니다, 동일한 스키마에 대해 둘 이상의 문서의 유효성을 검사 하는 경우 사용 하는 **XmlSchemaCollection** 메모리의에서 스키마를 캐시 하 여 더 나은 성능을 제공 하기 때문에 있습니다.  
  
 다음 코드 예제에서는 **XmlSchemaCollection** 개체를 컬렉션에 스키마를 추가 하 고 설정 된 **스키마** 속성입니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [XmlSchemaCollection 사용 하 여 XDR 유효성](../../../../docs/standard/data/xml/xdr-validation-with-xmlschemacollection.md)  
 [XmlSchemaCollection는 XML 스키마 (XSD) 유효성 검사](../../../../docs/standard/data/xml/xml-schema-xsd-validation-with-xmlschemacollection.md)
