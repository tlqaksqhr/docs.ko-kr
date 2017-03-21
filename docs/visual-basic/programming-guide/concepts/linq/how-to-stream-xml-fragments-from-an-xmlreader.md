---
title: "방법: XmlReader (Visual Basic)에서 XML 조각을 스트림 | Microsoft 문서"
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
ms.assetid: f67ce598-4a12-4dcb-9a07-24deca02a111
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
ms.openlocfilehash: c9c60bb4730ef6569390f76f63c40a2cbd1c9524
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-stream-xml-fragments-from-an-xmlreader-visual-basic"></a>방법: XmlReader (Visual Basic)에서 XML 조각 스트리밍
큰 XML 파일을 처리해야 하는 경우 전체 XML 트리를 메모리에 로드하는 것이 가능하지 않을 수 있습니다. 이 항목에서는 <xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader> 를 사용 하 여 조각을 스트림 하는 방법을 보여 줍니다.  
  
 사용 하는 가장 효과적인 방법 중 하나는 <xref:System.Xml.XmlReader>읽을 <xref:System.Xml.Linq.XElement>개체 사용자 지정 축 메서드를 직접 작성 하는 것입니다.</xref:System.Xml.Linq.XElement> </xref:System.Xml.XmlReader> 축 메서드는 일반적으로 컬렉션을 반환와 같은 <xref:System.Collections.Generic.IEnumerable%601>의 <xref:System.Xml.Linq.XElement>이 항목의 예제에서와 같이.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> 사용자 지정 축 메서드를 호출 하 여 XML 조각을 만든 후에 <xref:System.Xml.Linq.XNode.ReadFrom%2A>메서드를 사용 하 여 컬렉션을 반환 `yield return`.</xref:System.Xml.Linq.XNode.ReadFrom%2A> 이것은 사용자 지정 축 메서드에 지연된 실행 의미를 제공합니다.  
  
 XML 트리를 만들 때는 <xref:System.Xml.XmlReader>개체는 <xref:System.Xml.XmlReader>요소에 배치 되어야 합니다.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader> <xref:System.Xml.Linq.XNode.ReadFrom%2A>메서드는 요소의 닫는 태그를 읽을 때까지 반환 하지 않습니다.</xref:System.Xml.Linq.XNode.ReadFrom%2A>  
  
 부분 트리를 만들려는 경우를 인스턴스화할 수 있습니다는 <xref:System.Xml.XmlReader>, 변환 하려는 노드에 판독기를 배치는 <xref:System.Xml.Linq.XElement>트리를 선택한 다음 만들기는 <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement> </xref:System.Xml.XmlReader>  
  
 항목 [하는 방법: 헤더 정보 (Visual Basic)에 액세스할 수 있는 XML 조각 스트림](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md) 좀 더 복잡 한 문서를 스트림 하는 방법에 대 한 예제 및 정보를 포함 합니다.  
  
 항목 [하는 방법: 수행 스트리밍 변환의 큰 XML 문서 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-perform-streaming-transform-of-large-xml-documents.md) LINQ to XML 사용 하 여 작은 메모리 사용 공간을 유지 하면서 매우 큰 XML 문서를 변환 하는 예제입니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 사용자 지정 축 메서드를 만듭니다. [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리를 사용하여 이 메서드를 쿼리할 수 있습니다. 사용자 지정 축 메서드 `StreamRootChildDoc`는 반복되는 `Child` 요소가 있는 문서를 읽도록 특정하게 디자인된 메서드입니다.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 이 예제의 소스 문서는 매우 작습니다. `Child` 요소가 수백만 있더라도 이 예제에서는 여전히 작은 메모리 공간만 사용할 것입니다.  
  
## <a name="see-also"></a>참고 항목  
 [연습: Visual Basic에서 IEnumerable(Of T) 구현](../../../../visual-basic/programming-guide/language-features/control-flow/walkthrough-implementing-ienumerable-of-t.md)   
 [(Visual Basic) XML 구문 분석](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
