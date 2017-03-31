---
title: "방법: 구문 분석 오류 Catch(C#) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: bfb612d4-5605-48ef-8c93-915cf9d5dcfb
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: bf9469a328d80cca95fc5da2b143a494490089c2
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-catch-parsing-errors-c"></a>방법: 구문 분석 오류 Catch(C#)
이 항목에서는 잘못 구성되었거나 유효하지 않은 XML을 검색하는 방법을 보여 줍니다.  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]는 <xref:System.Xml.XmlReader>를 사용하여 구현됩니다. 잘못 구성되었거나 유효하지 않은 XML이 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]에 전달되면 기본 <xref:System.Xml.XmlReader> 클래스에서 예외를 throw합니다. XML의 구문을 분석하는 <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>과 같은 다양한 메서드는 예외를 catch하지 않습니다. 예외는 응용 프로그램에 의해 catch될 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 유효하지 않은 XML의 구문 분석을 시도합니다.  
  
```csharp  
try {  
    XElement contacts = XElement.Parse(  
        @"<Contacts>  
            <Contact>  
                <Name>Jim Wilson</Name>  
            </Contact>  
          </Contcts>");  
  
    Console.WriteLine(contacts);  
}  
catch (System.Xml.XmlException e)  
{  
    Console.WriteLine(e.Message);  
}  
```  
  
 이 코드를 실행하면 다음 예외가 throw됩니다.  
  
```  
The 'Contacts' start tag on line 1 does not match the end tag of 'Contcts'. Line 5, position 13.  
```  
  
 <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName> 및 <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName> 메서드가 throw할 수 있는 예외에 대한 자세한 내용은 <xref:System.Xml.XmlReader> 문서를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [XML 구문 분석(C#)](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)
