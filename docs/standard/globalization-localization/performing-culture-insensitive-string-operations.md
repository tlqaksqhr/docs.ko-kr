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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 62aa839d2dae2f6dc84d529a8abf5061367f221f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="performing-culture-insensitive-string-operations"></a>Culture의 영향을 받지 않는 문자열 작업 수행
문화권 구분 문자열 작업을 수행하는 대부분의 .NET Framework 메서드는 기본적으로 <xref:System.Globalization.CultureInfo> 매개 변수를 전달하여 사용할 문화권을 명시적으로 지정할 수 있도록 하는 메서드 오버로드를 제공합니다. 이러한 오버로드를 사용하여 매핑 및 정렬 규칙이 문화권을 구분하지 않는 결과를 보장할 경우 문화권 변동을 제거할 수 있습니다.  
  
 이 섹션에서는 기본적으로 문화권을 구분하는 .NET Framework 메서드를 사용하여 문화권을 구분하지 않는 문자열 작업을 수행하는 방법을 보여 주기 위해 다음 항목을 제공합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [문화권을 구분하지 않는 문자열 비교 수행](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-comparisons.md)  
 <xref:System.String.Compare%2A?displayProperty=nameWithType> 및 <xref:System.String.CompareTo%2A?displayProperty=nameWithType> 메서드를 사용하여 문화권을 구분하지 않는 문자열 비교를 수행하는 방법에 대해 설명합니다.  
  
 [문화권을 구분하지 않는 대/소문자 변경 수행](../../../docs/standard/globalization-localization/performing-culture-insensitive-case-changes.md)  
 <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType> 및 <xref:System.Char.ToLower%2A?displayProperty=nameWithType> 메서드를 사용하여 문화권을 구분하지 않는 대/소문자 변경을 수행하는 방법에 대해 설명합니다.  
  
 [컬렉션에서 문화권을 구분하지 않는 문자열 작업 수행](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md)  
 <xref:System.Collections.CaseInsensitiveComparer> 및 <xref:System.Collections.CaseInsensitiveHashCodeProvider> 클래스, <xref:System.Collections.SortedList>, <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> 및 <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> 메서드를 사용하여 컬렉션에서 문화권을 구분하지 않는 작업을 수행하는 방법에 대해 설명합니다.  
  
 [배열에서 문화권을 구분하지 않는 문자열 작업 수행](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md)  
 <xref:System.Array.Sort%2A?displayProperty=nameWithType> 및 <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> 메서드를 사용하여 배열에서 문화권을 구분하지 않는 작업을 수행하는 방법에 대해 설명합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [문화권을 구분하지 않는 문자열 작업](../../../docs/standard/globalization-localization/culture-insensitive-string-operations.md)  
 문자열에 대해 작업을 수행할 때 문화권을 알아야 하는 이유를 설명하고 문화권 구분 작업을 수행해야 하는 경우 및 문화권을 구분하지 않는 작업을 수행해야 하는 경우에 대한 지침을 제공합니다.
