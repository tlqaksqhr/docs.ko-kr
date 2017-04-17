---
title: "이벤트 디자인 | Microsoft Docs"
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
  - "사전 이벤트"
  - "이벤트 [.NET Framework] 디자인 지침"
  - "멤버 디자인 지침, 이벤트"
  - "이벤트 디자인 지침 이벤트 처리기 [.NET Framework]"
  - "사후 이벤트"
  - "서명, 이벤트 처리"
ms.assetid: 67b3c6e2-6a8f-480d-a78f-ebeeaca1b95a
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# 이벤트 디자인
이벤트는 \(사용자 코드를 호출 하는 프레임 워크를 사용할 수 있는 구문\) 콜백의 가장 자주 사용 되는 형태입니다. 다른 콜백 메커니즘 대리자, 가상 멤버 및 인터페이스 기반 플러그 인을 수행 하는 멤버를 포함 합니다. 유용성 연구의 데이터 대부분 개발자의 이벤트를 사용 하 여 다른 콜백 메커니즘을 사용 하는 것 보다 더 편한 지를 나타냅니다. 이벤트는 Visual Studio 및 다양 한 언어와 잘 통합 됩니다.  
  
 두 개의 그룹 이벤트에는 반드시: 상태의 시스템 변경 사항, 사전 이벤트 및 상태 변경 된 후 발생 한 이벤트를 호출 하기 전에 발생 한 이벤트 후 이벤트를 호출 합니다. 이전 이벤트의 예로 `Form.Closing`, 폼이 닫히기 전에 발생 하는 합니다. 이후 이벤트의 예로 `Form.Closed`, 는 폼이 닫힌 후 발생 하는 합니다.  
  
 **✓ 수행** "발생" 이라는 용어를 사용 하 여 이벤트 보다는 "발사" 또는 "트리거"입니다.  
  
 **✓ 수행** 사용 <xref:System.EventHandler%601?displayProperty=fullName> 수동으로 이벤트 처리기로 사용할 새 대리자를 만드는 대신 합니다.  
  
 **✓ 고려** 의 서브 클래스를 사용 하 여 <xref:System.EventArgs> 이벤트 인수로 제외 이벤트 데이터를 이벤트 처리 메서드를 필요가 없습니다를 확실히 있는 경우 사용할 수 있습니다는 `EventArgs` 직접 입력 합니다.  
  
 사용 하 여 API를 제공 하는 경우 `EventArgs` 를 직접 되지 됩니다를 이벤트와 호환성을 위반 하지 않고도 수행할 수 있는 모든 데이터를 추가할 수 있습니다. 하위 클래스를 사용 하는 경우에 처음 완전히 비어 있습니다 됩니다 필요할 때 하위 클래스에 속성을 추가할 수 있습니다.  
  
 **✓ 수행** 보호 된 가상 메서드를 사용 하 여 각 이벤트를 발생 합니다. 이 작업은 비정적 이벤트 봉인 되지 않은 클래스, 구조체, 봉인 된 클래스 또는 정적 이벤트에 적용할 수만 있습니다.  
  
 메서드의 목적은 재정의 사용 하는 이벤트를 처리 하는 파생된 클래스에 대 한 방법을 제공 하는 것입니다. 재정의 하는 것은 파생된 클래스에서 기본 클래스 이벤트를 처리 하는 보다 유연 하 고, 더 빠르고, 더 자연 스러운 방법입니다. 규칙에 따라 메서드의 이름이 "On"으로 시작 해야 하 고 이벤트의 이름으로 뒤에 올 합니다.  
  
 파생된 클래스 재정의 하는 메서드의 기본 구현을 호출 하지 않을 수 있습니다. 제대로 작동 하려면 기본 클래스에 대 한 실행 되어야 하는 방법에 처리를 포함 하 여이에 대비해 야.  
  
 **✓ 수행** 하나의 매개 변수는 이벤트를 발생 시키는 보호 된 메서드를 사용 합니다.  
  
 매개 변수 이름을 지정 해야 `e` 및 이벤트 인수 클래스로 입력 해야 합니다.  
  
 **X 하지 않으려면** 비정적 이벤트를 발생 시킬 때 보낸 사람으로 null을 전달 합니다.  
  
 **✓ 수행** 정적 이벤트를 발생 시킬 때 보낸 사람으로 null을 전달 합니다.  
  
 **X 하지 않으려면** 이벤트가 발생 하는 경우 이벤트 데이터 매개 변수로 null을 전달 합니다.  
  
 전달 해야 `EventArgs.Empty` 모든 데이터 이벤트 처리 메서드를 전달 하지 않을 경우. 개발자는이 매개 변수를 null이 될 수 없습니다.  
  
 **✓ 고려** 최종 사용자가 취소할 수 있는 이벤트를 발생 합니다. 이 사전 이벤트에만 적용 됩니다.  
  
 사용 하 여 <xref:System.ComponentModel.CancelEventArgs?displayProperty=fullName> 또는 최종 사용자 이벤트를 취소할 수 있도록 이벤트 인수로 해당 서브 클래스입니다.  
  
### 사용자 지정 이벤트 처리기 디자인  
 경우에는 `EventHandler<T>` 같은 프레임 워크를 제네릭을 지원 하지 않는 CLR의 이전 버전을 사용 해야 하는 경우 사용할 수 없습니다. 이러한 경우 디자인 하 고 사용자 지정 이벤트 처리기 대리자를 개발 해야 합니다.  
  
 **✓ 수행** 이벤트 처리기에 대 한 void의 반환 형식을 사용 합니다.  
  
 이벤트 처리기에 여러 이벤트 처리 수 있는 여러 개체에 메서드를 호출할 수 있습니다. 이벤트 처리 메서드가 값을 반환 하려면 허용 된 경우 각 이벤트 호출에 대해 여러 개의 반환 값 것입니다.  
  
 **✓ 수행** 사용 `object` 이벤트 처리기의 첫 번째 매개 변수의 형식으로이 호출 하 고 `sender`합니다.  
  
 **✓ 수행** 사용 <xref:System.EventArgs?displayProperty=fullName> 또는 해당 서브 클래스의 이벤트 처리기의 두 번째 매개 변수 형식으로이 호출 하 고 `e`합니다.  
  
 **X 하지 않으려면** 이벤트 처리기에는 두 개 이상의 매개 변수가 있습니다.  
  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [멤버 디자인 지침](../../../docs/standard/design-guidelines/member.md)   
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)