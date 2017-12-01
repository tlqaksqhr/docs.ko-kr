---
title: "XML DOM(문서 개체 모델) 계층 구조"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d187d4f-c76e-4223-a670-cc290783ce47
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6dec61860fba5815b1dae802d280e8df6628ab91
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="xml-document-object-model-dom-hierarchy"></a>XML DOM(문서 개체 모델) 계층 구조
다음 그림은 관련 위치에 클래스 이름과 함께 괄호 안에 W3C(World Wide Web 컨소시엄) 이름을 표시하여 XML DOM(문서 개체 모델)에 대한 클래스 계층 구조를 보여 줍니다.  
  
 ![XML 문서 개체 모델 &#40; DOM &#41; 계층 구조](../../../../docs/standard/data/xml/media/dom-class-hierarchy.gif "Dom_class_hierarchy")  
XML DOM(문서 개체 모델) 계층 구조  
  
 다음 클래스에서 상속 하지 않습니다는 **XmlNode**:  
  
-   **XmlImplementation**  
  
-   **XmlNamedNodeMap**  
  
-   **XmlNodeList**  
  
-   **XmlNodeChangedEventArgs**  
  
 **XmlImplementation** 클래스는 XML 문서를 만드는 데 사용 됩니다. 자세한 내용은 참조 [XML 문서 만들기](../../../../docs/standard/data/xml/xml-document-creation.md)합니다.  
  
 **XmlNamedNodeMap** 클래스를 순서가 지정 되지 않은 노드 집합을 처리 합니다. 자세한 내용은 참조 [이름 또는 인덱스 별로 정렬 되지 않은 노드 검색](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md)합니다.  
  
 **XmlNodeList** 클래스는 정렬 된 노드 목록을 처리 합니다. 자세한 내용은 참조 [인덱스 별로 정렬 된 노드 검색](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md)합니다.  
  
 **XmlNodeChangedEventArgs** 에 등록 된 이벤트 처리기를 처리 하는 클래스는 **XmlDocument**합니다. 자세한 내용은 참조 [XmlNodeChangedEventArgs를 사용한 XML 문서의 이벤트 처리](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md)합니다.  
  
 **XmlLinkedNode** 클래스에서 상속 **XmlNode**합니다. 메서드를 재정의 하기 위한 것 **XmlNode**:는 **PreviousSibling** 및 **NextSibling** 메서드. 이러한 재정의 된 메서드는 다음에서 상속 되며 사용 **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference**, 및 **XmlProcessingInstruction**, 이전 및 다음 형제 클래스인 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [XML 문서 개체 모델 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
