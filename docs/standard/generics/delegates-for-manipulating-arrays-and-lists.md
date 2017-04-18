---
title: "배열과 목록을 조작하기 위한 제네릭 대리자 | Microsoft Docs"
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
  - "배열[.NET Framework], 제네릭 대리자"
  - "대리자 연결"
  - "대리자[.NET Framework], 제네릭 대리자"
  - "제네릭 대리자[.NET Framework]"
  - "제네릭[.NET Framework], 대리자"
  - "목록[.NET Framework], 제네릭 대리자"
ms.assetid: 416be383-cc61-4102-9b1b-88b51adb963e
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# 배열과 목록을 조작하기 위한 제네릭 대리자
이 항목에서는 배열 또는 컬렉션의 요소에 대해 수행할 작업, 검색 조건자 및 변환을 위한 제네릭 대리자에 대해 간략하게 설명합니다.  
  
## 배열과 목록을 조작하기 위한 제네릭 대리자  
 <xref:System.Action%601> 제네릭 대리자는 지정된 형식의 요소에 대해 작업을 수행하는 메서드를 나타냅니다.  요소에 대해 원하는 작업을 수행하는 메서드를 만들고, 해당 메서드를 나타내는 <xref:System.Action%601> 대리자의 인스턴스를 만든 다음 배열과 대리자를 <xref:System.Array.ForEach%2A?displayProperty=fullName> 정적 제네릭 메서드에 전달할 수 있습니다.  메서드는 배열의 각 요소에 대해 호출됩니다.  
  
 <xref:System.Collections.Generic.List%601> 제네릭 클래스는 <xref:System.Action%601> 대리자를 사용하는 <xref:System.Collections.Generic.List%601.ForEach%2A> 메서드도 제공합니다.  이 메서드는 제네릭이 아닙니다.  
  
> [!NOTE]
>  이 경우 제네릭 형식 및 메서드에 대한 흥미로운 사항이 있습니다.  <xref:System.Array>가 제네릭 형식이 아니므로 <xref:System.Array.ForEach%2A?displayProperty=fullName> 메서드는 정적\(Visual Basic에서는 `Shared`\)이어야 합니다. <xref:System.Array.ForEach%2A?displayProperty=fullName>이 작동할 형식을 지정할 수 있는 유일한 이유는 메서드에 고유한 형식 매개 변수 목록에 있기 때문입니다.  반대로, 제네릭이 아닌 <xref:System.Collections.Generic.List%601.ForEach%2A?displayProperty=fullName> 메서드는 제네릭 클래스 <xref:System.Collections.Generic.List%601>에 속해 있으므로 단순히 해당 클래스의 형식 매개 변수를 사용합니다.  클래스가 강력한 형식이므로 메서드는 인스턴스 메서드일 수 있습니다.  
  
 <xref:System.Predicate%601> 제네릭 대리자는 특정 요소가 정의한 조건을 충족하는지 여부를 확인하는 메서드를 나타냅니다.  <xref:System.Array>의 정적 제네릭 메서드 <xref:System.Array.Exists%2A>, <xref:System.Array.Find%2A>, <xref:System.Array.FindAll%2A>, <xref:System.Array.FindIndex%2A>, <xref:System.Array.FindLast%2A>, <xref:System.Array.FindLastIndex%2A> 및 <xref:System.Array.TrueForAll%2A>와 함께 사용하여 요소 또는 요소 집합을 검색할 수 있습니다.  
  
 <xref:System.Predicate%601>은 <xref:System.Collections.Generic.List%601> 제네릭 클래스의 제네릭이 아닌 인스턴스 메서드에서도 작동합니다.  
  
 <xref:System.Comparison%601> 제네릭 대리자를 통해 기본 정렬 순서가 없는 배열 또는 목록 요소에 대한 정렬 순서를 제공하거나 기본 정렬 순서를 재정의할 수 있습니다.  비교를 수행하는 메서드를 만들고, 해당 메서드를 나타내는 <xref:System.Comparison%601> 대리자의 인스턴스를 만든 다음 배열과 대리자를 [Array.Sort\<T\>\(T\<xref:System.Array.Sort%60%601%28%60%600%5B%5D%2CSystem.Comparison%7B%60%600%7D%29?displayProperty=fullName> 정적 제네릭 메서드에 전달합니다.  <xref:System.Collections.Generic.List%601> 제네릭 클래스는 해당 인스턴스 메서드 오버로드인 <xref:System.Collections.Generic.List%601.Sort%28System.Comparison%7B%600%7D%29?displayProperty=fullName>을 제공합니다.  
  
 <xref:System.Converter%602> 제네릭 대리자를 통해 두 형식 간의 변환을 정의하고 한 형식의 배열을 다른 형식의 배열로 변환하거나 한 형식의 목록을 다른 형식의 목록으로 변환할 수 있습니다.  기존 목록의 요소를 새 형식으로 변환하는 메서드를 만들거나, 메서드를 나타내는 대리자 인스턴스를 만들거나, <xref:System.Array.ConvertAll%2A?displayProperty=fullName> 제네릭 정적 메서드를 사용하여 원래 배열에서 새 형식의 배열을 생성하거나, <xref:System.Collections.Generic.List%601.ConvertAll%2A?displayProperty=fullName> 제네릭 인스턴스 메서드를 사용하여 원래 목록에서 새 형식의 목록을 생성합니다.  
  
### 대리자 연결  
 이러한 대리자를 사용하는 많은 메서드는 다른 메서드로 전달될 수 있는 배열 또는 목록을 반환합니다.  예를 들어 배열의 특정 요소를 선택하고 이러한 요소는 새 형식으로 변환한 다음 새 배열에 저장하려는 경우 <xref:System.Array.FindAll%2A> 제네릭 메서드에서 반환된 배열을 <xref:System.Array.ConvertAll%2A> 제네릭 메서드에 전달할 수 있습니다.  새 요소 형식에 자연 정렬 순서가 없는 경우 <xref:System.Array.ConvertAll%2A> 제네릭 메서드에서 반환된 배열을 [Sort\<T\>\(T\<xref:System.Array.Sort%60%601%28%60%600%5B%5D%2CSystem.Comparison%7B%60%600%7D%29> 제네릭 메서드에 전달할 수 있습니다.  
  
## 참고 항목  
 <xref:System.Collections.Generic?displayProperty=fullName>   
 <xref:System.Collections.ObjectModel?displayProperty=fullName>   
 [제네릭](../../../docs/standard/generics/index.md)   
 [.NET Framework의 제네릭 컬렉션](../../../docs/standard/generics/collections.md)   
 [제네릭 인터페이스](../../../docs/standard/generics/interfaces.md)   
 [공 분산 및 반공 분산](../../../docs/standard/generics/covariance-and-contravariance.md)