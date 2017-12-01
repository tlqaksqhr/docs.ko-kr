---
title: "유지되지 않고 확장되는 엔터티 참조"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ffd97806-ab43-4538-8de2-5828bfbbde57
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 069d3b94a0269917400e75fdbe975ec39dcfdb71
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="entity-references-are-expanded-and-not-preserved"></a>유지되지 않고 확장되는 엔터티 참조
엔터티 참조가 확장 되어을 나타내는 텍스트로 **XmlEntityReference** 노드가 만들어지지 않습니다. 대신 엔터티 선언이 구문 분석 되 고 대신에 복사 되 고 선언의 내용에서 만든 노드는 **XmlEntityReference**합니다. 따라서는 `&publisher;` 예제에서는 `&publisher;` 저장 되지 않고, 대신는 **XmlText** 노드가 생성 됩니다.  
  
 ![트리 구조 확장](../../../../docs/standard/data/xml/media/xmlentityref-expanded-nodes.gif "xmlentityref_expanded_nodes")  
확장되는 엔터티 참조의 트리 구조  
  
 `B` 또는 `<` 같은 문자 엔터티는 유지되지 않습니다. 대신 항상 확장되어 텍스트 노드로 표현됩니다.  
  
 유지 하기 위해 **XmlEntityReference** 엔터티 참조의 자식 노드 및 노드 연결을 설정는 **EntityHandling** 플래그를 **ExpandCharEntities**합니다. 그렇지 않으면 둡니다는 **EntityHandling** 플래그를 하는 기본 **ExpandEntities**합니다. 이 경우 DOM에서 entityreference 노드가 유지되지 않습니다. 노드는 엔터티 선언의 자식 노드 복사본인 노드로 바뀝니다.  
  
 엔터티 참조를 유지하지 않는 경우 발생할 수 있는 부작용 중 하나는 문서를 저장하고 다른 응용 프로그램에 전달할 때 수신 응용 프로그램에서 노드가 엔터티 참조로 만들어졌다는 것을 알 수 없게 된다는 점입니다. 그러나 엔터티 참조를 유지하는 경우 수신 응용 프로그램에서 엔터티 참조를 인식하고 자식 노드를 읽습니다. 자식 노드가 엔터티 선언에 있던 정보를 나타내는 것은 분명합니다. 예를 들어, 엔터티 참조가 유지되는 경우 DOM은 이론적으로 다음과 같은 구조를 가집니다.  
  
 XmlElement: publisher  
  
 XmlEntityReference: `&publisher;`  
  
 XmlText: Microsoft Press  
  
 엔터티 참조가 DOM에서 확장되는 것이 기본 메서드이며 이 경우 다음 트리 형식의 구조를 갖습니다.  
  
 XmlElement: publisher  
  
 XmlText: Microsoft Press  
  
 엔터티 참조 노드는 사라지고 있고 수신 응용 프로그램 이라는 것을 알 수 없는 **XmlText** "Microsoft Press"를 포함 하는 노드가 엔터티 선언에서 생성 합니다.  
  
 엔터티를 확인할 수 없는 판독기를 사용 하는 경우는 **부하** 엔터티 참조를 발견 한 경우 메서드에서 예외를 throw 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [XML 문서 개체 모델 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
