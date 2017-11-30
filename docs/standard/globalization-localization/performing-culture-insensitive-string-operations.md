---
title: "Culture의 영향을 받지 않는 문자열 작업 수행"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- case mappings
- custom case mappings
- culture, custom sorting rules
- custom sorting rules
- culture-insensitive string operations, options for performing
- culture, custom case mappings
- culture-insensitive string operations, method overloads
ms.assetid: 579ef891-1f83-4c63-9ebd-2f40406b5b91
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e703e9adc531b7d1695d3e9bbed61a2c0f62ad31
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="performing-culture-insensitive-string-operations"></a>Culture의 영향을 받지 않는 문자열 작업 수행
명시적으로 전달 하 여 사용할 문화권을 지정할 수 있도록 하는 메서드 오버 로드를 제공 하는 기본적으로 문화권 구분 문자열 작업을 수행 하는 대부분의.NET Framework 메서드는 <xref:System.Globalization.CultureInfo> 매개 변수입니다. 이러한 오버로드를 사용하여 매핑 및 정렬 규칙이 문화권을 구분하지 않는 결과를 보장할 경우 문화권 변동을 제거할 수 있습니다.  
  
 이 섹션에서는 기본적으로 문화권을 구분하는 .NET Framework 메서드를 사용하여 문화권을 구분하지 않는 문자열 작업을 수행하는 방법을 보여 주기 위해 다음 항목을 제공합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [문화권을 구분하지 않는 문자열 비교 수행](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-comparisons.md)  
 사용 하는 방법에 설명 된 <xref:System.String.Compare%2A?displayProperty=nameWithType> 및 <xref:System.String.CompareTo%2A?displayProperty=nameWithType> 문화권을 구분 하지 않는 문자열 비교를 수행 하는 메서드.  
  
 [문화권을 구분하지 않는 대/소문자 변경 수행](../../../docs/standard/globalization-localization/performing-culture-insensitive-case-changes.md)  
 사용 하는 방법에 설명 된 <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>, 및 <xref:System.Char.ToLower%2A?displayProperty=nameWithType> 문화권을 구분 하지 않는 대/소문자 변경 수행 하는 메서드.  
  
 [컬렉션에서 문화권을 구분하지 않는 문자열 작업 수행](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md)  
 사용 하는 방법에 설명는 <xref:System.Collections.CaseInsensitiveComparer>, <xref:System.Collections.CaseInsensitiveHashCodeProvider> 클래스 <xref:System.Collections.SortedList>, <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> 및 <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> 컬렉션의 문화권을 구분 하지 않는 작업을 수행할 수 있습니다.  
  
 [배열에서 문화권을 구분하지 않는 문자열 작업 수행](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md)  
 사용 하는 방법에 설명 된 <xref:System.Array.Sort%2A?displayProperty=nameWithType> 및 <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> 배열에서 문화권을 구분 하지 않는 작업을 수행 하는 메서드.  
  
## <a name="related-sections"></a>관련 단원  
 [문화권을 구분하지 않는 문자열 작업](../../../docs/standard/globalization-localization/culture-insensitive-string-operations.md)  
 문자열에 대해 작업을 수행할 때 문화권을 알아야 하는 이유를 설명하고 문화권 구분 작업을 수행해야 하는 경우 및 문화권을 구분하지 않는 작업을 수행해야 하는 경우에 대한 지침을 제공합니다.
