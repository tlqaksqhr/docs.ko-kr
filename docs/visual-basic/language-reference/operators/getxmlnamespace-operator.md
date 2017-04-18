---
title: "GetXmlNamespace 연산자 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.GetXmlNamespace
- GetXmlNamespace
dev_langs:
- VB
helpviewer_keywords:
- GetXmlNamespace operator
- GetXmlNamespace keyword
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 929ba4edae9e155245228670424a3898896da807
ms.lasthandoff: 03/13/2017

---
# <a name="getxmlnamespace-operator-visual-basic"></a>GetXmlNamespace 연산자(Visual Basic)
가져옵니다는 <xref:System.Xml.Linq.XNamespace>지정된 된 XML 네임 스페이스 접두사에 해당 하는 개체입니다.</xref:System.Xml.Linq.XNamespace>  
  
## <a name="syntax"></a>구문  
  
```  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## <a name="parts"></a>요소  
 `xmlNamespacePrefix`  
 선택적 요소. XML 네임 스페이스 접두사를 식별 하는 문자열입니다. 값을 제공 하는 경우이 문자열은 유효한 XML 식별자 여야 합니다. 자세한 내용은 참조 [이름의 선언 된 XML 요소 및 특성](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)합니다. 지정 된 접두사가 기본 네임 스페이스가 반환 됩니다. 기본 네임 스페이스를 지정 하는 경우에 빈 네임 스페이스가 반환 됩니다.  
  
## <a name="return-value"></a>반환 값  
 <xref:System.Xml.Linq.XNamespace>XML 네임 스페이스 접두사에 해당 하는 개체입니다.</xref:System.Xml.Linq.XNamespace>  
  
## <a name="remarks"></a>주의  
 `GetXmlNamespace` 연산자 가져옵니다는 <xref:System.Xml.Linq.XNamespace>XML 네임 스페이스 접두사에 해당 하는 개체 `xmlNamespacePrefix`.</xref:System.Xml.Linq.XNamespace>  
  
 XML 리터럴 및 XML 축 속성에서 직접 XML 네임 스페이스 접두사를 사용할 수 있습니다. 하지만 사용 해야는 `GetXmlNamespace` 네임 스페이스 접두사를 변환 하는 연산자는 <xref:System.Xml.Linq.XNamespace>전에 코드에서 사용할 수 있습니다.</xref:System.Xml.Linq.XNamespace> 정규화 되지 않은 요소 이름을 추가할 수는 <xref:System.Xml.Linq.XNamespace>개체를 가져올 정규화 된 <xref:System.Xml.Linq.XName>개체, 많은 [!INCLUDE[sqltecxlinq](../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 메서드에 필요.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XNamespace>  
  
## <a name="example"></a>예제  
 다음 예제에서는 `ns` XML 네임 스페이스 접두사로 합니다. 다음 네임 스페이스의 접두사는 XML 리터럴을 만들고 노드의 정규화 된 이름을 가진 첫 번째 자식 노드를 사용 하 여 `ns:phone`합니다. 그런 다음 해당 자식 노드를 전달는 `ShowName` 정규화 된 이름을 사용 하 여 생성 하는 서브루틴의 `GetXmlNamespace` 연산자입니다. `ShowName` 서브루틴은 다음에 정규화 된 이름을 전달는 <xref:System.Xml.Linq.XNode.Ancestors%2A>메서드를 부모 `ns:contact` 노드.</xref:System.Xml.Linq.XNode.Ancestors%2A>  
  
 [!code-vb[VbXMLSamples #&38;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/getxmlnamespace-operator_1.vb)]  
  
 호출 하는 경우 `TestGetXmlNamespace.RunSample()`, 다음 텍스트가 포함 된 메시지 상자가 표시 됩니다.  
  
 `Name: Patrick Hines`  
  
## <a name="see-also"></a>참고 항목  
 [Imports 문 (XML Namespace)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)   
 [Visual Basic의 XML에 액세스](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
