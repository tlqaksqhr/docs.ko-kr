---
title: "형식 멤버의 이름 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "이벤트 [.NET Framework] 이름"
  - "이름 메서드 [.NET Framework]"
  - "형식 멤버"
  - "[.NET Framework] 속성 이름"
  - "필드 이름"
  - "필드 이름"
  - "형식 멤버 이름 [.NET Framework]"
  - "형식의 멤버 [.NET Framework]"
ms.assetid: af5a0903-36af-4c2a-b848-cf959affeaa5
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# 형식 멤버의 이름
형식 멤버의 내용이: 메서드, 속성, 이벤트, 생성자 및 필드입니다. 다음 섹션에서는 형식 멤버 이름 지정에 대 한 지침을 설명 합니다.  
  
## 메서드 이름에  
 메서드는 작업을 수행 하는 방법은 이기 때문에 디자인 지침 메서드 이름은 동사 또는 동사 구 있도록 필요 합니다. 또한이 지침을 따르면 명사 또는 형용사 구 인 속성 및 형식 이름을 메서드 이름 구분 하기 위해 사용 됩니다.  
  
 **✓ 수행** 동사 또는 동사 구 메서드 이름을 지정 합니다.  
  
```  
public class String {  
    public int CompareTo(...);  
    public string[] Split(...);  
    public string Trim();  
}  
  
```  
  
## 속성의 이름  
 다른 멤버와 달리 형용사 명사나 명사구 속성 지정 되어야 합니다. 속성은 데이터를 참조 하 고 속성의 이름을 반영 하는 때문입니다. 속성 이름에 대 한 PascalCasing 항상 사용 됩니다.  
  
 **✓ 수행** 명사나 명사구, 형용사를 사용 하 여 속성 이름을 지정 합니다.  
  
 **X 하지 않으려면** 다음 예제와 같이 "Get" 메서드의 이름과 일치 하는 속성이 있습니다.  
  
 `public string TextWriter { get {...} set {...} }`   
 `public string GetTextWriter(int value) { ... }`  
  
 이 패턴은 일반적으로 속성 메서드를 실제로 되어야 함을 나타냅니다.  
  
 **✓ 수행** 컬렉션 속성 이름을 단 수 구문 "List" 또는 "컬렉션입니다." 다음을 사용 하는 대신 컬렉션의 항목을 설명 하는 복수 구를으로  
  
 **✓ 수행** 찬성 구문으로 부울 속성 이름을 \(`CanSeek` 대신 `CantSeek`\). 필요에 따라 붙일 수 있습니다. 또한 부울 속성 값을 추가 하는 경우에 하지만 "Has" 또는 "Is", "을 수행할 수 있습니다,"입니다.  
  
 **✓ 고려** 속성 유형으로 동일한 이름을 지정 합니다.  
  
 예를 들어, 다음과 같은 속성이 올바르게 가져오고 설정 이라는 enum 값 `Color`, 이므로 속성 이름은 `Color`:  
  
```  
public enum Color {...}  
public class Control {  
    public Color Color { get {...} set {...} }  
}  
```  
  
## 이벤트의 이름  
 이벤트는 항상 일이 일어납니다 하나 또는 하나 발생 한 몇 가지 작업을 참조 합니다. 따라서 메서드의 경우와 마찬가지로 동사와 함께 이벤트는 이름이 지정 되며 동사 시제 이벤트가 발생 하는 경우 시간을 나타내는 데 사용 됩니다.  
  
 **✓ 수행** 동사 또는 동사 구를 사용 하 여 이벤트 이름을 지정 합니다.  
  
 예를 들면 `Clicked`, 를`Painting`, 를`DroppedDown`, 등입니다.  
  
 **✓ 수행** 이벤트 이름을 부여의 개념을 이전 및 이후, 현재 및 과거 시제를 사용 하 여 합니다.  
  
 닫기 이벤트는 창이 닫히기 전에 발생 하는 호출 하는 예를 들어 `Closing`, 하나는 창이 닫혀 있는 후에 발생 하는 호출 되 고 `Closed`합니다.  
  
 **X 하지 않으려면** "Before" 또는 "After" 접두사 또는 접미어를 나타내는 사전 및 사후 이벤트를 사용 합니다. 사용 하 여 현재 및 과거 시제 위에서 설명한 대로입니다.  
  
 **✓ 수행** 다음 예제와 같이 "EventHandler" 접미사를 사용 이벤트 처리기 \(대리자 형식의 이벤트로 사용\)의 이름을 지정 합니다.  
  
 `public delegate void ClickedEventHandler(object sender, ClickedEventArgs e);`  
  
 **✓ 수행** 라는 두 개의 매개 변수를 사용 하 여 `sender` 및 `e` 이벤트 처리기에 있습니다.  
  
 Sender 매개 변수는 이벤트를 발생 시킨 개체를 나타냅니다. 보낸 사람에 게 매개 변수는 일반적으로 형식 `object`, 더 구체적인 형식을 사용 하는 것이 불가능 한 경우에 합니다.  
  
 **✓ 수행** 이름 이벤트 인수 클래스 "EventArgs" 접미사를 사용 합니다.  
  
## 필드 이름  
 필드 명명 규칙은 공용 및 보호 된 정적 필드에 적용 됩니다. 내부 및 전용 필드 지침에서 다루지 않는 및 공용 또는 보호 된 인스턴스 필드에서 허용 하지 않는 [멤버 디자인 지침](../../../docs/standard/design-guidelines/member.md)합니다.  
  
 **✓ 수행** PascalCasing 필드 이름에 사용할 수 있습니다.  
  
 **✓ 수행** 명사나 명사구, 형용사를 사용 하 여 필드 이름을 지정 합니다.  
  
 **X 하지 않으려면** 필드 이름에 접두사를 사용 합니다.  
  
 예를 들어, 사용 하지 마십시오 "g\_" 또는 "s" 정적 필드를 나타냅니다.  
  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)   
 [명명 지침](../../../docs/standard/design-guidelines/naming-guidelines.md)