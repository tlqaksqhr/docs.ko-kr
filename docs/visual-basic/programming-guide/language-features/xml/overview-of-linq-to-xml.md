---
title: "Overview of LINQ to XML in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "LINQ to XML [Visual Basic], about LINQ to XML"
  - "LINQ [Visual Basic], LINQ to XML"
ms.assetid: 01c62a79-6d58-468e-84fb-039c05947701
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Overview of LINQ to XML in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 XML 리터럴 또는 XML 축 속성을 통해 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)]을 지원합니다.  따라서 사용자의 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 코드에서 XML을 사용하여 작업할 때 친숙하고 편리한 구문을 활용할 수 있습니다. *XML 리터럴*을 사용하면 XML을 사용자 코드에 직접 포함할 수 있습니다.  *XML 축 속성*을 사용하면 자식 노드, 하위 노드 및 XML 리터럴 특성에 액세스할 수 있습니다.  자세한 내용은 [XML Literals Overview](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md) 및 [Accessing XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)를 참조하십시오.  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)]은 특히 [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext-md.md)]를 활용하도록 디자인된 메모리 내 XML 프로그래밍 API입니다.  [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] API를 호출할 수도 있지만 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]을 사용해야만 XML 리터럴을 선언하고 XML 축 속성에 직접 액세스할 수 있습니다.  
  
> [!NOTE]
>  XML 리터럴 및 XML 축 속성은 ASP.NET 페이지의 선언 코드에서 지원되지 않습니다.  Visual Basic XML 기능을 사용하려면 사용자 코드를 ASP.NET 응용 프로그램의 코드 숨김 페이지에 넣습니다.  
  
 ![비디오에 링크](../../../../csharp/programming-guide/concepts/linq/media/playvideo.png "PlayVideo") 관련 비디오 데모를 보려면 [How Do I: Get Started with LINQ to XML?](http://go.microsoft.com/fwlink/?LinkId=143034) 및 [How Do I: Create Excel Spreadsheets using LINQ to XML?](http://go.microsoft.com/fwlink/?LinkId=143536)을 참조하십시오.  
  
## XML 만들기  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 XML 트리를 만드는 데는 두 가지 방법이 있습니다.  코드에서 XML 리터럴을 직접 선언하거나 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] API를 사용하여 트리를 만들 수 있습니다.  두 가지 프로세스 모두 코드에 XML 트리의 최종 구조를 반영할 수 있습니다.  예를 들어 다음 코드 예제에서는 XML 요소를 만듭니다.  
  
 [!code-vb[VbXmlSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/overview-of-linq-to-xml_1.vb)]  
  
 자세한 내용은 [Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)를 참조하십시오.  
  
## XML 액세스 및 탐색  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 XML 구조를 액세스하고 탐색하기 위한 XML 축 속성을 제공합니다.  이 속성을 사용하면 XML 자식 요소 이름을 지정하여 XML 요소 및 특성에 액세스할 수 있습니다.  또는 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] 메서드를 명시적으로 호출하여 요소 및 특성을 탐색하고 찾는 방법이 있습니다.  예를 들어 다음 코드 예제에서는 XML 축 속성을 사용하여 XML 요소의 특성 및 자식 요소를 참조합니다.  코드 예제에서는 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] 쿼리를 사용하여 자식 요소를 검색하고 이를 XML 요소로 출력하여 효과적인 변환을 수행합니다.  
  
 [!code-vb[VbXmlSamples#8](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/overview-of-linq-to-xml_2.vb)]  
  
 자세한 내용은 [Accessing XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)를 참조하십시오.  
  
## XML 네임스페이스  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 `Imports` 문을 사용하여 전역 XML 네임스페이스에 대한 별칭을 지정합니다.  다음 예제에서는 `Imports` 문을 사용하여 XML 네임스페이스를 가져오는 방법을 보여 줍니다.  
  
 [!code-vb[VbXMLSamples#1](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/overview-of-linq-to-xml_3.vb)]  
  
 XML 축 속성에 액세스하고 XML 문서 및 요소에 대한 XML 리터럴을 선언할 때 XML 네임스페이스 별칭을 사용할 수 있습니다.  
  
 [GetXmlNamespace Operator](../../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)를 사용하여 특정 네임스페이스 접두사에 대한 <xref:System.Xml.Linq.XNamespace> 개체를 검색할 수 있습니다.  
  
 자세한 내용은 [Imports Statement \(XML Namespace\)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)을 참조하십시오.  
  
### XML 리터럴의 XML 네임스페이스 사용  
 다음 예제에서는 전역 네임스페이스인 `ns`를 사용하는 <xref:System.Xml.Linq.XElement> 개체를 만드는 방법을 보여 줍니다.  
  
 [!code-vb[VbXMLSamples#2](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/overview-of-linq-to-xml_4.vb)]  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 컴파일러는 `xmlns` 특성을 사용하여 XML 네임스페이스 별칭이 포함된 XML 리터럴을 XML 네임스페이스를 사용하기 위해 XML 표기를 사용하는 코드로 변환합니다.  컴파일이 완료되면 이전 단원 예제에 나온 코드는 다음 예제와 기본적으로 동일한 실행 코드를 만듭니다.  
  
 [!code-vb[VbXMLSamples#3](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/overview-of-linq-to-xml_5.vb)]  
  
### XML 축 속성의 XML 네임스페이스 사용  
 XML 리터럴에 선언된 XML 네임스페이스는 XML 축 속성에서는 사용할 수 없습니다.  그러나 전역 네임스페이스는 XML 축 속성에서 사용할 수 있습니다.  콜론을 사용하여 XML 네임스페이스 접두사와 로컬 요소 이름을 구분합니다.  예를 들면 다음과 같습니다.  
  
 [!code-vb[VbXMLSamples#4](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/overview-of-linq-to-xml_6.vb)]  
  
## 참고 항목  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Accessing XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)   
 [Manipulating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)