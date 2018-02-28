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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9b59f85eb0ef6646345eaef2a409f622c6fe4651
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="namespace-affect-on-entity-reference-expansion-for-new-nodes-containing-elements-and-attributes"></a>요소 및 특성이 있는 새 노드의 엔터티 참조 확장에 대한 네임스페이스의 영향
엔터티 선언 내용은 거의 모든 항목을 포함할 수 있기 때문에 이 내용에 `<!ENTITY aname "<elem>test</elem>">`와 같은 요소가 포함될 가능성도 있습니다.  
  
 XML이 구문 분석될 때 `&aname;`은 구문 분석할 때의 대체 내용으로 확장되지 않습니다. 노드가 문서에 배치되지 않으면 요소에 대한 네임스페이스 확인 작업이 발생하지 않으므로 XML 확장이 수행되지 않습니다. 따라서 그전에는 범위에 있는 네임스페이스를 알 수 없습니다. 노드가 문서에 배치되면 네임스페이스 확인 작업이 발생하고 그에 따른 엔터티 내용이 해당 노드로 구문 분석됩니다.  
  
> [!NOTE]
>  새로 만들어진 entityreference 노드는 한 번 확장된 후에는 다시 확장되지 않습니다. 따라서 부모 노드가 설정될 때 요소의 대체 텍스트에서 사용된 네임스페이스가 바인딩됩니다. 하지만 기존 엔터티 참조 노드를 제거하고 다른 위치에 삽입할 경우 또는 **CloneNode** 메서드로 복제된 엔터티 참조 노드의 경우 해당 노드의 네임스페이스가 변경될 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [XML DOM(문서 개체 모델)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
