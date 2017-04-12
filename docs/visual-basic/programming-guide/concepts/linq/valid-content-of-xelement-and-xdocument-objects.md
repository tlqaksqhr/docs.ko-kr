---
title: "XElement 및 XDocument Objects2의 올바른 콘텐츠 | Microsoft 문서"
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
ms.assetid: 400bb692-478a-40b6-ac1b-4ccbb4cbbd02
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f752ae346167709b95e758d15c1785ba7b6fcc5f
ms.lasthandoff: 03/13/2017

---
# <a name="valid-content-of-xelement-and-xdocument-objects"></a>XElement 및 XDocument 개체의 올바른 콘텐츠
이 항목에서는 생성자에 전달될 수 있는 유효한 인수에 대해 설명하고 내용을 요소와 문서에 추가하는 데 사용하는 메서드에 대한 정보를 제공합니다.  
  
## <a name="valid-content"></a>유효한 내용  
 쿼리는 종종 <xref:System.Collections.Generic.IEnumerable%601>또는 <xref:System.Xml.Linq.XElement> <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XAttribute>.</xref:System.Xml.Linq.XAttribute> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> 로 평가 컬렉션을 전달할 수 있습니다 <xref:System.Xml.Linq.XElement>또는 <xref:System.Xml.Linq.XAttribute>개체는 <xref:System.Xml.Linq.XElement>생성자.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement> 따라서 XML 트리를 채우는 데 사용하는 메서드와 생성자에 쿼리의 결과를 내용으로 전달하는 것이 편리합니다.  
  
 간단한 내용을 추가할 때 다양한 형식이 이 메서드에 전달될 수 있습니다. 유효한 형식은 다음과 같습니다.  
  
-   <xref:System.String></xref:System.String>  
  
-   <xref:System.Double></xref:System.Double>  
  
-   <xref:System.Single></xref:System.Single>  
  
-   <xref:System.Decimal></xref:System.Decimal>  
  
-   <xref:System.Boolean></xref:System.Boolean>  
  
-   <xref:System.DateTime></xref:System.DateTime>  
  
-   <xref:System.TimeSpan></xref:System.TimeSpan>  
  
-   <xref:System.DateTimeOffset></xref:System.DateTimeOffset>  
  
-   `Object.ToString`을 구현하는 임의의 형식  
  
-   <xref:System.Collections.Generic.IEnumerable%601>.</xref:System.Collections.Generic.IEnumerable%601> 를 구현 하는 형식  
  
 복잡한 내용을 추가할 때 다양한 형식이 이 메서드에 전달될 수 있습니다.  
  
-   <xref:System.Xml.Linq.XObject></xref:System.Xml.Linq.XObject>  
  
-   <xref:System.Xml.Linq.XNode></xref:System.Xml.Linq.XNode>  
  
-   <xref:System.Xml.Linq.XAttribute>  
  
-   구현 하는 모든 형식<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>  
  
 개체를 구현 하는 경우 <xref:System.Collections.Generic.IEnumerable%601>, 개체의 컬렉션이 열거 되 고 컬렉션의 모든 항목이 추가 됩니다.</xref:System.Collections.Generic.IEnumerable%601> 컬렉션에 있으면 <xref:System.Xml.Linq.XNode>또는 <xref:System.Xml.Linq.XAttribute>개체를 컬렉션의 각 항목은 개별적으로 추가 됩니다.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XNode> 컬렉션에 텍스트(또는 텍스트로 변환된 개체)가 포함되어 있으면 컬렉션의 텍스트가 연결되어 단일 텍스트 노드로 추가됩니다.  
  
 내용이 `null`이면 아무 것도 추가되지 않습니다. 컬렉션을 전달할 때 컬렉션의 항목은 `null`일 수 있습니다. 컬렉션의 `null` 항목은 트리에 아무 영향도 미치지 않습니다.  
  
 추가된 특성은 포함하는 요소에서 고유한 이름을 갖고 있어야 합니다.  
  
 추가 하는 경우 <xref:System.Xml.Linq.XNode>또는 <xref:System.Xml.Linq.XAttribute>개체를 새 내용에 부모가 없는 경우 다음 개체 되기만 XML 트리에.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XNode> 새 내용이 이미 부모를 갖고 있고 다른 XML 트리의 일부이면 새 내용이 복제되고 새로 복제된 내용이 XML 트리에 추가됩니다.  
  
## <a name="valid-content-for-documents"></a>문서의 유효한 내용  
 특성과 간단한 내용은 문서에 추가될 수 없습니다.  
  
 만들 <xref:System.Xml.Linq.XDocument>.</xref:System.Xml.Linq.XDocument> 을 해야 하는 시나리오도 있습니다. 대신 사용 하 여 XML 트리를 일반적으로 만들 수는 <xref:System.Xml.Linq.XElement>루트 노드.</xref:System.Xml.Linq.XElement> 하지 않는 한 문서를 만듭니다 (예를 들어 때문에 최상위 수준에서 처리 명령과 주석을 만들어야 하거나 문서 형식을 지원 해야 합니다.)는 특정 요구 사항,이 사용 하기 어려운 <xref:System.Xml.Linq.XElement>를 루트 노드로.</xref:System.Xml.Linq.XElement>  
  
 문서의 유효한 내용은 다음과 같습니다.  
  
-   0 개 또는 한 <xref:System.Xml.Linq.XDocumentType>개체.</xref:System.Xml.Linq.XDocumentType> 문서 형식이 요소 앞에 나와야 합니다.  
  
-   0개나&1;개의 요소  
  
-   0개 이상의 주석  
  
-   0개 이상의 처리 명령  
  
-   공백만 포함된&0;개 이상의 텍스트 노드  
  
## <a name="constructors-and-functions-that-allow-adding-content"></a>내용 추가를 허용하는 생성자 및 함수  
 다음 메서드를 사용 <xref:System.Xml.Linq.XElement>하거나 <xref:System.Xml.Linq.XDocument>::</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> 자식 콘텐츠를 추가할 수 있습니다.  
  
|메서드|설명|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.%23ctor%2A></xref:System.Xml.Linq.XElement.%23ctor%2A>|<xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> 를 생성합니다.|  
|<xref:System.Xml.Linq.XDocument.%23ctor%2A></xref:System.Xml.Linq.XDocument.%23ctor%2A>|<xref:System.Xml.Linq.XDocument>.</xref:System.Xml.Linq.XDocument> 를 생성합니다.|  
|<xref:System.Xml.Linq.XContainer.Add%2A></xref:System.Xml.Linq.XContainer.Add%2A>|자식 콘텐츠 <xref:System.Xml.Linq.XElement>또는 <xref:System.Xml.Linq.XDocument>.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> 의 끝에 추가|  
|<xref:System.Xml.Linq.XNode.AddAfterSelf%2A></xref:System.Xml.Linq.XNode.AddAfterSelf%2A>|<xref:System.Xml.Linq.XNode>.</xref:System.Xml.Linq.XNode> 후 콘텐츠를 추가합니다.|  
|<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A></xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>|<xref:System.Xml.Linq.XNode>.</xref:System.Xml.Linq.XNode> 앞에 내용을 추가합니다|  
|<xref:System.Xml.Linq.XContainer.AddFirst%2A></xref:System.Xml.Linq.XContainer.AddFirst%2A>|<xref:System.Xml.Linq.XContainer>.</xref:System.Xml.Linq.XContainer> 의 자식 내용 시작 부분에 내용을 추가합니다|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A></xref:System.Xml.Linq.XElement.ReplaceAll%2A>|<xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> 의 모든 콘텐츠 (자식 노드와 특성)를 대체합니다.|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A></xref:System.Xml.Linq.XElement.ReplaceAttributes%2A>|<xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> 의 특성을 대체합니다.|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A></xref:System.Xml.Linq.XContainer.ReplaceNodes%2A>|자식 노드를 새 내용으로 바꿉니다.|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A></xref:System.Xml.Linq.XNode.ReplaceWith%2A>|노드를 새 내용으로 바꿉니다.|  
  
## <a name="see-also"></a>참고 항목  
 [XML 트리 (Visual Basic) 만들기](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
