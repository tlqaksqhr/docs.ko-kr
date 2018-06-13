---
title: 정규식의 스레드로부터의 안전성
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- .NET Framework regular expressions, threads
- regular expressions, threads
- searching with regular expressions, threads
- parsing text with regular expressions, threads
- pattern-matching with regular expressions, threads
ms.assetid: 7c4a167b-5236-4cde-a2ca-58646230730f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 79ca0b92cf79ca9be023925f064c1c7c16b3c9ac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33567720"
---
# <a name="thread-safety-in-regular-expressions"></a>정규식의 스레드로부터의 안전성
<xref:System.Text.RegularExpressions.Regex> 클래스 자체는 스레드로부터 안전하고 변경할 수 없습니다(읽기 전용). 즉, 모든 스레드에서 **Regex** 개체를 만들어 스레드 간에 공유할 수 있습니다. 일치하는 메서드는 모든 스레드에서 호출할 수 있고 전역 상태를 변경하지 않습니다.  
  
 그러나 **Regex**에서 반환한 결과 개체(**Match** 및 **MatchCollection**)는 단일 스레드에서 사용해야 합니다. 이런 개체의 대부분은 논리적으로 변경되지 않지만 이를 구현하면 성능을 향상시키는 몇 가지 결과의 계산이 지연될 수 있고 결과적으로 호출자는 해당 개체에 대한 액세스를 직렬화해야 합니다.  
  
 여러 스레드에서 **Regex** 결과 개체를 공유할 수 없는 경우 이러한 개체는 동기화된 메서드를 호출하여 스레드로부터 안전한 인스턴스로 변환할 수 있습니다. 열거자를 제외한 모든 정규식 클래스는 스레드로부터 안전하거나 동기화된 메서드에서 스레드로부터 안전한 개체로 변환될 수 있습니다.  
  
 열거자만이 예외입니다. 응용 프로그램은 컬렉션 열거자에 대한 호출을 직렬화해야 합니다. 규칙은 다음과 같습니다. 컬렉션을 둘 이상의 스레드에서 동시에 열거할 수 있는 경우 열거자에서 트래버스하는 컬렉션의 루트 개체에 대한 열거자 메서드 동기화해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [.NET 정규식](../../../docs/standard/base-types/regular-expressions.md)
