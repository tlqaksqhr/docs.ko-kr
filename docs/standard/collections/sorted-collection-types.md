---
title: "Sorted 컬렉션 형식 | Microsoft Docs"
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
  - "컬렉션[.NET Framework], SortedList 컬렉션 형식"
  - "컬렉션의 데이터 그룹화, SortedList 컬렉션 형식"
  - "SortedDictionary 컬렉션 형식"
  - "SortedList 클래스, 컬렉션의 데이터 그룹화"
  - "SortedList 컬렉션 형식"
ms.assetid: 3db965b2-36a6-4b12-b76e-7f074ff7275a
caps.latest.revision: 16
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 16
---
# Sorted 컬렉션 형식
<xref:System.Collections.SortedList?displayProperty=fullName> 클래스, <xref:System.Collections.Generic.SortedList%602?displayProperty=fullName> 제네릭 클래스 및 <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName> 제네릭 클래스는 <xref:System.Collections.IDictionary> 인터페이스를 구현한다는 점에서 <xref:System.Collections.Hashtable> 클래스 및 <xref:System.Collections.Generic.Dictionary%602> 제네릭 클래스와 유사하지만 요소를 키별 정렬 순서로 유지하며 해시 테이블의 O\(1\) 삽입 및 검색 특징이 없다는 점에서 다릅니다.  이 세 클래스에는 다음과 같이 공통적인 기능이 많이 있습니다.  
  
-   세 클래스 모두 <xref:System.Collections.IDictionary?displayProperty=fullName> 인터페이스를 구현합니다.  두 제네릭 클래스는 <xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName> 제네릭 인터페이스도 구현합니다.  
  
-   각 요소는 열거형 용도를 위한 키\/값 쌍입니다.  
  
    > [!NOTE]
    >  제네릭이 아닌 <xref:System.Collections.SortedList> 클래스는 열거될 때 <xref:System.Collections.DictionaryEntry> 개체를 반환하지만 두 제네릭 형식은 <xref:System.Collections.Generic.KeyValuePair%602> 개체를 반환합니다.  
  
-   요소는 제네릭이 아닌 <xref:System.Collections.SortedList>의 경우 <xref:System.Collections.IComparer?displayProperty=fullName> 구현에 따라 정렬되며 두 제네릭 클래스의 경우 <xref:System.Collections.Generic.IComparer%601?displayProperty=fullName> 구현에 따라 정렬됩니다.  
  
-   각 클래스는 키만 또는 값만 포함하는 컬렉션을 반환하는 속성을 제공합니다.  
  
 다음 표에서는 정렬된 두 목록 클래스와 <xref:System.Collections.Generic.SortedDictionary%602> 클래스 간의 몇 가지 차이점을 보여 줍니다.  
  
|제네릭이 아닌 <xref:System.Collections.SortedList> 클래스 및 <xref:System.Collections.Generic.SortedList%602> 제네릭 클래스|<xref:System.Collections.Generic.SortedDictionary%602> 제네릭 클래스|  
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|키와 값을 반환하는 속성은 효율적인 인덱싱된 검색을 위해 인덱싱됩니다.|인덱싱된 검색을 수행하지 않습니다.|  
|검색이 O\(log `n`\)입니다.|검색이 O\(log `n`\)입니다.|  
|삽입 및 제거는 일반적으로 O\(`n`\)이지만 삽입은 이미 정렬 순서로 되어 있는 데이터의 경우 O\(1\)이므로 각 요소가 목록 끝에 추가됩니다. 이 경우 크기 조정이 필요하지 않다고 가정합니다.|삽입 및 제거는 O\(log `n`\)입니다.|  
|<xref:System.Collections.Generic.SortedDictionary%602>보다 메모리를 적게 사용합니다.|제네릭이 아닌 <xref:System.Collections.SortedList> 클래스 및 <xref:System.Collections.Generic.SortedList%602> 제네릭 클래스보다 메모리를 많이 사용합니다.|  
  
 여러 스레드에서 동시에 액세스할 수 있어야 하는 정렬된 목록 또는 사전의 경우 <xref:System.Collections.Concurrent.ConcurrentDictionary%602>에서 파생되는 클래스에 정렬 논리를 추가할 수 있습니다.  
  
> [!NOTE]
>  직원 ID 번호를 포함하는 직원 레코드와 같이 고유한 키를 포함하는 값의 경우 <xref:System.Collections.ObjectModel.KeyedCollection%602> 제네릭 클래스에서 파생하여 목록의 일부 특징과 사전의 일부 특징이 있는 키 컬렉션을 만들 수 있습니다.  
  
 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]부터는 <xref:System.Collections.Generic.SortedSet%601> 클래스에서 삽입, 삭제 및 검색 후에 데이터를 정렬된 순서로 유지하는 자체 균형 조정 트리를 제공합니다.  이 클래스와 <xref:System.Collections.Generic.HashSet%601> 클래스는 <xref:System.Collections.Generic.ISet%601> 인터페이스를 구현합니다.  
  
## 참고 항목  
 <xref:System.Collections.IDictionary?displayProperty=fullName>   
 <xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>   
 <xref:System.Collections.Concurrent.ConcurrentDictionary%602>   
 [일반적으로 사용되는 컬렉션 형식](../../../docs/standard/collections/commonly-used-collection-types.md)