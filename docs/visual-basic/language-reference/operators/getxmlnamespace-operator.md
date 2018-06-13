---
title: GetXmlNamespace 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
helpviewer_keywords:
- GetXmlNamespace operator [Visual Basic]
- GetXmlNamespace keyword [Visual Basic]
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
ms.openlocfilehash: e21cf160d10f308990894d1a85c4f5d05b90f68d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603485"
---
# <a name="getxmlnamespace-operator-visual-basic"></a>GetXmlNamespace 연산자(Visual Basic)
가져옵니다는 <xref:System.Xml.Linq.XNamespace> 지정된 된 XML 네임 스페이스 접두사에 해당 하는 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a>요소  
 `xmlNamespacePrefix`  
 선택 사항입니다. XML 네임 스페이스 접두사를 식별 하는 문자열입니다. 제공 된 경우이 문자열에 유효한 XML 식별자 여야 합니다. 자세한 내용은 참조 [이름을의 선언 된 XML 요소 및 특성](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)합니다. 지정 된 접두사가 기본 네임 스페이스가 반환 됩니다. 기본 네임 스페이스를 지정 하는 경우 빈 네임 스페이스가 반환 됩니다.  
  
## <a name="return-value"></a>반환 값  
 <xref:System.Xml.Linq.XNamespace> XML 네임 스페이스 접두사에 해당 하는 개체입니다.  
  
## <a name="remarks"></a>설명  
 `GetXmlNamespace` 연산자 가져옵니다는 <xref:System.Xml.Linq.XNamespace> XML 네임 스페이스 접두사에 해당 하는 개체 `xmlNamespacePrefix`합니다.  
  
 XML 리터럴 및 XML 축 속성에 직접 XML 네임 스페이스 접두사를 사용할 수 있습니다. 그러나 사용 해야 합니다는 `GetXmlNamespace` 네임 스페이스 접두사를 변환 하는 연산자는 <xref:System.Xml.Linq.XNamespace> 개체 코드에서 사용할 수 있습니다. 정규화 되지 않은 요소 이름을 추가할 수 있습니다는 <xref:System.Xml.Linq.XNamespace> 가져올 정규화 된 개체 <xref:System.Xml.Linq.XName> 개체, 많은 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 메서드에 필요 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `ns` XML 네임 스페이스 접두사로 합니다. 다음 네임 스페이스의 접두사는 XML 리터럴을 만들고 정규화 된 이름을 가진 첫 번째 자식 노드에 액세스를 사용 하 여 `ns:phone`합니다. 그런 다음 해당 자식 노드 전달는 `ShowName` 정규화 된 이름을 사용 하 여 생성 하는 서브루틴은 `GetXmlNamespace` 연산자입니다. `ShowName` 서브루틴은 다음에 정규화 된 이름을 전달는 <xref:System.Xml.Linq.XNode.Ancestors%2A> 부모를 가져올 메서드 `ns:contact` 노드.  
  
 [!code-vb[VbXMLSamples#38](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/getxmlnamespace-operator_1.vb)]  
  
 호출 하는 경우 `TestGetXmlNamespace.RunSample()`, 다음 텍스트를 포함 하는 메시지 상자가 표시 됩니다.  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a>참고 항목  
 [Imports 문(XML 네임스페이스)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)  
 [Visual Basic에서 XML에 액세스](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
