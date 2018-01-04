---
title: "특성 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 89e892a379c7540cf67488471ae5281a4c4b86f4
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="attributes"></a>특성
<xref:System.Attribute?displayProperty=nameWithType>기본 클래스 사용자 지정 특성을 정의 하는 데 사용 합니다.  
  
 특성은 어셈블리, 형식, 멤버 및 매개 변수 같은 프로그래밍 요소에 추가할 수 있는 주석입니다. 이러한 어셈블리의 메타 데이터에 저장 되 고 리플렉션 Api를 사용 하 여 런타임에 액세스할 수 있습니다. 예를 들어 프레임 워크 정의 <xref:System.ObsoleteAttribute>, 하는 형식 또는 멤버는 형식 또는 멤버가 사용 되지 않습니다 나타냅니다에 적용할 수 있습니다.  
  
 특성에는 특성과 관련 된 추가 데이터를 전송 하는 하나 이상의 속성이 있을 수 있습니다. 예를 들어 `ObsoleteAttribute` 에 릴리스 하는 방법에 대 한 추가 정보를 수행할 수 사용 되지 않는 API를 바꾸는 새 Api의 설명 및 형식 또는 멤버가 더 이상 사용 되지 (를) 가져왔습니다.  
  
 특성이 적용 될 때 특성의 일부 속성을 지정 해야 합니다. 이 라고 필수 속성 또는 필수 인수를 위치 생성자 매개 변수로 나타내므로 합니다. 예를 들어는 <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> 의 속성은 <xref:System.Diagnostics.ConditionalAttribute> 필수 속성입니다.  
  
 반드시 특성이 적용 될 때 지정 해야 하는 속성은 선택적 속성 (또는 선택적 인수) 라고 합니다. 설정 가능한 속성으로 표시 됩니다. 컴파일러는 특성이 적용 될 때 이러한 속성을 설정 하는 특수 한 구문을 제공 합니다. 예를 들어는 <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> 속성은 선택적 인수를 나타냅니다.  
  
 **✓ 않습니다** "특성" 접미사를 사용 하 여 사용자 지정 특성 클래스 이름  
  
 **✓ 않습니다** 적용 된 <xref:System.AttributeUsageAttribute> 사용자 지정 특성에 있습니다.  
  
 **✓ 않습니다** 옵션 인수에 대해 설정 가능한 속성을 제공 합니다.  
  
 **✓ 않습니다** 필수 인수에 대 한 가져오기 전용 속성을 제공 합니다.  
  
 **✓ 않습니다** 필수 인수에 해당 하는 속성을 초기화할 생성자 매개 변수를 제공 합니다. 각 매개 변수에 해당 하는 속성으로 (있지만와 서로 다른 대/소문자 구분) 동일한 이름은 해야 합니다.  
  
 **하지 말고 X** 에 해당 하는 선택적 인수 속성을 초기화할 생성자 매개 변수를 제공 합니다.  
  
 즉, 생성자 및 setter를 모두 설정할 수 있는 속성이 포함 되지 않습니다. 이 지침에서는 인수는 선택 사항이 며 더 필요 하 고 동일한 작업을 수행 하는 두 가지는 피할 수 있는 명확히 명시 합니다.  
  
 **하지 말고 X** 사용자 지정 특성 생성자 오버 로드 합니다.  
  
 인수는 필수 및 선택적 사용자에 게 통신 명확 하 게 생성자가 하나만 필요 합니다.  
  
 **✓ 않습니다** 사용자 지정 특성 클래스를 가능 하면 항상 봉인 됩니다. 이렇게 하면 특성에 대 한 조회가 속도가 빨라집니다.  
  
 *일부 © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*  
  
 *피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*  
  
## <a name="see-also"></a>참고 항목  
 [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)  
 [사용 지침](../../../docs/standard/design-guidelines/usage-guidelines.md)
