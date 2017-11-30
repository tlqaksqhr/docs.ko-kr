---
title: "XmlSchemaCollection을 사용하여 XDR 유효성 검사"
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
ms.assetid: 00833027-1428-4586-83c1-42f5de3323d1
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: fab67e10aa0562b59f8c7704a5ca1feeb66d6208
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="xdr-validation-with-xmlschemacollection"></a><span data-ttu-id="44153-102">XmlSchemaCollection을 사용하여 XDR 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="44153-102">XDR Validation with XmlSchemaCollection</span></span>
<span data-ttu-id="44153-103">에 대 한 유효성을 검사할 Xml-data Reduced (XDR) 스키마에 저장 되는 경우는 **XmlSchemaCollection**, URI 스키마 컬렉션에 추가할 때 지정한 네임 스페이스와 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44153-103">If the XML-Data Reduced (XDR) schema you are validating against is stored in the **XmlSchemaCollection**, it is associated with the namespace URI specified when the schema was added to the collection.</span></span> <span data-ttu-id="44153-104">**XmlValidatingReader** 컬렉션의 해당 URI에 해당 하는 스키마에 XML 문서에서 네임 스페이스 URI를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="44153-104">**XmlValidatingReader** maps the namespace URI in the XML document to the schema that corresponds to that URI in the collection.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="44153-105">이제 <xref:System.Xml.Schema.XmlSchemaCollection> 클래스는 사용되지 않으며 <xref:System.Xml.Schema.XmlSchemaSet> 클래스로 대체되었습니다.</span><span class="sxs-lookup"><span data-stu-id="44153-105">The <xref:System.Xml.Schema.XmlSchemaCollection> class is now obsolete and has been replaced with the <xref:System.Xml.Schema.XmlSchemaSet> class.</span></span> <span data-ttu-id="44153-106">에 대 한 자세한 내용은 <xref:System.Xml.Schema.XmlSchemaSet> 클래스 참조 [스키마 컴파일을 위한 XmlSchemaSet](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="44153-106">For more information about the <xref:System.Xml.Schema.XmlSchemaSet> class see, [XmlSchemaSet for Schema Compilation](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md).</span></span>  
  
 <span data-ttu-id="44153-107">예를 들어, XML 문서의 루트 요소가 `<bookstore xmlns="urn:newbooks-schema">`스키마에 추가 되 면는 **XmlSchemaCollection** 다음과 같이 동일한 네임 스페이스를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="44153-107">For example, if the root element of the XML document is `<bookstore xmlns="urn:newbooks-schema">`, when the schema is added to the **XmlSchemaCollection** it references the same namespace, as follows:</span></span>  
  
```  
xsc.Add("urn:newbooks-schema", "newbooks.xdr")  
```  
  
 <span data-ttu-id="44153-108">다음 코드 예제는 **XmlValidatingReader** 를 사용 하는 **XmlTextReader** 에 XDR 스키마 인 HeadCount.xdr을 추가 하 고는 **XmlSchemaCollection**합니다.</span><span class="sxs-lookup"><span data-stu-id="44153-108">The following code example creates an **XmlValidatingReader** that takes an **XmlTextReader** and adds an XDR schema, HeadCount.xdr, to the **XmlSchemaCollection**.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.Schema  
  
Namespace ValidationSample  
  
   Class Sample  
  
      Public Shared Sub Main()  
         Dim tr As New XmlTextReader("HeadCount.xml")  
         Dim vr As New XmlValidatingReader(tr)  
  
         vr.Schemas.Add("xdrHeadCount", "HeadCount.xdr")  
         vr.ValidationType = ValidationType.XDR  
         AddHandler vr.ValidationEventHandler, AddressOf ValidationHandler  
  
         While vr.Read()  
            PrintTypeInfo(vr)  
            If vr.NodeType = XmlNodeType.Element Then  
               While vr.MoveToNextAttribute()  
                  PrintTypeInfo(vr)  
               End While  
            End If  
         End While  
         Console.WriteLine("Validation finished")  
      End Sub  
      ' Main  
  
      Public Shared Sub PrintTypeInfo(vr As XmlValidatingReader)  
         If Not (vr.SchemaType Is Nothing) Then  
            If TypeOf vr.SchemaType Is XmlSchemaDatatype Or TypeOf vr.SchemaType Is XmlSchemaSimpleType Then  
               Dim value As Object = vr.ReadTypedValue()  
               Console.WriteLine("{0}({1},{2}):{3}", vr.NodeType, vr.Name, value.GetType().Name, value)  
            End If  
         End If  
      End Sub  
      ' PrintTypeInfo  
  
      Public Shared Sub ValidationHandler(sender As Object, args As ValidationEventArgs)  
         Console.WriteLine("***Validation error")  
         Console.WriteLine("Severity:{0}", args.Severity)  
         Console.WriteLine("Message:{0}", args.Message)  
      End Sub  
      ' ValidationHandler  
   End Class  
   ' Sample  
End Namespace  
' ValidationSample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.Schema;  
  
namespace ValidationSample  
{  
   class Sample  
   {  
      public static void Main()  
      {  
         XmlTextReader tr = new XmlTextReader("HeadCount.xml");  
         XmlValidatingReader vr = new XmlValidatingReader(tr);  
  
         vr.Schemas.Add("xdrHeadCount", "HeadCount.xdr");  
         vr.ValidationType = ValidationType.XDR;  
         vr.ValidationEventHandler += new ValidationEventHandler (ValidationHandler);  
  
         while(vr.Read())  
         {  
            PrintTypeInfo(vr);  
            if(vr.NodeType == XmlNodeType.Element)  
            {  
               while(vr.MoveToNextAttribute())  
                  PrintTypeInfo(vr);  
            }  
         }  
         Console.WriteLine("Validation finished");  
      }  
  
      public static void PrintTypeInfo(XmlValidatingReader vr)  
      {  
         if(vr.SchemaType != null)  
         {  
            if(vr.SchemaType is XmlSchemaDatatype || vr.SchemaType is XmlSchemaSimpleType)  
            {  
               object value = vr.ReadTypedValue();  
               Console.WriteLine("{0}({1},{2}):{3}", vr.NodeType, vr.Name, value.GetType().Name, value);  
            }  
         }  
      }  
  
      public static void ValidationHandler(object sender, ValidationEventArgs args)  
      {  
         Console.WriteLine("***Validation error");  
         Console.WriteLine("\tSeverity:{0}", args.Severity);  
         Console.WriteLine("\tMessage:{0}", args.Message);  
      }  
   }  
}  
```  
  
 <span data-ttu-id="44153-109">다음에서는 유효성을 검사할 입력 파일 HeadCount.xml의 내용을 요약합니다.</span><span class="sxs-lookup"><span data-stu-id="44153-109">The following outlines the contents of the input file, HeadCount.xml, to be validated.</span></span>  
  
```xml  
<!--Load HeadCount.xdr in SchemaCollection for Validation-->  
<HeadCount xmlns='xdrHeadCount'>  
   <Name>Waldo Pepper</Name>  
   <Name>Red Pepper</Name>  
</HeadCount>  
```  
  
 <span data-ttu-id="44153-110">다음에서는 유효성을 검사할 XDR 스키마 파일 HeadCound.xdr의 내용을 요약합니다.</span><span class="sxs-lookup"><span data-stu-id="44153-110">The following outlines the contents of the XDR schema file, HeadCount.xdr, to be validated against.</span></span>  
  
```xml  
<Schema xmlns="urn:schemas-microsoft-com:xml-data" xmlns:dt="urn:schemas-microsoft-com:datatypes">  
   <ElementType name="Name" content="textOnly"/>  
   <AttributeType name="Bldg" default="2"/>  
   <ElementType name="HeadCount" content="eltOnly">  
      <element type="Name"/>  
      <attribute type="Bldg"/>  
   </ElementType>  
</Schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="44153-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="44153-111">See Also</span></span>  
 <xref:System.Xml.XmlValidatingReader.ValidationType%2A>  
 <!--zz <xref:System.Xml.XmlValidatingReader.Settings%2A>-->  `System.Xml.XmlValidatingReader.Settings`  
 [<span data-ttu-id="44153-112">XmlSchemaCollection 스키마 컴파일</span><span class="sxs-lookup"><span data-stu-id="44153-112">XmlSchemaCollection Schema Compilation</span></span>](../../../../docs/standard/data/xml/xmlschemacollection-schema-compilation.md)
