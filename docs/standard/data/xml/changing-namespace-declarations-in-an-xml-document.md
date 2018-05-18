---
title: XML 문서에서 네임스페이스 선언 변경
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: a2758f40-e497-4964-8d8d-1bb68af14dcd
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2fa41e8a4e8f5a15d789ddc81c2b94072c6f16b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="changing-namespace-declarations-in-an-xml-document"></a>XML 문서에서 네임스페이스 선언 변경
**XmlDocument**는 네임스페이스 선언 및 **xmlns** 특성을 문서 개체 모델의 일부로 표시합니다. 이러한 특성은 **XmlDocument**에 저장되므로 문서를 저장할 때 해당 특성의 위치를 유지할 수 있습니다. 이러한 특성을 변경해도 트리에 있는 다른 노드의 **Name**, **NamespaceURI** 및 **Prefix** 속성에는 영향을 주지 않습니다. 예를 들어, 다음과 같은 문서를 로드한다고 가정하면 `test` 요소의 **NamespaceURI**는 `123.`입니다.  
  
```xml  
<test xmlns="123"/>  
```  
  
 다음과 같이 `xmlns` 특성을 제거해도 `test` 요소의 **NamespaceURI**는 여전히 `123`입니다.  
  
```vb  
doc.documentElement.RemoveAttribute("xmlns")  
```  
  
```csharp  
doc.documentElement.RemoveAttribute("xmlns");  
```  
  
 마찬가지로 다음과 같이 `doc` 요소에 다른 `xmlns` 특성을 추가한다고 가정하더라도 `test` 요소의 **NamespaceURI**는 역시 `123`입니다.  
  
```vb  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
```csharp  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
 따라서 `xmlns` 특성을 변경해도 **XmlDocument** 개체를 저장하고 다시 로드하지 않는 한 아무 영향도 미치지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [XML DOM(문서 개체 모델)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
