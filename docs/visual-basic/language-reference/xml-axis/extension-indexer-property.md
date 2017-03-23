---
title: "확장 인덱서 속성 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlPropertyExtensionIndexer
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
caps.latest.revision: 22
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 25f434a5b5f8caf013ad5f778897e4e98e3d825d
ms.lasthandoff: 03/13/2017

---
# <a name="extension-indexer-property-visual-basic"></a>확장명 인덱서 속성(Visual Basic)
컬렉션의 개별 요소에 액세스할 수 있도록 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
object(index)  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`object`|필수 요소. 쿼리 가능 컬렉션입니다. <xref:System.Collections.Generic.IEnumerable%601>또는 <xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601> 를 구현 하는 컬렉션, 즉|  
|(|필수 요소. 인덱서 속성의 시작을 나타냅니다.|  
|`index`|필수 요소. 컬렉션에 있는 요소의&0;부터 시작 위치를 지정 하는 정수 식입니다.|  
|)|필수 요소. 인덱서 속성의 끝을 나타냅니다.|  
  
## <a name="return-value"></a>반환 값  
 컬렉션에서 지정된 된 위치에서 개체 또는 `Nothing` 경우 인덱스가 범위를 벗어났습니다.  
  
## <a name="remarks"></a>주의  
 컬렉션의 개별 요소에 액세스 하는 확장 인덱서 속성을 사용할 수 있습니다. 이 인덱서 속성은 일반적으로 XML 축 속성의 출력에 사용 됩니다. XML 자식 및 XML 하위 축 속성의 컬렉션을 반환 합니다. <xref:System.Xml.Linq.XElement>개체 또는 특성 값입니다.</xref:System.Xml.Linq.XElement>  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러에 대 한 호출을 확장 인덱서 속성을 변환의`ElementAtOrDefault` 메서드. 배열 인덱서 달리는`ElementAtOrDefault` 메서드가 반환 `Nothing` 경우 인덱스가 범위를 벗어났습니다. 이 동작은 컬렉션의 요소 수를 쉽게 확인할 수 없는 경우에 유용 합니다.  
  
 이 인덱서 속성을 구현 하는 컬렉션에 대 한 확장 속성 처럼 <xref:System.Collections.Generic.IEnumerable%601>또는 <xref:System.Linq.IQueryable%601>: 인덱서 또는 기본 속성 컬렉션에 없는 경우에 사용 됩니다.</xref:System.Linq.IQueryable%601> </xref:System.Collections.Generic.IEnumerable%601>  
  
 컬렉션의 첫 번째 요소 값에 액세스 하려면 <xref:System.Xml.Linq.XElement>또는 <xref:System.Xml.Linq.XAttribute>개체, XML을 사용할 수 있습니다 `Value` 속성.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement> 자세한 내용은 참조 [XML 값 속성](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 컬렉션의 두 번째 자식 노드에 액세스 하는 확장 인덱서를 사용 하 여 <xref:System.Xml.Linq.XElement>개체.</xref:System.Xml.Linq.XElement> 이라는 모든 자식 요소를 가져오는 자식 축 속성을 사용 하 여 액세스 됩니다 `phone` 에 `contact` 개체입니다.  
  
 [!code-vb[VbXMLSamples #&24;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/extension-indexer-property_1.vb)]  
  
 이 코드의 텍스트는 다음과 같습니다.  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Xml.Linq.XElement>   
 [XML 축 속성](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [XML 리터럴](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Visual Basic에서 XML 만들기](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [XML 값 속성](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
