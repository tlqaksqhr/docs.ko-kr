---
title: "프로그래밍 가이드(LINQ to XML)(C#) | Microsoft 문서"
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
ms.assetid: 4b1ffd10-ab81-4a0d-a0ca-e9876478d924
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 5e1e95d92123b2874aace0c36005a8a07a6203fc
ms.contentlocale: ko-kr
ms.lasthandoff: 05/24/2017

---
# <a name="programming-guide-linq-to-xml-c"></a>프로그래밍 가이드(LINQ to XML)(C#)
이 단원에서는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]을 사용한 프로그래밍의 개념과 방법에 대해 설명합니다.  
  
## <a name="who-should-read-this-documentation"></a>이 설명서를 읽을 대상  
 이 설명서는 C#과 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]의 기본적인 내용을 알고 있는 개발자를 대상으로 합니다.  
  
 이 설명서의 목표는 모든 개발자가 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]을 쉽게 사용할 수 있도록 하는 것입니다. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]을 사용하면 XML을 쉽게 프로그래밍할 수 있습니다. 전문 개발자가 아니어도 LINQ to XML을 사용할 수 있습니다.  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]은 제네릭 클래스에 크게 의존하므로 제네릭 클래스의 사용에 대해 이해해야 합니다. 또한 매개 변수가 있는 형식으로 선언된 대리자에 대해 알고 있으면 도움이 됩니다. C# 제네릭 클래스에 대해 잘 모르는 경우에는 [제네릭 클래스](../../../../csharp/programming-guide/generics/generic-classes.md)를 참조하세요.  
  
## <a name="in-this-section"></a>단원 내용  
  
|항목|설명|  
|-----------|-----------------|  
|[LINQ to XML 프로그래밍 개요(C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)|[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 클래스에 대해 간략하게 설명하고 가장 중요한 클래스 중 <xref:System.Xml.Linq.XElement>, <xref:System.Xml.Linq.XAttribute> 및 <xref:System.Xml.Linq.XDocument> 클래스에 대해 자세히 설명합니다.|  
|[XML 트리 만들기(C#)](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)|XML 트리 생성의 개념과 작업에 대해 설명합니다. 함수 생성을 사용하거나 문자열이나 파일에서 XML 텍스트의 구문을 분석하여 XML 트리를 만들 수 있습니다. 또한 <xref:System.Xml.XmlReader>를 사용하여 XML 트리를 채울 수 있습니다.|  
|[XML 네임스페이스 작업(C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)|네임스페이스를 사용하는 XML 트리를 만드는 데 대해 자세히 설명합니다.|  
|[XML 트리 serialize(C#)](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)|XML 트리를 serialize하는 여러 방법에 대해 설명하고 사용할 방법에 대한 지침을 제공합니다.|  
|[LINQ to XML 축(C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)|[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 쿼리를 작성하기 전에 이해해야 하는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 축 메서드를 열거하고 설명합니다.|  
|[XML 트리 쿼리(C#)](../../../../csharp/programming-guide/concepts/linq/querying-xml-trees.md)|XML 트리를 쿼리하는 일반적인 예제를 제공합니다.|  
|[XML 트리 수정(LINQ to XML)(C#)](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)|DOM(문서 개체 모델)과 마찬가지로, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]을 통해서도 메모리 내 XML 트리를 수정할 수 있습니다.|  
|[고급 LINQ to XML 프로그래밍(C#)](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)|주석, 이벤트, 스트리밍 및 기타 고급 시나리오에 대해 설명합니다.|  
|[LINQ to XML 보안(C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-security.md)|LINQ to XML과 관련된 보안 문제에 대해 설명하고 보안 노출을 줄이기 위한 몇 가지 지침을 제공합니다.|  
|[샘플 XML 문서(LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-documents-linq-to-xml.md)|이 설명서의 많은 예제에서 사용하는 샘플 XML 문서가 포함되어 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [시작(LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/getting-started-linq-to-xml.md)   
 [LINQ to XML(C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml.md)
