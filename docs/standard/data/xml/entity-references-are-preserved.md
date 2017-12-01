---
title: "엔터티 참조 유지"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 000a6cae-5972-40d6-bd6c-a9b7d9649b3c
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 770c714e8f5942ea733c417ae9b06f69e4acf1a5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="entity-references-are-preserved"></a>엔터티 참조 유지
엔터티 참조가 확장 되지 않고, 유지 때 XML 문서 개체 모델 (DOM)에서는 **XmlEntityReference** 노드 엔터티 참조를 발견 한 경우.  
  
 다음 XML을 사용한다고 가정합니다.  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 DOM 빌드는 **XmlEntityReference** 에 도달할 때 노드는 `&publisher;` 참조 합니다. **XmlEntityReference** 엔터티 선언의 내용에서 복사 된 자식 노드를 포함 합니다. 이전 코드 예제에서는 엔터티 선언에 텍스트를 되므로 포함 한 **XmlText** entityreference 노드의 자식 노드로 노드가 만들어집니다.  
  
 ![트리 구조 유지 된 엔터티 참조에 대 한](../../../../docs/standard/data/xml/media/xmlentityref-notexpanded-nodes.gif "xmlentityref_notexpanded_nodes")  
유지되는 엔터티 참조의 트리 구조  
  
 자식 노드는 **XmlEntityReference** 은 모든 자식의 복사본에서 만든 노드는 **XmlEntity** 엔터티 선언이 발생 했을 때 노드.  
  
> [!NOTE]
>  복사한 노드는 **XmlEntity** 없는 경우가 entityreference 노드 아래의 정확히 복사 합니다. entityreference 노드 범위에 속한 네임스페이스가 있을 수 있으며 자식 노드의 최종 구성에 영향을 미칠 수 있습니다.  
  
 같은 일반 엔터티 기본적으로 `&abc;` 유지 및 **XmlEntityReference** 노드 항상 생성 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [XML 문서 개체 모델 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
