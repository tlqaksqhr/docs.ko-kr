---
title: "Collections and Collection Types for XAML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 58f8e7c6-9a41-4f25-8551-c042f1315baa
caps.latest.revision: 2
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 2
---
# Collections and Collection Types for XAML
이 항목에서는 속성의 컬렉션을 지원 하 고 컬렉션 항목이 상위 개체 요소나 속성 요소를 요소의 자식으로 인스턴스화는 XAML 구문을 지원 하기 위한 형식 정의 하는 방법을 설명 합니다.  
  
## XAML 컬렉션 개념  
 개념적으로, XAML 속성 요소 컬렉션으로 구현 되어야 하거나 위치 범위 내에서 여러 하위 항목이 XAML 개체 요소 XAML의 관계입니다.  해당 컬렉션 특정 XAML 속성 XAML 형식 관계에서 부모와 연결 되어야 합니다.  XAML 프로세서의 각 항목에 새로 추가 된 항목 백업 컬렉션 속성에 태그 지정 때문에 컬렉션의 속성 이어야 합니다.  
  
 XAML 언어 수준 컬렉션 지원의 정확한 요구 사항은 완전 하 게 정의 되지 않습니다.  모음 목록 또는 사전을 \(있지만 둘 다\) 될 수 있음을 개념은 XAML 언어 수준에서 정의 된 하 고 있지만 백업 종류 중 하나 목록을 나타내는 또는 사전 XAML 언어에 의해 정의 되지 않았습니다.  
  
 에 있습니다.NET Framework XAML 서비스 개념의 XAML 컬렉션 지원의 관점에서 명확 하 게 정의 됩니다.NET Framework 지원 형식입니다.  특히, 컬렉션에 대 한 XAML 지원에 여러 가지를 기반으로 합니다.NET Framework 개념 및 목록과 사전에 일반적으로 사용 되는 Api입니다.NET Framework 프로그래밍입니다.  
  
1.  <xref:System.Collections.IList> 인터페이스 목록 컬렉션을 나타냅니다.  
  
2.  <xref:System.Collections.IDictionary> 인터페이스는 dicionary 컬렉션을 나타냅니다.  
  
3.  <xref:System.Array>배열 및 배열 지원 나타냅니다 <xref:System.Collections.IList> 메서드가 있습니다.  
  
 각 이러한 컬렉션 개념을 합니다.NET Framework XAML 서비스 XAML 프로세서가 기대를 호출 하는 `Add` 메서드의 특정 인스턴스가 컬렉션 속성의 형식입니다.  나는 serialization 시나리오에서는 개별 XAML 형식 인스턴스 목록, 사전 또는 각 컬렉션의 특정 "항목" 개념에 따라 배열의 각 항목에 대 한 XAML 프로세서가 생성 합니다.  These are : <xref:System.Collections.IList.Item%2A>;  <xref:System.Collections.IDictionary.Item%2A>; the explicit <xref:System.Array.System%23Collections%23IList%23Item%2A> for <xref:System.Array>.  
  
## 제네릭 컬렉션  
 제네릭 컬렉션 유용 하 게 사용할 수 있습니다 일반에 대 한.NET Framework 프로그래밍 및 XAML 컬렉션 속성을 사용할 수 있습니다.  그러나 제네릭 인터페이스 <xref:System.Collections.Generic.IList%601> 및 <xref:System.Collections.Generic.IDictionary%602> 으로 식별 됩니다.NET Framework XAML 서비스 XAML 프로세서가 아닌\-원본에 해당 하는 것으로 <xref:System.Collections.IList> 또는 <xref:System.Collections.IDictionary>.  인터페이스를 구현 하는 것이 아니라 제네릭 컬렉션 속성 형식에 권장 되는 방법 클래스에서 파생 된 <xref:System.Collections.Generic.List%601> 또는 <xref:System.Collections.Generic.Dictionary%602>.  이러한 클래스는 제네릭이 아닌 인터페이스를 구현 및 따라서 XAML 컬렉션에 대 한 예상된 지원의 기본 구현을 포함 합니다.  
  
## 읽기 전용 컬렉션 및 초기화 논리  
 에 있습니다.NET Framework 프로그래밍에서 값은 읽기 전용 컬렉션으로 컬렉션의 모든 속성을 확인 하는 일반적인 디자인 패턴입니다.  이 패턴 인스턴스 컬렉션에는 어떻게 더 나은 컨트롤에 컬렉션 속성을 소유 하 고 있습니다.  특히 패턴 속성을 설정 하 여 전체 컬렉션을 기존의 실수로 인 한 교체가 되지 않습니다.  이 패턴에서 호출자가 컬렉션에 임의의 대 대신 컬렉션 형식 및\/또는 관련 컬렉션 인터페이스를 지원 되는 속성 또는 메서드를 호출 하 여 이루어져야 합니다 <xref:System.Collections.IList>.  
  
 이 패턴을 사용 하 여 해당 속성은 빈 컬렉션을 보유 하는 읽기 전용 컬렉션 속성을 노출 하는 클래스 먼저 초기화 해야 한다는 의미입니다.  일반적으로 클래스를 생성 동작의 일부로 초기화를 수행 합니다.  기본 생성자는 속성을 처리 하기 전에 일반적으로 XAML를 호출 하므로 XAML에 대 한 유용 합니다, 이러한 논리가 기본 생성자가 항상 참조 되는 것이 중요 \(컬렉션 속성 또는 그렇지 않으면\).  
  
## XAML 형식 시스템 지원 및 컬렉션  
 XAML 구문 분석 및 채우기 또는 컬렉션 속성 serialize 할 기본 메커니즘 외에 XAML 입력 시스템에 구현 된.NET Framework XAML 서비스 XAML에서 컬렉션에 해당 하는 몇 가지 디자인 기능을 포함 합니다.  
  
1.  <xref:System.Xaml.XamlType.IsCollection%2A>XAML 형식은 XAML 컬렉션 지원 기능을 제공 하는 형식으로 백업 될 경우 true를 반환 합니다.  
  
2.  <xref:System.Xaml.XamlType.IsDictionary%2A>및 <xref:System.Xaml.XamlType.IsArray%2A> 또한 XAML 형식 지원 하는 컬렉션 모드를 식별할 수 있습니다.  사용자 지정 XAML 프로세서에는 기반으로 합니다.NET Framework XAML 서비스 및 XAML 형식 시스템 있지만 기존에 따라 <xref:System.Xaml.XamlWriter> 구현을 알아야 하는 컬렉션 모드를 사용 해야 할 수 있습니다 컬렉션 처리 하기 위해 호출할 메서드를 알 수 있습니다.  
  
3.  각각 이전 속성 값에는 잠재적으로 영향을 재정의 의해 <xref:System.Xaml.XamlType.LookupCollectionKind%2A> XAML 형식입니다.