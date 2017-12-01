---
title: "요소 및 특성이 있는 새 노드의 엔터티 참조 확장에 대한 네임스페이스의 영향"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 64359aee-aab0-4042-9a32-d19789af6ca7
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 39110a9b44e6efbe7ad0331cfdb4fbe6078e7cfc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="namespace-affect-on-entity-reference-expansion-for-new-nodes-containing-elements-and-attributes"></a>요소 및 특성이 있는 새 노드의 엔터티 참조 확장에 대한 네임스페이스의 영향
엔터티 선언 내용은 거의 모든 항목을 포함할 수 있기 때문에 이 내용에 `<!ENTITY aname "<elem>test</elem>">`와 같은 요소가 포함될 가능성도 있습니다.  
  
 XML이 구문 분석될 때 `&aname;`은 구문 분석할 때의 대체 내용으로 확장되지 않습니다. 노드가 문서에 배치되지 않으면 요소에 대한 네임스페이스 확인 작업이 발생하지 않으므로 XML 확장이 수행되지 않습니다. 따라서 그전에는 범위에 있는 네임스페이스를 알 수 없습니다. 노드가 문서에 배치되면 네임스페이스 확인 작업이 발생하고 그에 따른 엔터티 내용이 해당 노드로 구문 분석됩니다.  
  
> [!NOTE]
>  새로 만들어진 entityreference 노드는 한 번 확장된 후에는 다시 확장되지 않습니다. 따라서 부모 노드가 설정될 때 요소의 대체 텍스트에서 사용된 네임스페이스가 바인딩됩니다. 그러나 복제 된 엔터티 참조 노드 또는 기존 엔터티 참조 노드 제거 하 고 다른 위치에 삽입에 대 한 네임 스페이스를 변경할 수는 **CloneNode** 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [XML 문서 개체 모델 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
