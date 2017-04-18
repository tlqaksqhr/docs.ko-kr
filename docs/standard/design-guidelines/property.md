---
title: "속성 디자인 | Microsoft Docs"
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
  - "멤버 디자인 지침, 속성"
  - "디자인 지침 [.NET Framework] 속성"
ms.assetid: 127cbc0c-cbed-48fd-9c89-7c5d4f98f163
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# 속성 디자인
속성 메서드 기술적으로 매우 유사 하지만는 해당 사용 시나리오 측면에서 매우 다릅니다. 스마트 필드로 봐야 합니다. 필드가 호출 구문 및 메서드의 유연성을가지고 있습니다.  
  
 **✓ 수행** 호출자가 속성의 값을 변경할 수 없어야 하는 경우 가져오기 전용 속성을 만듭니다.  
  
 염두에서에 둬야 되는 경우의 형식 속성이 변경 가능한 참조 형식인, 경우에 속성이 가져오기 전용 속성 값을 변경할 수 있습니다.  
  
 **X 하지 않으려면** 설정 전용 속성 또는 속성 getter 보다 광범위 한 액세스 가능성을 가진 setter를 제공 합니다.  
  
 예를 들어은 공용 및 보호 된 getter 속성을 사용 하지 마십시오.  
  
 속성 getter를 제공할 수 없는 경우 대신 방법으로 기능을 구현 합니다. 메서드 이름에 시작 하는 것이 좋습니다. `Set` 하 고 뒤 무엇는 지정한 속성입니다. 예를 들어 <xref:System.AppDomain> 라는 메서드가 `SetCachePath` 라는 설정 전용 속성 대신 `CachePath`합니다.  
  
 **✓ 수행** 기본값 보안 허점이 나 그다지 비효율적인 코드에서 발생 하지 않으면 확인 하는 모든 속성에 대 한 적절 한 기본값을 제공 합니다.  
  
 **✓ 수행** 허용 속성을이 인해 임시 잘못 된 상태 개체의 경우에 순서에 관계 없이 설정할 수 있습니다.  
  
 수 있는 일부 한 속성 값을 잘못 되었을 수 지점에 서로 관련 된 두 개 이상의 속성에 대 한 일반적 동일한 개체에서 다른 속성의 값이 지정 됩니다. 이러한 경우 상호 관련 된 속성은 개체에서 함께 사용 실제로 될 때까지 잘못 된 상태에서 발생 한 예외를 연기 해야 합니다.  
  
 **✓ 수행** 속성 setter는 예외를 throw 하는 경우 이전 값을 유지 합니다.  
  
 **X 방지** 속성 getter에서 예외를 throw 합니다.  
  
 속성 getter 간단한 작업 및 사전 조건이 없어야 합니다. Getter 수에서 예외를 throw 하는 메서드가 되도록 아마도 재설계 해야 합니다. 인덱서, 예외는 인수 유효성 검사의 결과로 기대할 위치에이 규칙이 적용 되지 않습니다 확인 합니다.  
  
### 인덱싱된 속성 디자인  
 인덱싱된 속성에는 매개 변수를 포함 하 고 배열 인덱싱 유사한 특수 구문을 사용 하 여 호출 될 수 있는 특수 속성이입니다.  
  
 인덱싱된 속성은 일반적으로 인덱서 라고 합니다. 인덱서는 논리적 컬렉션의 항목에 대 한 액세스를 제공 하는 Api에만 사용 해야 합니다. 예를 들어, 문자열의 컬렉션인 문자와에 인덱서 <xref:System.String?displayProperty=fullName> 해당 문자에 액세스 하는 추가 되었습니다.  
  
 **✓ 고려** 인덱서를 사용 하 여 내부 배열에 저장 된 데이터에 대 한 액세스를 제공 합니다.  
  
 **✓ 고려** 컬렉션 항목을 나타내는 형식에 인덱서를 제공 합니다.  
  
 **X 방지** 를 사용 하 여 인덱싱된 속성 둘 이상의 매개 변수를 사용 합니다.  
  
 디자인에 여러 매개 변수가 필요한 경우 다시 속성 논리를 컬렉션에 실제로 접근자를 나타내는지 여부를 고려 합니다. 그렇지 않은 경우 대신 메서드를 사용 합니다. 메서드 이름에 시작 하는 것이 좋습니다. `Get` 또는 `Set`합니다.  
  
 **X 방지** 인덱서 매개 변수 형식 이외의 다른 <xref:System.Int32?displayProperty=fullName>, <xref:System.Int64?displayProperty=fullName>, <xref:System.String?displayProperty=fullName>, <xref:System.Object?displayProperty=fullName>, 또는 열거형입니다.  
  
 디자인에는 다른 형식의 매개 변수가 필요한 경우 다시 확인 API 논리를 컬렉션에 실제로 접근자를 나타내는지 여부를 합니다. 그렇지 않은 경우는 메서드를 사용 합니다. 메서드 이름에 시작 하는 것이 좋습니다. `Get` 또는 `Set`합니다.  
  
 **✓ 수행** 이름을 사용 하 여 `Item` 에 대 한 분명 더 알아보기 쉬운 이름에는 발생 하지 않으면 인덱싱된 속성 \(예: 참조는 <xref:System.String.Chars%2A> 속성을 `System.String`\).  
  
 C\#에서는 인덱서 항목 이름은 기본적으로는 합니다.<xref:System.Runtime.CompilerServices.IndexerNameAttribute> 이 이름을 사용자 지정 하는 것입니다.  
  
 **X 하지 않으려면** 인덱서와 의미 체계 상 동등한 되는 메서드를 제공 합니다.  
  
 **X 하지 않으려면** 개 이상의 제품군의 한 가지 형식으로 오버 로드 된 인덱서를 제공 합니다.  
  
 C\# 컴파일러에 의해 적용 됩니다.  
  
 **X 하지 않으려면** 사용 하 여 기본이 아닌 인덱싱된 속성입니다.  
  
 C\# 컴파일러에 의해 적용 됩니다.  
  
### 속성 변경 알림 이벤트  
 때로는 속성 값의 변경 사항이 사용자에 게 알리는 이벤트를 제공 하는 것이 유용 합니다. 예를 들어 `System.Windows.Forms.Control` 를 발생 시킵니다는 `TextChanged` 값 이후 이벤트의 `Text` 속성이 변경 합니다.  
  
 **✓ 고려** 를 발생 시키는 변경 알림 이벤트 고급 수준의 Api \(일반적으로 디자이너 구성 요소\)의 속성 값이 수정 된 경우.  
  
 사용자에 게 알려 개체의 속성을 변경 하는 경우에 대 한 좋은 시나리오의 경우 개체 속성에 대 한 변경 알림 이벤트를 발생 시켜야 합니다.  
  
 그러나 기본 형식, 컬렉션 등 하위 수준 Api에 대 한 이러한 이벤트를 발생 시키기 위해 때문에 오버 헤드가 되도록 많지 않습니다. 예를 들어 <xref:System.Collections.Generic.List%601> 에 새 항목이 목록에 추가 될 때 이러한 이벤트를 발생 시 키 지는 및 `Count` 속성 변경 합니다.  
  
 **✓ 고려** 를 발생 시키는 변경 알림 이벤트 속성의 값이 외부 힘을 통해 변경 합니다.  
  
 속성 값을 외부 요인 \(방식 이외의 다른 개체에서 메서드를 호출 하 여\)을 통해 변경 되 면 발생 값 변경 되 고 변경 된 개발자에 게 이벤트를 나타냅니다. 좋은 예로 `Text` 텍스트 상자 컨트롤의 속성입니다. 사용자의 텍스트를 입력 하는 경우는 `TextBox`, 속성 값이 자동으로 변경 합니다.  
  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [멤버 디자인 지침](../../../docs/standard/design-guidelines/member.md)   
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)