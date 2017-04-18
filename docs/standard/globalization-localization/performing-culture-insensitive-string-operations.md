---
title: "Culture의 영향을 받지 않는 문자열 작업 수행 | Microsoft Docs"
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
  - "대/소문자 매핑"
  - "사용자 지정 대/소문자 매핑"
  - "문화권, 사용자 지정 정렬 규칙"
  - "사용자 지정 정렬 규칙"
  - "문화권을 구분하지 않는 문자열 작업, 수행할 옵션"
  - "문화권, 사용자 지정 대/소문자 매핑"
  - "문화권 비구분 문자열 연산, 메서드 오버로드"
ms.assetid: 579ef891-1f83-4c63-9ebd-2f40406b5b91
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Culture의 영향을 받지 않는 문자열 작업 수행
문화권별 문자열 작업을 수행하는 대부분의 .NET Framework 메서드는 기본적으로 <xref:System.Globalization.CultureInfo> 매개 변수를 제공하여 사용할 문화권을 명시적으로 지정할 수 있는 메서드 오버로드를 제공합니다.  이러한 오버로드를 통해 문화권에 관계없이 일정한 대\/소문자 매핑 및 정렬 규칙을 적용하고 문화권을 구분하지 않는 결과를 얻을 수 있습니다.  
  
 이 단원은 기본적으로 문화권에 따라 다른 .NET Framework 메서드를 사용하여 문화권을 구분하지 않는 문자열 작업을 수행하는 방법을 보여 주는 다음 항목을 제공합니다.  
  
## 단원 내용  
 [문화권을 구분하지 않는 문자열 비교 수행](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-comparisons.md)  
 <xref:System.String.Compare%2A?displayProperty=fullName> 및 <xref:System.String.CompareTo%2A?displayProperty=fullName> 메서드를 사용하여 문화권을 구분하지 않고 문자열을 비교하는 방법을 보여 줍니다.  
  
 [문화권을 구분하지 않는 대\/소문자 변경 수행](../../../docs/standard/globalization-localization/performing-culture-insensitive-case-changes.md)  
 <xref:System.String.ToUpper%2A?displayProperty=fullName>, <xref:System.String.ToLower%2A?displayProperty=fullName>, <xref:System.Char.ToUpper%2A?displayProperty=fullName> 및 <xref:System.Char.ToLower%2A?displayProperty=fullName> 메서드를 사용하여 문화권을 구분하지 않고 대\/소문자를 변경하는 방법을 보여 줍니다.  
  
 [컬렉션에서 문화권을 구분하지 않는 문자열 작업 수행](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md)  
 [CaseInsensitiveComparer 클래스](frlrfSystemCollectionsCaseInsensitiveComparerClassTopic), <xref:System.Collections.CaseInsensitiveHashCodeProvider> 클래스, [SortedList 클래스](frlrfSystemCollectionsSortedListClassTopic), [ArrayList.Sort 메서드](https://msdn.microsoft.com/en-us/library/system.collections.arraylist.sort.aspx) 및 [CollectionsUtil.CreateCaseInsensitiveHashtable 메서드](frlrfSystemCollectionsSpecializedCollectionsUtilClassCreateCaseInsensitiveHashtableTopic)를 사용하여 컬렉션에서 문화권을 구분하지 않는 작업을 수행하는 방법에 대해 설명합니다.  
  
 [배열에서 문화권을 구분하지 않는 문자열 작업 수행](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md)  
 <xref:System.Array.Sort%2A?displayProperty=fullName> 및 <xref:System.Array.BinarySearch%2A?displayProperty=fullName> 메서드를 사용하여 문화권을 구분하지 않는 배열 작업을 수행하는 방법을 보여 줍니다.  
  
## 관련 단원  
 [문화권을 구분하지 않는 문자열 작업](../../../docs/standard/globalization-localization/culture-insensitive-string-operations.md)  
 문자열에 대해 작업을 수행할 때 문화권을 알고 있어야 하는 이유를 설명하고 언제 culture에 따라 다른 작업을 수행하고 문화권을 구분하지 않는 작업을 수행해야 하는지에 대한 지침을 제공합니다.