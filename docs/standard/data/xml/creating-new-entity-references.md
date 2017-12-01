---
title: "새 엔터티 참조 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a42f81b3-0403-4e34-b346-7d2129804e54
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 22e9b66f58275141cf9da154573ca43a0b90affc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="creating-new-entity-references"></a>새 엔터티 참조 만들기
**CreateEntityReference** 메서드를 새로 만들고 **XmlEntityReference** 노드. XML DOM(문서 개체 모델)에서는 참조될 엔터티 이름이 이미 선언되지 않았는지 확인합니다. 있는 경우, 자식 노드의 **XmlEntityReference** 노드가 엔터티 선언 노드에서 복사 됩니다. 일치하는 엔터티 선언이 없으면 entityreference 노드의 유일한 자식으로 빈 텍스트 노드가 추가됩니다. 때문에 자식 노드는 **XmlEntityReference** 노드는 다른 노드의 복사본, 이러한 자식 노드는 읽기 전용 이며 수정할 수 없습니다.  
  
 노드가 복사될 때 엔터티 참조가 있는 범위에 네임스페이스가 있을 수 있습니다. 이 네임스페이스는 생성되는 모든 요소 또는 특성 노드의 구성에 영향을 줍니다.  
  
> [!NOTE]
>  DOM에 자식 노드를 추가 **EntityReference** 삽입할 경우에는 **EntityReference** 노드를 문서입니다. 새로 만든 **EntityReference** 노드에 자식 노드가 없습니다.  
  
 경우에는 **XmlDataDocument** 는의 파생된 클래스는 **XmlDocument**, **XmlDataDocument** 엔터티 참조의 생성을 지원 하지 않습니다. 때문에 이것이 **EntityReference** 하위는 읽기 전용입니다. 자식은 **EntityReference** 노드 여러 지역에 걸쳐 있을 수 있습니다. 이 경우에 행의 일부 영역에 연결 된의 일부를 포함 하는 **EntityReference** 읽기 전용으로 설정 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [XML 문서 개체 모델 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
