---
title: "DOM을 로드할 경우 공백 문자 및 유효 공백 문자 처리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1b141a0a-50d8-4ebd-83cd-a84449bb22b2
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 82401a18132801f9aa5368832b96be3cb67a8642
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="white-space-and-significant-white-space-handling-when-loading-the-dom"></a>DOM을 로드할 경우 공백 문자 및 유효 공백 문자 처리
문서를 로드할 때 공백을 유지 및 만들기 옵션을 설정할 수 있습니다 **XmlWhitespace** 문서 트리의 노드. 공백 노드를 만들려면 설정는 **PreserveWhitespace** 속성을 true로 합니다. 속성이로 설정 된 경우 **false**, 기본값, 공백 노드가 만들어지지 않습니다. 유효 공백 노드가 항상 유지 되 고 **XmlSignificantWhitespace** 노드가 항상의 설정에 관계 없이이 데이터를 나타내는 메모리에 생성 됩니다는 **PreserveWhitespace** 플래그입니다.  
  
 판독기에서 문서가 로드 되 면 다음의 설정 된 **PreserveWhitespace** 플래그 속성은 **XmlDocument** 클래스 생성에 영향을 줍니다 **XmlWhitespace** 노드 경우에만 **WhitespaceHandling** 속성에는 **XmlTextReader** 로 설정 되지 않은 **WhitespaceHandling.None**합니다. 값인는 **WhitespaceHandling** 속성에서의 플래그 설정 보다 우선 하는 판독기에는 **XmlDocument**합니다. 대 한 자세한 내용은 **XmlSignificantWhitespace**, 참조 <xref:System.Xml.XmlSignificantWhitespace>합니다.  
  
## <a name="see-also"></a>참고 항목  
 [XML 문서 개체 모델 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
