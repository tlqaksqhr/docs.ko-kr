---
title: "정규식의 컴파일 및 다시 사용 | Microsoft Docs"
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
  - ".NET Framework 정규식, 컴파일"
  - ".NET Framework 정규식, 엔진"
  - "컴파일, 정규식"
  - "정규식으로 텍스트 구문 분석, 컴파일"
  - "정규식과 패턴 일치, 컴파일"
  - "정규식, 컴파일"
  - "정규식, 엔진"
  - "정규식으로 검색, 컴파일"
ms.assetid: 182ec76d-5a01-4d73-996c-0b0d14fcea18
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# 정규식의 컴파일 및 다시 사용
정규식 엔진에서 식을 컴파일하는 방법과 정규식이 캐시되는 방법에 대해 알고 있으면 정규식을 폭넓게 사용하는 응용 프로그램의 성능을 최적화할 수 있습니다.  이 항목에서는 컴파일과 캐싱에 대해 설명합니다.  
  
## 컴파일된 정규식 비교  
 기본적으로, 정규식 엔진은 정규식을 일련의 내부 지침으로 컴파일하는데, 이러한 내부 지침은 고급 코드로서 MSIL\(Microsoft Intermediate Language\)과 다릅니다.  엔진은 정규식을 처리할 때 이러한 내부 코드를 해석합니다.  
  
 <xref:System.Text.RegularExpressions.Regex> 개체가 <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> 옵션을 사용하여 생성된 경우 정규식 엔진에서는 고급 정규식 내부 지침 코드가 아닌 명시적 MSIL 코드로 정규식을 컴파일합니다.  이렇게 하면 .NET Framework의 JIT\(Just\-In\-Time\) 컴파일러에서 이 식을 네이티브 기계어 코드로 변환하여 성능을 향상시킬 수 있습니다.  
  
 그러나 생성된 MSIL은 언로드될 수 없으며  코드를 언로드할 수 있는 유일한 방법은 응용 프로그램 도메인 전체, 즉 응용 프로그램의 모든 코드를 언로드하는 것입니다.  실제적으로, <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> 옵션을 사용하여 정규식을 컴파일하면 정규식을 만든 <xref:System.Text.RegularExpressions.Regex> 개체가 해제되어 가비지 수집된 후에도 .NET Framework에서는 컴파일된 해당 식에서 사용하는 리소스를 해제하지 않습니다.  
  
 따라서, <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName> 옵션으로 컴파일할 정규식의 수를 제한하여 너무 많은 리소스를 사용하지 않도록 해야 합니다.  응용 프로그램에서 제한 없는 수의 여러 정규식을 사용해야 한다면 각 식을 컴파일하지 않고 대신 해석하는 것이 좋습니다.  그러나 적은 수의 정규식을 반복적으로 사용해야 하는 경우에는 성능을 높일 수 있도록 이들 정규식을 <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>로 컴파일하는 것이 좋습니다.  다른 방법은 미리 컴파일된 정규식을 사용하는 것입니다.  <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A> 메서드를 사용하여 모든 식을 다시 사용할 수 있는 DLL로 컴파일할 수 있습니다.  이렇게 하면 런타임에 컴파일할 필요가 없고 정규식이 컴파일되어 있으므로 속도도 빨라집니다.  
  
## 정규식 캐시  
 정규식 엔진에서는 성능을 향상시키기 위해 컴파일된 정규식에 대해 응용 프로그램 수준의 캐시를 유지 관리합니다.  이 캐시에는 정적 메서드 호출에서만 사용되는 정규식 패턴이 저장됩니다. 인스턴스 메서드에 지정된 정규식 패턴은 캐시되지 않습니다. 정규식을 사용할 때마다 해당 정규식을 고급 바이트 코드로 다시 분석하지 않아도 됩니다.  
  
 캐시되는 최대 정규식 수는 `static`\(Visual Basic의 경우 `Shared`\) <xref:System.Text.RegularExpressions.Regex.CacheSize%2A?displayProperty=fullName> 속성의 값에 따라 결정됩니다.  기본적으로 정규식 엔진에서는 최대 15개의 컴파일된 정규식을 캐시합니다.  컴파일된 정규식의 수가 캐시 크기를 초과하는 경우에는 가장 오래 전에 사용된 정규식이 삭제되고 새 정규식이 캐시됩니다.  
  
> [!IMPORTANT]
>  .NET Framework 버전 2.0에서 정규식이 캐시되는 방식은 .NET Framework 버전 1.0 및 1.1과 상당히 다릅니다.  .NET Framework 1.0 및 1.1에서는 정적 메서드 호출과 인스턴스 메서드 호출에서 사용되는 정규식이 모두 캐시됩니다.  그리고 새 정규식을 저장하기 위해 캐시가 자동으로 확장됩니다.  반면 .NET Framework 2.0에서는 정적 메서드 호출에서 사용된 정규식만 캐시됩니다.  그리고 <xref:System.Text.RegularExpressions.Regex.CacheSize%2A> 속성 값을 설정하여 캐시 크기를 조정할 수는 있지만 기본적으로 15개의 최근 정규식만 캐시됩니다.  
  
 응용 프로그램에서는 다음과 같은 두 가지 방법 중 하나로 미리 컴파일된 정규식을 사용할 수 있습니다.  
  
-   <xref:System.Text.RegularExpressions.Regex> 개체의 정적 메서드를 사용하여 정규식을 정의합니다.  다른 정적 메서드 호출에서 이미 정의한 정규식 패턴을 사용할 경우 정규식 엔진은 캐시에서 이 패턴을 검색합니다.  그렇지 않을 경우 엔진에서는 정규식을 컴파일하여 캐시에 추가합니다.  
  
-   기존 <xref:System.Text.RegularExpressions.Regex> 개체의 정규식 패턴이 필요한 경우에 한해 이 개체를 다시 사용합니다.  
  
 개체 인스턴스화 및 정규식 컴파일의 오버헤드로 인해 많은 수의 <xref:System.Text.RegularExpressions.Regex> 개체를 만들고 신속하게 소멸하려면 비용이 많이 듭니다.  많은 수의 정규식을 사용하는 응용 프로그램의 경우 정적 `Regex` 메서드에 대한 호출을 사용하고 정규식 캐시의 크기를 늘려서 성능을 최적화할 수 있습니다.  
  
## 참고 항목  
 [.NET Framework 정규식](../../../docs/standard/base-types/regular-expressions.md)