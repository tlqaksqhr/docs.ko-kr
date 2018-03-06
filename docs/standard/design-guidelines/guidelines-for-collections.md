---
title: "컬렉션에 대한 지침"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 297b8f1d-b11f-4dc6-960a-8e990817304e
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 09a2a075e21de6968989575385db07ab39eb627f
ms.sourcegitcommit: c3957fdb990060559d73cca44ab3e2c7b4d049c0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2018
---
# <a name="guidelines-for-collections"></a>컬렉션에 대한 지침
일부 일반적인 특성에 포함 된 개체의 그룹을 조작 하도록 특별히 설계 된 모든 형식은 컬렉션을 간주할 수 있습니다. 구현 하는 이러한 형식에 대 한 적절 한 것은 항상 <xref:System.Collections.IEnumerable> 또는 <xref:System.Collections.Generic.IEnumerable%601>이므로이 섹션의만 이라고 생각 컬렉션 수를 하나 또는 둘 다 인터페이스를 구현 하는 형식입니다.  
  
 **X 하지 않으면** 공용 Api에서 약한 형식의 컬렉션을 사용 합니다.  
  
 모든 컬렉션 항목을 나타내는 매개 변수 및 반환 값의 형식을 해당 형식의 기본 형식 (컬렉션의 공용 멤버에만 적용)는 정확한 항목 유형, 이어야 합니다.  
  
 **X 하지 않으면** 사용 <xref:System.Collections.ArrayList> 또는 <xref:System.Collections.Generic.List%601> 공용 Api에서 합니다.  
  
 이러한 형식은 데이터 구조 공용 Api에 없는 내부 구현에 사용할 수 있도록 설계 됩니다. `List<T>` 성능 및 유연성과 Api cleanness 대신 전원에 대해 최적화 되어 있습니다. 예를 들어, 반환 하는 경우 `List<T>`, 현재까지 됩니다 클라이언트 코드에서 컬렉션을 수정할 때 알림을 받을 수 있게 합니다. 또한 `List<T>` 와 같은 많은 멤버를 노출 <xref:System.Collections.Generic.List%601.BinarySearch%2A>, 되지 않은 유용 하거나 다양 한 시나리오에 적용할 수 있습니다. 다음 두 섹션에서는 형식 (추상화) 공용 Api에서 사용 하도록 특별히 설계에 대해 설명 합니다.  
  
 **X 하지 않으면** 사용 `Hashtable` 또는 `Dictionary<TKey,TValue>` 공용 Api에서 합니다.  
  
 이러한 형식은 데이터 구조 내부 구현에 사용할 수 있도록 설계 됩니다. 공용 Api를 사용 해야 <xref:System.Collections.IDictionary>, `IDictionary <TKey, TValue>`, 또는 인터페이스 중 하나 또는 모두를 구현 하는 사용자 지정 형식을 합니다.  
  
 **X 하지 않으면** 사용 <xref:System.Collections.Generic.IEnumerator%601>, <xref:System.Collections.IEnumerator>, 또는 다른 종류의 반환 형식으로 제외 하 고 이러한 인터페이스를 구현 하는 `GetEnumerator` 메서드.  
  
 이외의 다른 방법 중에서 열거자를 반환 하는 형식 `GetEnumerator` 함께 사용할 수 없습니다는 `foreach` 문.  
  
 **X 하지 않으면** 둘 다 구현 `IEnumerator<T>` 및 `IEnumerable<T>` 을 같은 형식의 합니다. 제네릭이 아닌 인터페이스에 적용 되는 동일한 `IEnumerator` 및 `IEnumerable`합니다.  
  
## <a name="collection-parameters"></a>컬렉션 매개 변수  
 **✓ 않습니다** 는 최소 특수 형식 가능한 매개 변수 형식으로 사용 합니다. 매개 변수를 사용 하 여 컬렉션을 수행 합니다. 대부분의 멤버는 `IEnumerable<T>` 인터페이스입니다.  
  
 **하지 말고 X** 를 사용 하 여 <xref:System.Collections.Generic.ICollection%601> 또는 <xref:System.Collections.ICollection> 액세스를 매개 변수로 `Count` 속성입니다.  
  
 대신 사용을 고려 `IEnumerable<T>` 또는 `IEnumerable` 동적으로 개체를 구현 하는지 확인 하 고 `ICollection<T>` 또는 `ICollection`합니다.  
  
## <a name="collection-properties-and-return-values"></a>컬렉션의 속성 및 반환 값  
 **X 하지 않으면** 설정 가능한 컬렉션 속성을 제공 합니다.  
  
 컬렉션을 먼저 선택 취소 한 다음 새 콘텐츠를 추가 하 여 컬렉션의 내용을 바꿀 수 있습니다. 전체 컬렉션을 대체 일반적인 시나리오는 경우에 제공 하 여는 `AddRange` 메서드 컬렉션입니다.  
  
 **✓ 않습니다** 사용 `Collection<T>` 또는 하위 클래스 `Collection<T>` 속성 또는 반환 값 나타내는 읽기/쓰기 컬렉션입니다.  
  
 경우 `Collection<T>` 몇 가지 요구 사항을 충족 하지 않습니다 (예: 컬렉션은 구현 하지 해야 <xref:System.Collections.IList>)를 구현 하 여 사용자 지정 컬렉션을 사용 하 여 `IEnumerable<T>`, `ICollection<T>`, 또는 <xref:System.Collections.Generic.IList%601>합니다.  
  
 **✓ 수행** 사용 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>의 서브 클래스 `ReadOnlyCollection<T>`, 또는 드물지만에서 `IEnumerable<T>` 속성 또는 반환 값을 나타내는 읽기 전용 컬렉션에 대 한 합니다.  
  
 일반적으로 선호 `ReadOnlyCollection<T>`합니다. 몇 가지 요구 사항을 충족 하지 않는 경우 (예: 컬렉션은 구현 하지 해야 `IList`)를 구현 하 여 사용자 지정 컬렉션을 사용 하 여 `IEnumerable<T>`, `ICollection<T>`, 또는 `IList<T>`합니다. 읽기 전용 컬렉션을 사용자 지정을 구현 하는 경우 구현 `ICollection<T>.IsReadOnly` 반환할 `true`합니다.  
  
 경우에만 지원 하려는 앞 으로만 이동 가능한 반복 인지는 경우에 사용 하면 `IEnumerable<T>`합니다.  
  
 **✓ 고려** 제네릭 기본 컬렉션의 하위 클래스를 사용 하 여 컬렉션을 직접 사용 하는 대신 합니다.  
  
 이렇게 하면 더 나은 이름일 고 기본 컬렉션 형식에 존재 하지 않는 도우미 구성원을 추가 합니다. 이 높은 수준의 Api에 특히 적합 합니다.  
  
 **✓ 고려** 의 서브 클래스를 반환 `Collection<T>` 또는 `ReadOnlyCollection<T>` 에서 매우 흔히 사용 되는 메서드 및 속성입니다.  
  
 이렇게 하면 더욱 도우미 메서드를 추가 하거나 컬렉션 구현을 나중에 변경할 수 있습니다.  
  
 **✓ 고려** 컬렉션에 저장 된 항목에는 고유 키가 있는 경우 키 컬렉션을 사용 하 여 (이름, Id 등.). 키가 지정 된 컬렉션은 정수과 키로 인덱싱할 수 및에서 상속 하 여 일반적으로 구현 되는 컬렉션 `KeyedCollection<TKey,TItem>`합니다.  
  
 키 컬렉션 일반적으로 더 큰 메모리 용량 있고 메모리 오버 헤드는 키를 갖는 것의 이점 보다 중요 한 경우 사용 하지 않아야 합니다.  
  
 **X 하지 않으면** 컬렉션 속성에서 또는 컬렉션을 반환 하는 방법 중에서 null 값을 반환 합니다. 빈 컬렉션 이거나 빈 배열 대신 반환 합니다.  
  
 Null 및 빈 (0 항목) 컬렉션 또는 배열과 되어야 함을 일반적인 규칙은 동일 하 게 처리 합니다.  
  
### <a name="snapshots-versus-live-collections"></a>스냅숏을 라이브 컬렉션 비교  
 컬렉션의에서 특정 시점에 상태를 나타내는 스냅숏 컬렉션 이라고 합니다. 예를 들어 데이터베이스 쿼리에서 반환 된 행을 포함 하는 컬렉션 스냅숏을 것입니다. 항상 현재 상태를 나타내는 컬렉션 라이브 컬렉션 이라고 합니다. 예를 들어 컬렉션의 `ComboBox` 항목은 라이브 컬렉션입니다.  
  
 **X 하지 않으면** 속성에서 스냅숏 컬렉션을 반환 합니다. 속성 라이브 컬렉션을 반환 해야 합니다.  
  
 속성 getter 매우 간단한 작업 해야 합니다. o (n) 작업에서 내부 컬렉션의 복사본을 만드는 필요 스냅숏을 반환 합니다.  
  
 **✓ 않습니다** 스냅숏 컬렉션 또는 라이브를 사용 하 여 `IEnumerable<T>` (또는 해당 하위 유형)을 휘발성 하는 컬렉션을 나타내는 (즉, 하는 변경할 수 명시적으로 컬렉션을 수정 하지 않고).  
  
 일반적으로 공유 리소스 (예: 디렉터리의 파일)를 나타내는 모든 컬렉션은 일시적입니다. 이러한 컬렉션 매우 어렵거나 구현에서 앞 으로만 이동 가능한 열거자 단순히 아닌 경우 라이브 컬렉션으로 구현 됩니다.  
  
## <a name="choosing-between-arrays-and-collections"></a>배열 및 컬렉션 중에서 선택  
 **✓ 않습니다** 배열을 통해 컬렉션을 선호 합니다.  
  
 컬렉션 내용 보다 잘 제어할 시간이 지남에 따라 확장할 수 및 더 사용할 수 없습니다. 또한 배열을 사용 하 여 읽기 전용 시나리오에 대 한 것이 좋습니다 배열을 복제 비용은 제한 된다는 가정 하기 때문에 있습니다. 유용성 연구 일부 개발자 컬렉션 기반 Api를 사용 하 여 더 잘 알고 있는지 설명 했습니다.  
  
 그러나, 낮은 수준의 Api 개발 하는 경우 읽기 / 쓰기 시나리오에 대 한 배열을 사용 하 여 수 있습니다. 배열 있으며 작업 집합을 줄일 수는 작은 메모리 사용 공간을 있고 런타임에서 최적화 되기 때문에 배열의 요소에 대 한 액세스 빠릅니다.  
  
 **✓ 고려** 메모리 소비를 최소화 하 고 성능을 최대화 하려면 배열 낮은 수준의 Api에서 사용 합니다.  
  
 **✓ 않습니다** 바이트 배열 바이트의 컬렉션 대신 사용 합니다.  
  
 **X 하지 않으면** 속성 getter 속성을 호출할 때마다 새 배열 (예: 내부 배열 복사본)을 반환 해야 하는 경우 속성에 대 한 배열을 사용 합니다.  
  
## <a name="implementing-custom-collections"></a>사용자 지정 컬렉션을 구현합니다.  
 **✓ 고려** 에서 상속 `Collection<T>`, `ReadOnlyCollection<T>`, 또는 `KeyedCollection<TKey,TItem>` 새 컬렉션을 디자인 하는 경우.  
  
 **✓ 않습니다** 구현 `IEnumerable<T>` 새 컬렉션을 디자인 하는 경우. 구현 하는 것이 좋습니다. `ICollection<T>` 또는 심지어 `IList<T>` 것이 적합 합니다.  
  
 이러한 사용자 지정 컬렉션을 구현할 때에서 설정한 API 패턴을 따를 `Collection<T>` 및 `ReadOnlyCollection<T>` 최대한 근접 하 게 합니다. 즉, 동일한 멤버를 명시적으로 구현, 및 등이 두 컬렉션 이름 같은 매개 변수 이름을 지정 합니다.  
  
 **✓ 고려** 제네릭이 아닌 컬렉션 인터페이스를 구현 (`IList` 및 `ICollection`) 컬렉션 입력으로 이러한 인터페이스를 라인 Api에 전달 경우가 많습니다.  
  
 **하지 말고 X** 관련 되지 않은 컬렉션의 개념을 복잡 한 Api와 형식에 컬렉션 인터페이스를 구현 합니다.  
  
 **X 하지 않으면** 와 같은 제네릭이 아닌 기본 컬렉션에서 상속할 `CollectionBase`합니다. 사용 하 여 `Collection<T>`, `ReadOnlyCollection<T>`, 및 `KeyedCollection<TKey,TItem>` 대신 합니다.  
  
### <a name="naming-custom-collections"></a>사용자 지정 컬렉션 이름 지정  
 컬렉션 (구현 하는 형식은 `IEnumerable`) 주로 두 가지 이유로 생성 됩니다: (1) 구조를 만들려면 새 데이터 구조 관련 작업 그리고 자주 기존 데이터 구조 보다 다양 한 성능 특성 (예: <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.LinkedList%601>, <xref:System.Collections.Generic.Stack%601>), 및 (2) 항목의 특정 집합을 보관 하기 위한 특수 한 컬렉션을 만듭니다 (예: <xref:System.Collections.Specialized.StringCollection>). 데이터 구조는 응용 프로그램 및 라이브러리의 내부 구현에서 가장 자주 사용 됩니다. 특수 컬렉션은 주로 (속성 및 매개 변수 형식)와 Api에 노출 될를 합니다.  
  
 **✓ 않습니다** 의 추상화를 구현 하는 이름에 "사전" 접미사를 사용 하 여 `IDictionary` 또는 `IDictionary<TKey,TValue>`합니다.  
  
 **✓ 않습니다** 구현 하는 형식 이름에 "Collection" 접미사 사용 `IEnumerable` (또는 해당 하위 항목의) 및 항목 목록을 표시 합니다.  
  
 **✓ 않습니다** 사용자 지정 데이터 구조에 대 한 적절 한 데이터 구조 이름을 사용 합니다.  
  
 **하지 말고 X** 컬렉션 추상화의 이름에 "LinkedList" 또는 "Hashtable" 등의 특정 구현 암시 모든 접미사를 사용 합니다.  
  
 **✓ 고려** 항목 형식의 이름이 포함 된 컬렉션 이름을 접두사로 사용 합니다. 예를 들어 형식의 항목을 저장 하는 컬렉션 `Address` (구현 `IEnumerable<Address>`) 명명할 `AddressCollection`합니다. 접두사 "I" 항목 형식이 인터페이스인 경우 항목의 종류를 생략할 수 있습니다. 따라서 컬렉션 <xref:System.IDisposable> 항목을 호출할 수 있습니다 `DisposableCollection`합니다.  
  
 **✓ 고려** 해당 쓰기 가능한 컬렉션 추가 될 수 있는 프레임 워크에 이미 있는 경우 읽기 전용 컬렉션의 이름에 "ReadOnly" 접두사를 사용 합니다.  
  
 문자열의 읽기 전용 컬렉션을 호출 해야 하는 예를 들어 `ReadOnlyStringCollection`합니다.  
  
 *Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*  
  
 *피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*  
  
## <a name="see-also"></a>참고 항목  
 [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)  
 [사용 지침](../../../docs/standard/design-guidelines/usage-guidelines.md)
