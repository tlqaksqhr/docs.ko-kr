---
title: "XmlSchemaCollection을 사용하여 XDR 유효성 검사 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 00833027-1428-4586-83c1-42f5de3323d1
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# XmlSchemaCollection을 사용하여 XDR 유효성 검사
유효성을 검사하려는 XDR\(XML\-Data Reduced\) 스키마가 **XmlSchemaCollection**에 저장된 경우 스키마를 컬렉션에 추가할 때 지정한 네임스페이스 URI와 연관됩니다.  **XmlValidatingReader**에서는 XML 문서의 네임스페이스 URI를 컬렉션의 해당 URI에 상응하는 스키마로 매핑합니다.  
  
> [!IMPORTANT]
>  이제 <xref:System.Xml.Schema.XmlSchemaCollection> 클래스는 사용되지 않으며 <xref:System.Xml.Schema.XmlSchemaSet> 클래스로 대체되었습니다.  <xref:System.Xml.Schema.XmlSchemaSet> 클래스에 대한 자세한 내용은 [스키마 컴파일을 위한 XmlSchemaSet](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)를 참조하세요.  
  
 예를 들어, XML 문서의 루트 요소가 `<bookstore xmlns="urn:newbooks-schema">`일 경우 스키마를 **XmlSchemaCollection**에 추가하면 다음과 같이 동일한 네임스페이스를 참조합니다.  
  
```  
xsc.Add("urn:newbooks-schema", "newbooks.xdr")  
```  
  
 다음 코드 예제에서는 **XmlTextReader**를 사용하는 **XmlValidatingReader**를 만들고 XDR 스키마인 HeadCount.xdr을 **XmlSchemaCollection**에 추가합니다.  
  
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
  
 다음에서는 유효성을 검사할 입력 파일 HeadCount.xml의 내용을 요약합니다.  
  
```  
<!--Load HeadCount.xdr in SchemaCollection for Validation-->  
<HeadCount xmlns='xdrHeadCount'>  
   <Name>Waldo Pepper</Name>  
   <Name>Red Pepper</Name>  
</HeadCount>  
```  
  
 다음에서는 유효성을 검사할 XDR 스키마 파일 HeadCound.xdr의 내용을 요약합니다.  
  
```  
<Schema xmlns="urn:schemas-microsoft-com:xml-data" xmlns:dt="urn:schemas-microsoft-com:datatypes">  
   <ElementType name="Name" content="textOnly"/>  
   <AttributeType name="Bldg" default="2"/>  
   <ElementType name="HeadCount" content="eltOnly">  
      <element type="Name"/>  
      <attribute type="Bldg"/>  
   </ElementType>  
</Schema>  
```  
  
## 참고 항목  
 <xref:System.Xml.XmlValidatingReader.ValidationType%2A>   
 <xref:System.Xml.XmlValidatingReader.Settings%2A>   
 [XmlSchemaCollection 스키마 컴파일](../../../../docs/standard/data/xml/xmlschemacollection-schema-compilation.md)