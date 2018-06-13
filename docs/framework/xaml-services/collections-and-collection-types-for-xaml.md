---
title: XAML을 위한 컬렉션 및 컬렉션 형식
ms.date: 03/30/2017
ms.assetid: 58f8e7c6-9a41-4f25-8551-c042f1315baa
ms.openlocfilehash: 5605c97b13503e18e2f698f2a19f715663052b08
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562978"
---
# <a name="collections-and-collection-types-for-xaml"></a>XAML을 위한 컬렉션 및 컬렉션 형식
이 항목 컬렉션을 지원 하 고 컬렉션 항목 요소는 부모 개체의 요소 또는 속성 요소 자식으로 인스턴스화하기 위한 XAML 구문을 지원 하도록 설계 된 형식의 속성을 정의 하는 방법을 설명 합니다.  
  
## <a name="xaml-collection-concepts"></a>XAML 컬렉션 개념  
 개념적으로 XAML 개체 요소 범위 내에서 여러 개의 자식 항목이 위치나 XAML 속성 요소를 컬렉션으로 구현 해야 하는 XAML의 관계입니다. 해당 컬렉션의 해당 관계의 부모는 XAML 형식 특정 XAML 속성과 연결 해야 합니다. 속성의 각 항목에 태그를 백업 컬렉션 속성의 새로 추가 된 항목을 할당 하는 XAML 프로세서는 예상 하기 때문에 컬렉션 이어야 합니다.  
  
 XAML 언어 수준에서 지 원하는 컬렉션의 정확한 요구 사항은 완벽 하 게 정의 되어 있지 않은 합니다. 컬렉션 목록 또는 사전 (하지만 둘 다) 될 수 있음을 개념은 XAML 언어 수준에서 정의 하지만 어떤 지원 형식을 나타내는 두 목록 또는 사전 XAML 언어에 의해 정의 되지 않았습니다.  
  
 .NET Framework XAML 서비스에서 XAML 지 원하는 컬렉션의 개념은 더 명확 하 게.NET Framework 지원 형식으로 정의 됩니다. 특히, 컬렉션에 대 한 XAML 지원은 여러.NET Framework의 개념 및 목록 및 일반적인.NET Framework 프로그래밍에서 사전에 사용 되는 Api에 기반 합니다.  
  
1.  <xref:System.Collections.IList> 인터페이스 목록 컬렉션을 나타냅니다.  
  
2.  <xref:System.Collections.IDictionary> 인터페이스 dicionary 컬렉션을 나타냅니다.  
  
3.  <xref:System.Array> 지 원하는 배열 및 배열 나타냅니다 <xref:System.Collections.IList> 메서드.  
  
 호출 하는.NET Framework XAML 서비스 XAML 프로세서에서는 각 컬렉션 개념은 `Add` 컬렉션 속성 형식의 특정 인스턴스에 메서드. 또는 serialization 시나리오에서 XAML 프로세서는 목록, 사전 또는 "항목" 각 컬렉션의 특정 개념을 기준으로 배열에 있는 각 항목에 대 한 불연속 XAML 형식 인스턴스를 생성 합니다. 이들은: <xref:System.Collections.IList.Item%2A>; <xref:System.Collections.IDictionary.Item%2A>; 명시적 <xref:System.Array.System%23Collections%23IList%23Item%2A> 에 대 한 <xref:System.Array>합니다.  
  
## <a name="generic-collections"></a>제네릭 컬렉션  
 제네릭 컬렉션을 프로그래밍 하는 일반.NET Framework에 유용할 수 있습니다 및 XAML 컬렉션 속성에 사용할 수도 있습니다. 그러나 제네릭 인터페이스 <xref:System.Collections.Generic.IList%601> 및 <xref:System.Collections.Generic.IDictionary%602> 제네릭이 아닌를.NET Framework XAML 서비스 XAML 프로세서에서 식별 되지 않은 <xref:System.Collections.IList> 또는 <xref:System.Collections.IDictionary>합니다. 클래스에서 파생 하는 제네릭 컬렉션 속성 형식에 대 한 권장된 접근 방식을 인터페이스를 구현 하는 대신 <xref:System.Collections.Generic.List%601> 또는 <xref:System.Collections.Generic.Dictionary%602>합니다. 이러한 클래스 제네릭이 아닌 인터페이스를 구현 하 고 따라서 기본 구현에서 XAML 컬렉션에 대 한 예상된 지원을 포함 합니다.  
  
## <a name="read-only-collections-and-initialization-logic"></a>읽기 전용 컬렉션 및 초기화 로직을  
 .NET framework 프로그래밍에서 것은 읽기 전용 컬렉션으로 컬렉션의 값을 보유 하는 모든 속성을 확인 하려면 일반적인 디자인 패턴. 이 패턴을 보다 효율적으로 제어할 컬렉션에 수행 되는 작업 컬렉션 속성을 소유 하는 인스턴스 허용... 특히, 패턴 속성을 설정 하 여 전체 기존 컬렉션의 실수로 교체 수 없습니다. 이 패턴에서와 같은 관련 컬렉션 인터페이스 및/또는 컬렉션 형식에서 지 원하는 대로 메서드 또는 속성을 호출 하 여 호출자에 게 사용 하 여 컬렉션에 대 한 액세스 만든 대신 해야 <xref:System.Collections.IList>합니다.  
  
 이 패턴을 사용 하 여 읽기 전용 컬렉션 속성을 노출 하는 모든 클래스는 빈 컬렉션을 보유 하도록 해당 속성을 먼저 초기화 해야 하는 것을 의미 합니다. 일반적으로 초기화 하는 클래스에 대 한 구성 동작의 일부로 수행 됩니다. XAML에 대 한 유용할 것이 중요 하지만 이러한 논리는 기본 생성자를 사용 하 여 항상 참조 XAML 일반적으로 속성을 처리 하기 전에 기본 생성자를 호출 하기 때문에 (컬렉션 속성 또는 그렇지 않은 경우).  
  
## <a name="xaml-type-system-support-and-collections"></a>XAML 형식 시스템 지원 및 컬렉션  
 XAML을 구문 분석 하 고 채우거 나 컬렉션 속성을 직렬화 하는 작업의 기본 메커니즘에 외 XAML 형식 시스템에서.NET Framework XAML 서비스 구현에 xaml에서 컬렉션에 관련 된 몇 가지 디자인 기능은 포함 되어 있습니다.  
  
1.  <xref:System.Xaml.XamlType.IsCollection%2A> XAML 형식 XAML 컬렉션 지원을 제공 하는 형식으로 백업 되어 있는 경우 true를 반환 합니다.  
  
2.  <xref:System.Xaml.XamlType.IsDictionary%2A> 및 <xref:System.Xaml.XamlType.IsArray%2A> XAML 형식을 지원 되는 컬렉션 모드를 식별할 수 있습니다. 사용자 지정 XAML에 대 한.NET Framework XAML 서비스 및 XAML을 기반으로 하는 프로세서 형식 시스템 하지만 기존에 기반을 두지 <xref:System.Xaml.XamlWriter> 구현을 사용 하는 컬렉션 모드를 알고 있으면 할 수도 있습니다 사용할 방법에 대 한 호출을 확인 하기 위해 컬렉션 처리 합니다.  
  
3.  각각의 이전 속성 값은 영향을 받는 재정의가 <xref:System.Xaml.XamlType.LookupCollectionKind%2A> XAML 형식입니다.
