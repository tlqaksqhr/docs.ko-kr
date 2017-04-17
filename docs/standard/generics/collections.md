---
title: ".NET Framework의 제네릭 컬렉션 | Microsoft Docs"
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
  - "제네릭 컬렉션[.NET Framework]"
  - "제네릭[.NET Framework], 컬렉션"
ms.assetid: 5b646751-6ab7-465c-916c-b1a76aefa9f5
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# .NET Framework의 제네릭 컬렉션
이 항목에서는 .NET Framework의 제네릭 컬렉션 클래스 및 기타 제네릭 형식을 개략적으로 설명합니다.  
  
## .NET Framework의 제네릭 컬렉션  
 .NET Framework 클래스 라이브러리는 <xref:System.Collections.Generic> 및 <xref:System.Collections.ObjectModel> 네임스페이스에서 다양한 제네릭 컬렉션 클래스를 제공합니다.  이러한 클래스에 대한 자세한 내용은 [일반적으로 사용되는 컬렉션 형식](../../../docs/standard/collections/commonly-used-collection-types.md)을 참조하세요.  
  
### System.Collections.Generic  
 대부분의 제네릭 컬렉션 형식은 제네릭이 아닌 형식과 직접적인 연관이 있습니다.  <xref:System.Collections.Generic.Dictionary%602>는 <xref:System.Collections.Hashtable>의 제네릭 버전으로, <xref:System.Collections.DictionaryEntry> 대신 제네릭 구조체인 <xref:System.Collections.Generic.KeyValuePair%602>를 열거형에 사용합니다.  
  
 <xref:System.Collections.Generic.List%601>은 <xref:System.Collections.ArrayList>의 제네릭 버전입니다.  제네릭이 아닌 버전에 해당하는 제네릭 <xref:System.Collections.Generic.Queue%601> 및 <xref:System.Collections.Generic.Stack%601> 클래스가 있습니다.  
  
 <xref:System.Collections.Generic.SortedList%602>의 제네릭 버전과 제네릭이 아닌 버전이 있습니다.  두 버전은 모두 사전과 목록의 하이브리드입니다.  <xref:System.Collections.Generic.SortedDictionary%602> 제네릭 클래스는 순수 사전이며 제네릭이 아닌 대응 항목이 없습니다.  
  
 <xref:System.Collections.Generic.LinkedList%601> 제네릭 클래스는 연결된 목록입니다.  제네릭이 아닌 대응 항목이 없습니다.  
  
### System.Collections.ObjectModel  
 <xref:System.Collections.ObjectModel.Collection%601> 제네릭 클래스는 고유한 제네릭 컬렉션 형식을 파생시키기 위한 기본 클래스를 제공합니다.  <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> 클래스는 <xref:System.Collections.Generic.IList%601> 제네릭 인터페이스를 구현하는 형식에서 읽기 전용 컬렉션을 생성하는 편리한 방법을 제공합니다.  <xref:System.Collections.ObjectModel.KeyedCollection%602> 제네릭 클래스는 고유한 키를 포함하는 개체를 저장하는 방법을 제공합니다.  
  
## 기타 제네릭 형식  
 <xref:System.Nullable%601> 제네릭 구조체를 통해 `null`이 할당될 수 있는 것처럼 값 형식을 사용할 수 있습니다.  이 기능은 값 형식을 포함하는 필드가 누락될 수 있는 데이터베이스 쿼리를 사용할 때 유용할 수 있습니다.  제네릭 형식 매개 변수는 임의의 값 형식일 수 있습니다.  
  
> [!NOTE]
>  C\#에서는 언어에 nullable 형식에 대한 구문이 있기 때문에 명시적으로 <xref:System.Nullable%601>을 사용해야 합니다.  
  
 <xref:System.ArraySegment%601> 제네릭 구조체는 0부터 시작하는 임의 형식의 1차원 배열 내에서 요소 범위를 구분하는 방법을 제공합니다.  제네릭 형식 매개 변수는 배열 요소의 형식입니다.  
  
 이벤트가 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]에서 사용되는 이벤트 처리 패턴을 따르는 경우 <xref:System.EventHandler%601> 제네릭 대리자를 사용하면 이벤트를 처리할 대리자 형식을 선언할 필요가 없습니다.  예를 들어 이벤트 데이터를 저장할 <xref:System.EventArgs>에서 파생된 `MyEventArgs` 클래스를 만들었다고 가정합니다.  그런 다음 이벤트를 다음과 같이 선언할 수 있습니다.  
  
 [!code-cpp[Conceptual.Generics.Overview#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.generics.overview/cpp/source2.cpp#7)]
 [!code-csharp[Conceptual.Generics.Overview#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.generics.overview/cs/source2.cs#7)]
 [!code-vb[Conceptual.Generics.Overview#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.generics.overview/vb/source2.vb#7)]  
  
## 참고 항목  
 <xref:System.Collections.Generic?displayProperty=fullName>   
 <xref:System.Collections.ObjectModel?displayProperty=fullName>   
 [제네릭](../../../docs/standard/generics/index.md)   
 [배열과 목록을 조작하기 위한 제네릭 대리자](../../../docs/standard/generics/delegates-for-manipulating-arrays-and-lists.md)   
 [제네릭 인터페이스](../../../docs/standard/generics/interfaces.md)