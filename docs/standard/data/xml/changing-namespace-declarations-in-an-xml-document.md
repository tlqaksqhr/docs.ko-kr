---
title: "XML 문서에서 네임스페이스 선언 변경"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: a2758f40-e497-4964-8d8d-1bb68af14dcd
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 627882efcbc41310ee177cba984e4add5b07bd15
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="changing-namespace-declarations-in-an-xml-document"></a>XML 문서에서 네임스페이스 선언 변경
**XmlDocument** 네임 스페이스 선언을 노출 및 **xmlns** 문서 개체 모델의 일부로 특성입니다. 에 저장 됩니다는 **XmlDocument**이므로 문서를 저장 하면 해당 특성의 위치를 유지할 수 있습니다. 이러한 특성을 변경 해도 영향을 미치지 않습니다는 **이름**, **NamespaceURI**, 및 **접두사** 트리에 있는 다른 노드의의 속성입니다. 예를 들어, 다음 문서를 로드 하는 경우 다음의 `test` 요소에 **NamespaceURI**`123.`  
  
```xml  
<test xmlns="123"/>  
```  
  
 제거 하는 경우는 `xmlns` 특성을 다음과 같이 하면 `test` 요소에 아직는 **NamespaceURI** 의 `123`합니다.  
  
```vb  
doc.documentElement.RemoveAttribute("xmlns")  
```  
  
```csharp  
doc.documentElement.RemoveAttribute("xmlns");  
```  
  
 마찬가지로, 다른 추가 하는 경우 `xmlns` 특성을 `doc` 요소 다음과 같이 하면 `test` 요소에 아직 **NamespaceURI** `123`합니다.  
  
```vb  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
```csharp  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
 따라서 변경 `xmlns` 특성 저장 하 고 다시 로드 될 때까지 아무 영향도 주지 것입니다는 **XmlDocument** 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [XML 문서 개체 모델 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
