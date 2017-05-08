---
title: "클래스, 구조체 및 인터페이스의 이름 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "형식 이름, 지침"
  - "클래스 [.NET Framework] 이름"
  - "열거형 [.NET Framework] 이름"
  - "인터페이스 이름 [.NET Framework]"
  - "일반 형식 이름"
  - "이름 [.NET Framework] 형식 이름"
  - "클래스 이름 [.NET Framework]"
  - "이름 인터페이스 [.NET Framework]"
  - "제네릭 형식 매개 변수"
ms.assetid: 87a4b0da-ed64-43b1-ac43-968576c444ce
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# 클래스, 구조체 및 인터페이스의 이름
일반 형식 이름을 지정할 때 명명 지침을 따릅니다.  
  
 **✓ 수행** 클래스 및 구조체 명사 또는 명사구를 PascalCasing를 사용 하 여 이름을 지정 합니다.  
  
 이 이름에 있는 동사 구 메서드에서 형식 이름을 구분 합니다.  
  
 **✓ 수행** 형용사 구 또는 경우에 따라 명사 또는 명사구 인터페이스 이름을 지정 합니다.  
  
 명사 및 명사구를 거의 사용 해야 하 고 형식을 추상 클래스와 인터페이스 하지 되어야 함을 나타낼 수 있습니다.  
  
 **X 하지 않으려면** 클래스 이름 접두사 \(예: "C"\)을 제공 합니다.  
  
 **✓ 고려** 의 이름 끝의 파생 클래스 이름으로 기본 클래스입니다.  
  
 이 가독성이 뛰어납니다 하 고 관계를 명확 하 게 설명 합니다. 코드에서이 작업의 몇 가지 예는: `ArgumentOutOfRangeException`, 하는 한 종류의 `Exception`, 및 `SerializableAttribute`, 하는 한 종류의 `Attribute`합니다. 그러나 반드시이 지침; 적용에 적절 한 판단 예를 들어는 `Button` 클래스는 일종의 `Control` 이벤트에 있지만 `Control` 이름에 표시 되지 않으면.  
  
 **✓ 수행** 문자로 접두사 인터페이스 이름을 I, 형식 인터페이스 임을 나타냅니다.  
  
 예를 들어 `IComponent` \(설명이 포함 된 명사\) `ICustomAttributeProvider` \(명사구\) 및 `IPersistable` \(명사\)는 적절 한 인터페이스 이름입니다. 다른 형식 이름에서와 마찬가지로 약어를 하지 마십시오.  
  
 **✓ 수행** 이름에서 "I" 접두사 인터페이스 이름에는 클래스 인터페이스의 표준 구현을 인 클래스\-인터페이스 쌍을 정의 하는 경우에 다른 지 확인 합니다.  
  
## 제네릭 형식 매개 변수 이름  
 제네릭은은.NET Framework 2.0에 추가 되었습니다. 기능 식별자 라는 새로운 유형의 도입 *형식 매개 변수*합니다.  
  
 **✓ 수행** 단일 문자 이름을 완전히 이해 하기 쉬우며 및 설명이 포함 된 이름 값을 더 하지 않는 설명적인 이름으로 제네릭 형식 매개 변수 이름입니다.  
  
 **✓ 고려** 를 사용 하 여 `T` 하나의 단일 문자 형식 매개 변수가 있는 형식에 대 한 형식 매개 변수 이름으로 합니다.  
  
```  
public int IComparer<T> { ... }  
public delegate bool Predicate<T>(T item);  
public struct Nullable<T> where T:struct { ... }  
```  
  
 **✓ 수행** 설명적인 형식 매개 변수 이름 앞에 `T`합니다.  
  
```  
public interface ISessionChannel<TSession> where TSession : ISession{  
    TSession Session { get; }  
}  
```  
  
 **✓ 고려** 제약 조건을 나타내는 매개 변수 이름의 형식 매개 변수에 적용 합니다.  
  
 매개 변수를 제한 하는 예를 들어 `ISession` 파일명 `TSession`합니다.  
  
## 공용 형식의 이름  
 **✓ 수행** 또는 특정.NET Framework 형식 구현에서 파생 된 형식 이름을 지정할 때 다음 표에 설명 된 지침을 따릅니다.  
  
|기본 형식|형식 파생 된 구현 지침|  
|-----------|-------------------|  
|`System.Attribute`|**✓ 수행** 사용자 지정 특성 클래스의 이름에 접미사 "특성"을 추가 합니다. 사용자 지정 특성 클래스의 이름에 "특성" 접미사를 추가 합니다.|  
|`System.Delegate`|**✓ 수행** 이벤트에 사용 되는 대리자의 이름에 "이벤트 처리기" 접미사를 추가 합니다.<br /><br /> **✓ 수행** 이외의 이벤트 처리기로 사용 되는 접미사 "Callback" 이름에 대리자를 추가 합니다.<br /><br /> **X 하지 않으려면** 접미사 "Delegate" 대리자를 추가 합니다.|  
|`System.EventArgs`|**✓ 수행** 접미사 "EventArgs."를 추가 합니다.|  
|`System.Enum`|**X 하지 않으려면** 대신 해당 하는 언어에서 지 원하는 키워드를 사용 하 여; 예를 들어 C\#에서는 enum 키워드를 사용 하 여이 클래스에서 파생 됩니다.<br /><br /> **X 하지 않으려면** "열거형" 또는 "플래그입니다." 접미사를 추가 합니다.|  
|`System.Exception`|**✓ 수행** "예외입니다." 접미사를 추가 합니다.|  
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|**✓ 수행** "사전입니다." 접미사를 추가 합니다.`IDictionary` 는 컬렉션의 특정 형식 이지만이 지침 다음에 나오는 더 일반적으로 특정 컬렉션에 우선 합니다.|  
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|**✓ 수행** "컬렉션입니다." 접미사를 추가 합니다.|  
|`System.IO.Stream`|**✓ 수행** "스트림입니다." 접미사를 추가 합니다.|  
|`CodeAccessPermission IPermission`|**✓ 수행** "권한" 접미사를 추가 합니다.|  
  
## 열거형 이름 지정  
 일반적 열거형 형식 \(열거형이 라고도 함\)의 이름은 표준 형식 명명 규칙 \(PascalCasing 등\) 따라야 합니다. 그러나 열거형에만 적용 되는 추가 지침 있습니다.  
  
 **✓ 수행** 해당 값은 비트 필드 경우가 아니면 열거형에 대 한 단수형 형식 이름을 사용 합니다.  
  
 **✓ 수행** 라고도 플래그 열거형 값으로 비트 필드가 있는 열거형에 대 한 복수 형식 이름을 사용 합니다.  
  
 **X 하지 않으려면** 열거형 형식 이름에 "열거형" 접미사를 사용 합니다.  
  
 **X 하지 않으려면** 사용 "플래그" 또는 열거형에서 "플래그" 접미사 이름을 입력 합니다.  
  
 **X 하지 않으려면** 등 서식 있는 텍스트 열거형에 대 한 열거형 값 이름 \(예: "ad" ADO 열거형입니다.\), "rtf"에 접두사를 사용 합니다.  
  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)   
 [명명 지침](../../../docs/standard/design-guidelines/naming-guidelines.md)