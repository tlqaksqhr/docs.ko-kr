---
title: "정규식의 컴파일 및 다시 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parsing text with regular expressions, compilation
- searching with regular expressions, compilation
- .NET Framework regular expressions, engines
- .NET Framework regular expressions, compilation
- regular expressions, compilation
- compilation, regular expressions
- pattern-matching with regular expressions, compilation
- regular expressions, engines
ms.assetid: 182ec76d-5a01-4d73-996c-0b0d14fcea18
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 76acdf2d0d2f7805ec78ea44136bfc63441b9bc9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="compilation-and-reuse-in-regular-expressions"></a>정규식의 컴파일 및 다시 사용
정규식 엔진이 식을 컴파일하는 방법과 정규식이 캐시되는 방식을 이해하면 정규식을 광범위하게 사용하는 응용 프로그램의 성능을 최적화할 수 있습니다. 이 항목에서는 컴파일과 캐시 둘 다에 대해 설명합니다.  
  
## <a name="compiled-regular-expressions"></a>컴파일된 정규식  
 기본적으로 정규식 엔진은 정규식을 내부 명령 시퀀스(Microsoft 중간 언어, 즉 MSIL과 다른 고급 코드)로 컴파일합니다. 엔진은 정규식을 실행할 때 내부 코드를 해석합니다.  
  
 경우는 <xref:System.Text.RegularExpressions.Regex> 개체로 구성 되며는 <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> 옵션을 정규식을 고급 정규식 내부 지침 대신 명시적 MSIL 코드를 컴파일합니다. 이렇게 하면 .NET의 JIT(Just-In-Time) 컴파일러가 성능 향상을 위해 식을 네이티브 기계어 코드로 변환할 수 있습니다.  
  
그러나 생성된 MSIL을 언로드할 수 없습니다. 코드를 언로드하는 유일한 방법은 전체 응용 프로그램 도메인을 언로드하는 것(즉, 모든 응용 프로그램 코드 언로드)입니다. 효과적으로 정규식으로 컴파일되면는 <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> 옵션, 정규식에서 작성 된 경우에 컴파일된 식을 사용 하는 리소스를 해제 하지 않습니다는 <xref:System.Text.RegularExpressions.Regex> 자체가 가비지 수집을 해제 하는 개체입니다.  
  
 다른 정규식 사용 하 여 컴파일할 수를 제한 해야는 <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> 너무 많은 리소스를 사용 하지 않도록 하려면 옵션입니다. 응용 프로그램이 많거나 무제한 개수의 정규식을 사용해야 하는 경우 각 식을 컴파일하지 않고 해석해야 합니다. 그러나 정규식 수가 적은 반복 해 서 사용 되는 경우 이러한 사용 컴파일해야 <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> 성능 향상을 위해 합니다. 대신 미리 컴파일된 정규식을 사용 하는 것입니다. 사용 하 여 모든 식을 다시 사용할 수 있는 DLL로 컴파일할 수 있습니다는 <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A> 메서드. 이렇게 하면 런타임 시 컴파일된 정규식의 속도 없으면서도 컴파일할 필요가 없습니다.  
  
## <a name="the-regular-expressions-cache"></a>정규식 캐시  
 성능 향상을 위해 정규식 엔진은 응용 프로그램 수준의 컴파일된 정규식 캐시를 유지 관리합니다. 캐시는 정적 메서드 호출에만 사용되는 정규식 패턴을 저장합니다. 인스턴스 메서드에 제공된 정규식 패턴은 캐시되지 않습니다. 따라서 사용할 때마다 식을 고급 바이트 코드로 다시 구문 분석할 필요가 없습니다.  
  
 캐시 된 정규식의 최대 수의 값에 의해 결정 됩니다는 `static` (`Shared` Visual basic에서) <xref:System.Text.RegularExpressions.Regex.CacheSize%2A?displayProperty=nameWithType> 속성입니다. 기본적으로 정규식 엔진은 최대 15개의 컴파일된 정규식을 캐시합니다. 컴파일된 정규식 개수가 캐시 크기를 초과하면 가장 오래 전에 사용한 정규식이 삭제되고 새 정규식이 캐시됩니다.  
  
 응용 프로그램은 다음 두 가지 방법 중 하나로 미리 컴파일된 정규식을 활용할 수 있습니다.  
  
-   정적 메서드를 사용 하 여는 <xref:System.Text.RegularExpressions.Regex> 정규식을 정의 하는 개체입니다. 다른 정적 메서드 호출에서 이미 정의된 정규식 패턴을 사용하는 경우 정규식 엔진이 캐시에서 검색합니다. 이미 정의된 정규식 패턴을 사용하지 않는 경우 엔진이 정규식을 컴파일하고 캐시에 추가합니다.  
  
-   기존 다시 사용 하 여 <xref:System.Text.RegularExpressions.Regex> 정규식 패턴은 필요한 경우 개체입니다.  
  
 개체 인스턴스화 및 만들고 신속 하 게 삭제 하면 다양 한 정규식 컴파일 오버 헤드로 인해 <xref:System.Text.RegularExpressions.Regex> 개체는 비용이 많이 드는 프로세스입니다. 많은 수의 정규식을 사용 하는 응용 프로그램의 경우 정적에 대 한 호출을 사용 하 여 성능을 최적화할 수 `Regex` 메서드와 늘려서 정규식 캐시의 크기입니다.  
  
## <a name="see-also"></a>참고 항목  
 [.NET 정규식](../../../docs/standard/base-types/regular-expressions.md)
