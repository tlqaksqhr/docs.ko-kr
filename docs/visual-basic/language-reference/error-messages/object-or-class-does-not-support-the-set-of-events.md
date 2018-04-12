---
title: 개체 또는 클래스가 이벤트 집합을 지원하지 않습니다.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: be4b9140222ef969bfb836fd74f45b8f662360b8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a>개체 또는 클래스가 이벤트 집합을 지원하지 않습니다.
사용 하려는 `WithEvents` 지정한 이벤트 집합에 대 한 이벤트 원본으로 작동할 수 없는 구성 요소와 변수입니다. 개체의 이벤트를 싱크한 다음 다른 개체를 만들 하려는 예를 들어 `Implements` 첫 번째 개체입니다. 하지만 구현 된 개체에서 이벤트를 싱크할 수 생각할 수 있습니다이 그렇지 않은 경우입니다. `Implements`만 메서드 및 속성에 대 한 인터페이스를 구현합니다. `WithEvents`개인에 대 한 지원 되지 않습니다 `UserControls`를 발생 시키는 데 필요한 형식 정보 때문에 `ObjectEvent` 런타임 시를 사용할 수 없습니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  이벤트 소스가 아닌 하는 구성 요소에 대 한 이벤트를 싱크할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)  
 [Implements 문](../../../visual-basic/language-reference/statements/implements-statement.md)
