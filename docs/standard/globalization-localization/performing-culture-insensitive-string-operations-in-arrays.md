---
title: "배열에서 문화권을 구분하지 않는 문자열 작업 수행 | Microsoft Docs"
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
  - "배열[.NET Framework], 문화권 비구분 문자열 연산"
  - "comparer 매개 변수"
  - "문화권 비구분 문자열 연산, 배열"
ms.assetid: f12922e1-6234-4165-8896-63f0653ab478
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# 배열에서 문화권을 구분하지 않는 문자열 작업 수행
<xref:System.Array.Sort%2A?displayProperty=fullName> 및 <xref:System.Array.BinarySearch%2A?displayProperty=fullName> 메서드의 오버로드는 기본적으로 <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=fullName> 속성을 사용하여 문화권별 정렬을 수행합니다.  이러한 메서드가 반환한 문화권 구분 결과는 정렬 순서의 차이 때문에 문화권마다 다를 수 있습니다.  문화권 구분 동작이 나타나지 않게 하려면 `comparer` 매개 변수를 사용하는 이 메서드의 오버로드 중 하나를 사용합니다.  `comparer` 매개 변수는 배열의 요소를 비교할 때 사용할 <xref:System.Collections.IComparer> 구현을 지정합니다.  <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>를 사용하는 사용자 지정 고정 비교자 클래스를 매개 변수에 지정합니다.  사용자 지정 고정 비교자 클래스의 예제는 [컬렉션에서 Culture를 구분하지 않는 문자열 작업 수행](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) 항목의 "SortedList 클래스 사용" 하위 항목에 있습니다.  
  
 **참고** 비교 메서드에 **CultureInfo.InvariantCulture**를 전달하면 문화권을 구분하지 않는 비교가 수행됩니다.  그러나 파일 경로, 레지스트리 키, 환경 변수 등에 대해 비언어적인 비교를 수행하지는 않습니다.  비교 결과를 기반으로 하는 보안 결정을 지원하지도 않습니다.  비언어적인 비교나 결과 기반의 보안 결정 지원의 경우 응용 프로그램에서 <xref:System.StringComparison> 값을 받아들이는 비교 메서드를 사용해야 합니다.  그런 다음 응용 프로그램이 <xref:System.StringComparison>을 전달해야 합니다.  
  
## 참고 항목  
 <xref:System.Array.Sort%2A?displayProperty=fullName>   
 <xref:System.Array.BinarySearch%2A?displayProperty=fullName>   
 <xref:System.Collections.IComparer>   
 [Culture의 영향을 받지 않는 문자열 작업 수행](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)