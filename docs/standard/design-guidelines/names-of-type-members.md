---
title: "형식 멤버의 이름"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- events [.NET Framework], names
- methods [.NET Framework], names
- type members
- properties [.NET Framework], names
- fields, names
- field names
- names [.NET Framework], type members
- members [.NET Framework], type
ms.assetid: af5a0903-36af-4c2a-b848-cf959affeaa5
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1a3460b734d5bab6f5362fa9d3631e06821f6d49
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="names-of-type-members"></a>형식 멤버의 이름
형식 멤버의 내용이: 메서드, 속성, 이벤트, 생성자 및 필드입니다. 다음 섹션에서는 형식 멤버 이름 지정에 대 한 지침을 설명 합니다.  
  
## <a name="names-of-methods"></a>메서드의 이름  
 메서드 작업을 수행 하는 방법은 이기 때문에 디자인 지침도 록 요구할 메서드 이름이 동사 또는 동사 구입니다. 또한이 지침을 따르면 명사 또는 형용사 구 이름 속성에서 메서드 이름을 구분 하는 데 사용 합니다.  
  
 **✓ 않습니다** 동사 또는 동사 구 메서드 이름을 지정 합니다.  
  
```  
public class String {  
    public int CompareTo(...);  
    public string[] Split(...);  
    public string Trim();  
}  
```  
  
## <a name="names-of-properties"></a>속성의 이름  
 다른 멤버와 달리 형용사 명사나 명사구 속성 지정 되어야 합니다. 속성 데이터를 나타내며 속성의 이름을 반영 하는 때문입니다. PascalCasing 속성 이름에 항상 사용 됩니다.  
  
 **✓ 않습니다** 명사나 명사구, 형용사를 사용 하 여 속성 이름을 지정 합니다.  
  
 **하지 않으면 X** 다음 예제와 같이 "Get" 메서드의 이름과 일치 하는 속성이 있습니다.  
  
 `public string TextWriter { get {...} set {...} }`  
 `public string GetTextWriter(int value) { ... }`  
  
 이 패턴은 일반적으로 속성 메서드를 실제로 되어야 함을 나타냅니다.  
  
 **✓ 않습니다** 단 수 구문 "List" 또는 "컬렉션입니다." 다음을 사용 하는 대신 컬렉션의 항목을 설명 하는 복수 구문으로 컬렉션의 속성 이름  
  
 **✓ 않습니다** 찬성 구 사용 하는 부울 속성 이름은 (`CanSeek` 대신 `CantSeek`). 필요에 따라 붙일 수 있습니다. 또한 부울 속성 값을 추가 하는 경우에 하지만 "에" 또는 "Is", "을 수행할 수 있습니다,".  
  
 **✓ 고려** 속성 형식으로 동일한 이름을 지정 합니다.  
  
 예를 들어 다음과 같은 속성이 올바르게 가져오고 설정 이라는 enum 값 `Color`하므로 속성은 이름, `Color`:  
  
```  
public enum Color {...}  
public class Control {  
    public Color Color { get {...} set {...} }  
}  
```  
  
## <a name="names-of-events"></a>이벤트의 이름  
 이벤트를 발생 또는 발생 한 하나 작업을 항상 참조 합니다. 따라서 메서드의 경우와 마찬가지로 동사와 함께 이벤트 라고 하며 동사 시제 이벤트가 발생 한 경우 시간을 나타내는 데 사용 됩니다.  
  
 **✓ 않습니다** 동사 또는 동사 구를 사용 하 여 이벤트 이름을 지정 합니다.  
  
 예를 들면 `Clicked`, `Painting`, `DroppedDown`등입니다.  
  
 **✓ 않습니다** 부여의 개념을 사용 하 여 이벤트 이름을 이전 및 이후, 현재 및 과거 시제를 사용 하 여 합니다.  
  
 예를 들어 닫기 이벤트는 창이 닫히기 전에 발생 하는 호출 되 `Closing`, 하나는 창이 닫혀 있는 후에 발생 하는 호출 되 고 `Closed`합니다.  
  
 **X 하지 않으면** "Before" 또는 "After" 접두사 또는 접미어를 나타내는 사전 및 사후 이벤트를 사용 합니다. 사용 하 여 현재 및 과거 시제 앞서 설명한 합니다.  
  
 **✓ 않습니다** 다음 예제와 같이 "EventHandler" 접미사를 사용 이벤트 처리기 (이벤트 형식으로 사용 되는 대리자)의 이름을 지정 합니다.  
  
 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`  
  
 **✓ 않습니다** 의 두 매개 변수를 사용 하 여 `sender` 및 `e` 이벤트 처리기에 있습니다.  
  
 보낸 사람 매개 변수는 이벤트를 발생 시킨 개체를 나타냅니다. 보낸 사람 매개 변수는 일반적으로 형식 `object`를 더 구체적인 형식을 사용 하는 것이 불가능 한 경우에 합니다.  
  
 **✓ 않습니다** 이름을 이벤트 인수 클래스 "EventArgs" 접미사를 사용 합니다.  
  
## <a name="names-of-fields"></a>필드 이름  
 필드 이름 지정 지침 정적 공용 및 보호 된 필드에 적용 됩니다. 내부 및 전용 필드 지침을 다루지 않은 하 고 공용 또는 보호 된 인스턴스 필드에서 허용 되지 않습니다는 [멤버 디자인 지침](../../../docs/standard/design-guidelines/member.md)합니다.  
  
 **✓ 않습니다** PascalCasing 필드 이름에 사용할 수 있습니다.  
  
 **✓ 않습니다** 명사나 명사구, 형용사를 사용 하 여 필드 이름을 지정 합니다.  
  
 **X 하지 않으면** 필드 이름에 접두사를 사용 합니다.  
  
 예를 들어 사용 하지 마십시오 "g_" 또는 "s_" 정적 필드를 나타냅니다.  
  
 *일부 © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*  
  
 *피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*  
  
## <a name="see-also"></a>참고 항목  
 [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)  
 [명명 지침](../../../docs/standard/design-guidelines/naming-guidelines.md)
