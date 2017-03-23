---
title: "방법: Catch 구문 분석 오류 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 22e9068e-ea58-447b-816e-cd1852c11787
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 0c4ba619d1f269352b3288f6cadf3b6f37a0dc2d
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-catch-parsing-errors-visual-basic"></a>방법: Catch 구문 분석 오류 (Visual Basic)
이 항목에서는 잘못 구성되었거나 유효하지 않은 XML을 검색하는 방법을 보여 줍니다.  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader> 를 사용 하 여 구현 됩니다. 잘못 구성 되었거나 유효 하지 않은 XML에 전달 되 면 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], 내부 <xref:System.Xml.XmlReader>클래스에는 예외가 throw 됩니다.</xref:System.Xml.XmlReader> 와 같은 XML의 구문을 분석 하는 다양 한 메서드 <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, 예외를 catch 하지 않습니다; 예외는 응용 프로그램에서 다음 낼 수 있습니다.</xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>  
  
 XML 리터럴을 사용하는 경우에는 구문 분석 오류를 가져올 수 없습니다. Visual Basic 컴파일러는 잘못 구성되었거나 유효하지 않은 XML의 오류를 catch합니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 유효하지 않은 XML의 구문 분석을 시도합니다.  
  
```vb  
Try  
    Dim contacts As XElement = XElement.Parse("<Contacts>" & vbCrLf & _  
        "    <Contact>" & vbCrLf & _  
        "        <Name>Jim Wilson</Name>" & vbCrLf & _  
        "    </Contact>" & vbCrLf & _  
        "</Contcts>")  
  
    Console.WriteLine(contacts)  
Catch e As System.Xml.XmlException  
    Console.WriteLine(e.Message)  
End Try  
```  
  
 이 코드를 실행하면 다음 예외가 throw됩니다.  
  
```  
The 'Contacts' start tag on line 1 does not match the end tag of 'Contcts'. Line 5, position 13.  
```  
  
 예상할 수 있는 예외에 대 한 내용은 <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>, 및 <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>를 throw 하는 메서드를 참조는 <xref:System.Xml.XmlReader>설명서.</xref:System.Xml.XmlReader> </xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName> </xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName> </xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName> </xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>  
  
## <a name="see-also"></a>참고 항목  
 [(Visual Basic) XML 구문 분석](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
