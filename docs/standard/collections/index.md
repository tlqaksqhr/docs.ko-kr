---
title: "컬렉션 및 데이터 구조 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "컬렉션의 데이터 그룹화"
  - "개체 [.NET Framework], 컬렉션에서 그룹화"
  - "Array 클래스, 컬렉션에서 데이터 그룹화"
  - "스레딩 [.NET Framework], 보안"
  - "Collections 클래스"
  - "컬렉션[.NET Framework]"
ms.assetid: 60cc581f-1db5-445b-ba04-a173396bf872
caps.latest.revision: 36
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 35
---
# 컬렉션 및 데이터 구조
비슷한 데이터는 컬렉션으로 저장 및 조작하면 보다 효율적으로 처리할 수 있는 경우가 많습니다. 사용할 수는 <xref:System.Array?displayProperty=fullName> 의 클래스 또는 클래스는 <xref:System.Collections>, <xref:System.Collections.Generic>, <xref:System.Collections.Concurrent>, System.Collections.Immutable 네임 스페이스를 추가, 제거 및 개별 요소나 컬렉션의 요소 범위를 수정 합니다.  
  
 컬렉션에는 제네릭 컬렉션과 제네릭이 아닌 컬렉션의 두 가지 기본 유형이 있습니다. .NET Framework 2.0에서 추가된 제네릭 컬렉션은 컴파일 타임에 형식이 안전한 컬렉션을 제공합니다. 이로 인해 제네릭 컬렉션은 일반적으로 성능이 더 뛰어납니다. 제네릭 컬렉션은 생성 시 형식 매개 변수를 허용하며, 컬렉션에서 항목을 추가하거나 제거할 때 <xref:System.Object> 형식 간에 캐스팅을 수행하지 않아도 됩니다.  또한 대부분의 제네릭 컬렉션은 [!INCLUDE[win8_appstore_long](../../../includes/win8-appstore-long-md.md)] 앱에서 지원됩니다. 으로 항목을 저장 하는 제네릭이 아닌 컬렉션 <xref:System.Object>, 캐스팅을 수행 해야 하 고 대부분에 지원 되지 않습니다 [!INCLUDE[win8_appstore_long](../../../includes/win8-appstore-long-md.md)] 앱 개발 합니다. 그러나 이전 코드에는 제네릭이 아닌 컬렉션이 포함되어 있는 경우도 있습니다.  
  
 부터는 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], 컬렉션에는 <xref:System.Collections.Concurrent> 네임 스페이스는 여러 스레드에서 컬렉션 항목에 액세스 하기 위한 효율적이 고 스레드로부터 안전한 작업을 제공 합니다. System.Collections.Immutable 네임 스페이스의 변경 불가능 컬렉션 클래스 ([NuGet 패키지](https://www.nuget.org/packages/System.Collections.Immutable)) 되므로 본질적으로 스레드로부터 안전한 작업은 원래 컬렉션의 복사본에서 수행 되며 원본 컬렉션을 수정할 수 없습니다.  
  
<a name="BKMK_Commoncollectionfeatures"></a>   
## <a name="common-collection-features"></a>일반 컬렉션 기능  
 모든 컬렉션은 컬렉션의 항목 추가, 제거 또는 찾기를 위한 방법을 제공합니다. 또한 모든 컬렉션 구현 하는 직접 또는 간접적으로 <xref:System.Collections.ICollection> 인터페이스 또는 <xref:System.Collections.Generic.ICollection%601> 인터페이스는 이러한 기능을 공유 합니다.  
  
-   **컬렉션을 열거하는 기능**  
  
     .NET framework 컬렉션을 구현 하거나 <xref:System.Collections.IEnumerable?displayProperty=fullName> 또는 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> 컬렉션을 반복할 수 있도록 합니다. 열거자는 컬렉션의 모든 요소에 대한 이동 가능 포인터라고 할 수 있습니다. [foreach에](../Topic/foreach,%20in%20\(C%23%20Reference\).md) 문 및 [각각에 대해... 다음 문](../Topic/For%20Each...Next%20Statement%20\(Visual%20Basic\).md) 노출 하는 열거자를 사용 하 여는 <xref:System.Collections.IEnumerable.GetEnumerator%2A> 메서드와 숨기기 복잡 한 열거자를 조작 합니다. 또한 모든 구현 하는 컬렉션 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> 것으로 간주 됩니다는 *쿼리 가능 형식* LINQ로 쿼리할 수 있습니다. LINQ 쿼리는 데이터 액세스를 위한 일반 패턴을 제공합니다. 이러한 쿼리는 대개 표준 `foreach` 루프보다 간결하고 읽기 쉬우며 필터링, 순서 지정 및 그룹화 기능을 제공합니다. 또한 LINQ 쿼리를 통해 성능을 향상시킬 수도 있습니다. 자세한 내용은 참조 [LINQ to Objects](../../../ocs/visual-basic/programming-guide/concepts/linq/linq-to-objects.md), [PLINQ (병렬 LINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md) 및 [LINQ 쿼리 (C#) 소개](../Topic/Introduction%20to%20LINQ%20Queries%20\(C%23\).md)합니다.  
  
-   **컬렉션의 내용을 배열에 복사하는 기능**  
  
     하지만 모든 컬렉션을 사용 하 여 배열에 복사할 수는 **CopyTo** 메서드도 있습니다; 새 배열의 요소 순서는 열거자를 반환 하는 순서에 기반 합니다. 결과 배열은 항상&1;차원이며 하한은&0;입니다.  
  
 또한 다수의 컬렉션 클래스에는 다음 기능도 포함되어 있습니다.  
  
-   **Capacity 및 Count 속성**  
  
     컬렉션의 용량은 컬렉션에 포함할 수 있는 요소의 수이고, 컬렉션의 카운트는 컬렉션에 실제로 포함되어 있는 요소의 수입니다. 용량이나 카운트 중 하나 또는 둘 다를 숨기는 컬렉션도 있습니다.  
  
     대부분의 컬렉션은 현재 용량에 도달하면 자동으로 용량을 확장합니다. 이때 메모리가 다시 할당되며 요소는 이전 컬렉션에서 새 컬렉션으로 복사됩니다. 따라서 컬렉션을 사용하는 데 필요한 코드는 감소하지만 컬렉션 성능이 저하될 수 있습니다. 예를 들어 <xref:System.Collections.Generic.List%601>경우 <xref:System.Collections.Generic.List%601.Count%2A> 는 보다 작은 <xref:System.Collections.Generic.List%601.Capacity%2A>, 항목을 추가 하는 것은 o (1) 연산입니다. 항목을 추가 합니다. 여기서 n은은 o (n) 작업이 됩니다. 용량을 새 요소로 적용로 늘려야 하는 경우 <xref:System.Collections.Generic.List%601.Count%2A>합니다. 메모리가 여러 번 다시 할당되어 성능이 저하되는 현상을 방지하는 가장 좋은 방법은 초기 용량을 컬렉션의 예상 크기로 설정하는 것입니다.  
  
     <xref:System.Collections.BitArray>는 해당 용량과 길이 및 카운트가 모두 같은 특수한 경우입니다.  
  
-   **일관된 하한**  
  
     컬렉션의 하한은 첫 번째 요소의 인덱스입니다. <xref:System.Collections> 네임스페이스의 모든 인덱싱된 컬렉션은 하한이 0입니다. 즉, 0부터 인덱싱됩니다. <xref:System.Array> 기본적으로&0; 값은 있지만의 인스턴스를 만들 때 다른 하 한을 정의할 수 있습니다는 **배열** 클래스를 사용 하 여 <xref:System.Array.CreateInstance%2A?displayProperty=fullName>합니다.  
  
-   **여러 스레드로부터의 액세스를 위한 동기화**(<xref:System.Collections> 클래스에만 해당됨).  
  
     제네릭이 아닌 컬렉션 형식은 <xref:System.Collections> 네임 스페이스 동기화 어느 정도의 스레드 보안을 제공; 통해 일반적으로 노출 되는 <xref:System.Collections.ICollection.SyncRoot%2A> 및 <xref:System.Collections.ICollection.IsSynchronized%2A> 멤버입니다. 이러한 컬렉션은 기본적으로 스레드로부터 안전하지 않습니다. 확장 가능하며 효율적인 다중 스레드 방식으로 컬렉션에 액세스해야 하는 경우에는 <xref:System.Collections.Concurrent> 네임스페이스의 클래스 중 하나를 사용하거나 변경할 수 없는 컬렉션을 사용하는 것이 좋습니다. 자세한 내용은 [스레드로부터 안전한 컬렉션](../../../docs/standard/collections/thread-safe/index.md)을 참조하세요.  
  
<a name="BKMK_Choosingacollection"></a>   
## <a name="choosing-a-collection"></a>컬렉션 선택  
 일반적으로는 제네릭 컬렉션을 사용해야 합니다. 다음 표에는 몇 가지 일반적인 컬렉션 시나리오와 이러한 시나리오에서 사용할 수 있는 컬렉션 클래스에 대해 설명합니다. 제네릭 컬렉션을 처음 사용하는 경우 이 표의 내용을 참조하여 작업에 가장 적합한 제네릭 컬렉션을 선택할 수 있습니다.  
  
|||||  
|-|-|-|-|  
|수행할 작업|제네릭 컬렉션 옵션|제네릭이 아닌 컬렉션 옵션|스레드로부터 안전하거나 변경할 수 없는 컬렉션 옵션|  
|키별로 빠르게 조회할 수 있도록 항목을 키/값 쌍으로 저장|<xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName></TKey, TValue>|<xref:System.Collections.Hashtable><br /><br /> (키의 해시 코드를 기준으로 구성되는 키/값 쌍 컬렉션)|<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName>\</TKey, TValue><br /><br /> <xref:System.Collections.ObjectModel.ReadOnlyDictionary%602?displayProperty=fullName>\</TKey, TValue><br /><br /> [ImmutableDictionary (TKey, t) 클래스](../Topic/ImmutableDictionary\(TKey,%20TValue\)%20Class.md)|  
|인덱스별로 항목 액세스|<xref:System.Collections.Generic.List%601?displayProperty=fullName>|<xref:System.Array?displayProperty=fullName><br /><br /> <xref:System.Collections.ArrayList?displayProperty=fullName>|[ImmutableList(T) 클래스](../Topic/ImmutableList\(T\)%20Class.md)<br /><br /> [ImmutableArray 클래스](../Topic/ImmutableArray%20Class.md)|  
|FIFO(선입 선출) 방식으로 항목 사용|<xref:System.Collections.Generic.Queue%601?displayProperty=fullName>|<xref:System.Collections.Queue?displayProperty=fullName>|<xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName><br /><br /> [ImmutableQueue(T) 클래스](../Topic/ImmutableQueue\(T\)%20Class.md)|  
|LIFO(후입 선출) 방식으로 데이터 사용|<xref:System.Collections.Generic.Stack%601?displayProperty=fullName>|<xref:System.Collections.Stack?displayProperty=fullName>|<xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=fullName><br /><br /> [ImmutableStack(T) 클래스](../Topic/ImmutableStack\(T\)%20Class.md)|  
|순서대로 항목 액세스|<xref:System.Collections.Generic.LinkedList%601?displayProperty=fullName>|권장 사항 없음|권장 사항 없음|  
|항목을 컬렉션에 추가하거나 컬렉션에서 제거할 때 알림이 표시됩니다. (구현 <xref:System.ComponentModel.INotifyPropertyChanged> 및 <xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=fullName>)|<xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=fullName>|권장 사항 없음|권장 사항 없음|  
|정렬된 컬렉션|<xref:System.Collections.Generic.SortedList%602?displayProperty=fullName>\</TKey, TValue>|<xref:System.Collections.SortedList?displayProperty=fullName>|[ImmutableSortedDictionary (TKey, t) 클래스](../Topic/ImmutableSortedDictionary\(TKey,%20TValue\)%20Class.md)<br /><br /> [ImmutableSortedSet(T) 클래스](../Topic/ImmutableSortedSet\(T\)%20Class.md)|  
|수학 함수용 집합|<xref:System.Collections.Generic.HashSet%601?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.SortedSet%601?displayProperty=fullName>|권장 사항 없음|[ImmutableHashSet(T) 클래스](../Topic/ImmutableHashSet\(T\)%20Class.md)<br /><br /> [ImmutableSortedSet(T) 클래스](../Topic/ImmutableSortedSet\(T\)%20Class.md)|  
  
<a name="BKMK_RelatedTopics"></a>   
## <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|-----------|-----------------|  
|[Collection 클래스 선택](../../../docs/standard/collections/selecting-a-collection-class.md)|다양한 컬렉션에 대해 설명하고 시나리오에 맞는 컬렉션을 선택하는 데 도움이 되는 정보를 제공합니다.|  
|[일반적으로 사용되는 컬렉션 형식](../../../docs/standard/collections/commonly-used-collection-types.md)|와 같이 일반적으로 사용 되는 제네릭 및 제네릭이 아닌 컬렉션 형식을 설명 <xref:System.Array?displayProperty=fullName>, <xref:System.Collections.Generic.List%601?displayProperty=fullName>, 및 <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName>.\</TKey, TValue>|  
|[제네릭 컬렉션 사용 기준](../../../docs/standard/collections/when-to-use-generic-collections.md)|제네릭 컬렉션 형식의 사용을 설명합니다.|  
|[컬렉션 내에서 비교 및 정렬](../../../docs/standard/collections/comparisons-and-sorts-within-collections.md)|컬렉션에서 같음 비교 및 정렬 비교를 사용하는 방법을 설명합니다.|  
|[Sorted 컬렉션 형식](../../../docs/standard/collections/sorted-collection-types.md)|정렬된 컬렉션의 성능 및 특징에 대해 설명합니다.|  
|[Hashtable 및 Dictionary 컬렉션 형식](../../../docs/standard/collections/hashtable-and-dictionary-collection-types.md)|제네릭 및 제네릭이 아닌 해시 기반 사전 형식의 기능을 설명합니다.|  
|[스레드로부터 안전한 컬렉션](../../../docs/standard/collections/thread-safe/index.md)|같은 컬렉션 형식에 설명 <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> 및 <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=fullName> 지 원하는 여러 스레드에서 안전 하 고 효율적인 동시 액세스 합니다.|  
|System.Collections.Immutable|변경 불가능은 컬렉션을 소개하고 컬렉션 형식에 대한 링크를 제공합니다.|  
  
<a name="BKMK_Reference"></a>   
## <a name="reference"></a>참조  
 <xref:System.Array?displayProperty=fullName>  
  
 <xref:System.Collections?displayProperty=fullName>  
  
 <xref:System.Collections.Concurrent?displayProperty=fullName>  
  
 <xref:System.Collections.Generic?displayProperty=fullName>  
  
 <xref:System.Collections.Specialized?displayProperty=fullName>  
  
 <xref:System.Linq?displayProperty=fullName>  
  
 System.Collections.Immutable
