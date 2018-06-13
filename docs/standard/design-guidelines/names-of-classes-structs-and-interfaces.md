---
title: 클래스, 구조체 및 인터페이스의 이름
ms.date: 03/30/2017
helpviewer_keywords:
- type names, guidelines
- classes [.NET Framework], names
- enumerations [.NET Framework], names
- names [.NET Framework], interfaces
- common type names
- names [.NET Framework], type names
- names [.NET Framework], classes
- interfaces [.NET Framework], names
- generic type parameters
ms.assetid: 87a4b0da-ed64-43b1-ac43-968576c444ce
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a1841fbfcb76d5b56681b63ec4b39e9a7418707f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33576144"
---
# <a name="names-of-classes-structs-and-interfaces"></a>클래스, 구조체 및 인터페이스의 이름
다음에 나오는 이름 지정 지침 일반 형식의 이름 지정에 적용 됩니다.  
  
 **✓ 않습니다** 명사 또는 명사구를 PascalCasing를 사용 하 여으로 클래스 및 구조체 이름을 지정 합니다.  
  
 이 동사 구 붙은 메서드에서 형식 이름을 구분 합니다.  
  
 **✓ 않습니다** 형용사 구 또는 경우에 따라 명사 또는 명사구 인터페이스 이름을 지정 합니다.  
  
 명사 및 명사구를 거의 사용 해야 하며 형식을 추상 클래스와 인터페이스 하지 되어야 함을 나타낼 수 있습니다.  
  
 **X 하지 않으면** 클래스 이름 (예: "C")는 접두사를 제공 합니다.  
  
 **✓ 고려** 기본 클래스의 이름으로 클래스를 파생 종료 이름입니다.  
  
 이 매우 읽을 수 하 고 관계를 명확 하 게 설명 합니다. 이 코드의 예로: `ArgumentOutOfRangeException`, 하는 한 종류의 `Exception`, 및 `SerializableAttribute`, 하는 한 종류의 `Attribute`합니다. 그러나 되기;이 지침을 적용할 때 적절 한 판단 신호를 사용 하 여 예를 들어는 `Button` 클래스는 일종의 `Control` 이벤트 있지만 `Control` 이름에 표시 되지 않습니다.  
  
 **✓ 않습니다** 문자로 접두사 인터페이스 이름을 I, 유형을 인터페이스 임을 나타냅니다.  
  
 예를 들어 `IComponent` (설명이 포함 된 명사) `ICustomAttributeProvider` (명사구) 및 `IPersistable` (명사)은 적절 한 인터페이스의 이름입니다. 다른 형식 이름에서와 마찬가지로 약어를 하지 마십시오.  
  
 **✓ 않습니다** 이름으로 "I" 접두사 인터페이스 이름에는 클래스는 인터페이스의 표준 구현 클래스-인터페이스 쌍을 정의 하는 경우에 다른 지 확인 합니다.  
  
## <a name="names-of-generic-type-parameters"></a>제네릭 형식 매개 변수 이름  
 제네릭은.NET Framework 2.0에 추가 되었습니다. 도입 된 새로운 종류의 라는 식별자는 기능인 *형식 매개 변수*합니다.  
  
 **✓ 않습니다** 단일 문자 이름을 완전히 자체 설명 하 고 설명 하는 이름 값을 더 하지 않는 경우 제외 설명적인 이름으로 name 제네릭 형식 매개 변수입니다.  
  
 **✓ 고려** 를 사용 하 여 `T` 단일 문자 형식 매개 변수를 사용 하는 형식에 대 한 형식 매개 변수 이름으로 합니다.  
  
```  
public int IComparer<T> { ... }  
public delegate bool Predicate<T>(T item);  
public struct Nullable<T> where T:struct { ... }  
```  
  
 **✓ 않습니다** 설명적인 형식 매개 변수 이름 앞에 `T`합니다.  
  
```  
public interface ISessionChannel<TSession> where TSession : ISession{  
    TSession Session { get; }  
}  
```  
  
 **✓ 고려** 제약 조건을 나타내는 매개 변수 이름의 형식 매개 변수에 적용 합니다.  
  
 예를 들어 한 매개 변수를 제한할 `ISession` 파일명 `TSession`합니다.  
  
## <a name="names-of-common-types"></a>공용 형식의 이름  
 **✓ 않습니다** 또는 특정.NET Framework 형식이 구현에서 파생 된 형식의 이름을 지정할 때 다음 표에 설명 된 지침을 따르십시오.  
  
|Base Type|형식 파생/구현 지침|  
|---------------|------------------------------------------|  
|`System.Attribute`|**✓ 않습니다** 사용자 지정 특성 클래스의 이름에 "특성" 접미사를 추가 합니다.|  
|`System.Delegate`|**✓ 않습니다** 이벤트에 사용 되는 대리자의 이름에 "EventHandler" 접미사를 추가 합니다.<br /><br /> **✓ 않습니다** 이외의 이벤트 처리기로 사용 되는 접미사 "Callback" 이름에 대리자를 추가 합니다.<br /><br /> **X 하지 않으면** "대리자" 접미사는 대리자를 추가 합니다.|  
|`System.EventArgs`|**✓ 않습니다** "EventArgs입니다." 접미사 추가|  
|`System.Enum`|**X 하지 않으면** 대신 해당 언어에서 지 원하는 키워드를 사용 하 여; 예를 들어 C#에서 사용 하 여이 클래스에서 파생 된 `enum` 키워드입니다.<br /><br /> **X 하지 않으면** "열거형" 또는 "Flag" 접미사 추가|  
|`System.Exception`|**✓ 않습니다** "예외" 접미사 추가|  
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|**✓ 않습니다** "사전입니다." 접미사 추가 `IDictionary` 는 컬렉션의 특정 형식 이지만이 지침 뒤에 오는 보다 일반적인 컬렉션 지침 보다 우선 합니다.|  
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|**✓ 않습니다** "Collection" 접미사 추가|  
|`System.IO.Stream`|**✓ 않습니다** "스트림입니다." 접미사 추가|  
|`CodeAccessPermission IPermission`|**✓ 않습니다** "권한" 접미사 추가|  
  
## <a name="naming-enumerations"></a>열거형 이름 지정  
 일반적 (열거형) 열거형 형식 이름에 표준 형식 명명 규칙 (PascalCasing 등) 따라야 합니다. 그러나 열거형에만 적용 되는 추가 지침이 있습니다.  
  
 **✓ 않습니다** 비트 필드에 해당 값이 경우가 아니면 열거형에 대 한 단수형 형식 이름을 사용 합니다.  
  
 **✓ 않습니다** 라고도 함 플래그 열거형 값으로 비트 필드 열거형에 대 한 복수 형식 이름을 사용 합니다.  
  
 **X 하지 않으면** enum 형식 이름에 "열거형" 접미사를 사용 합니다.  
  
 **X 하지 않으면** "플래그를"를 사용 하 여 또는 열거형에서 "Flags" 접미사 이름을 입력 합니다.  
  
 **X 하지 않으면** 서식 있는 텍스트 열거형 등에 대 한 열거형 값 이름 (예: "ad" 열거형의 ADO.), "rtf"에 접두사를 사용 합니다.  
  
 *Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*  
  
 *피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*  
  
## <a name="see-also"></a>참고 항목  
 [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)  
 [명명 지침](../../../docs/standard/design-guidelines/naming-guidelines.md)
