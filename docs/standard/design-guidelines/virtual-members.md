---
title: 가상 멤버
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- overridable members
- virtual members
- members [.NET Framework], virtual
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fa4227fc4476b86f07216650b22fccc25af7dd98
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="virtual-members"></a>가상 멤버
가상 멤버는 하위 클래스의 동작을 변경 하는 따라서 재정의할 수 있습니다. 콜백을 제공 하 고 확장성 측면에서 매우 유사 하지만 실행 성능 및 메모리 사용량 측면에서 더 좋은 것은 있습니다. 또한 가상 멤버 만들어야 하는 특별 한 종류의 기존 유형 (특수화) 시나리오에서 더 자연 스러운 느낍니다.  
  
 가상 멤버 콜백 및 이벤트 보다 성능이 나을 수 있지만 비가상 메서드 보다 더 잘 수행 하지 않습니다.  
  
 가상 멤버의 가지 주요 단점은 가상 멤버의 동작은 컴파일 타임에만 수정할 수 있습니다. 런타임 시 콜백의 동작을 수정할 수 있습니다.  
  
 콜백을 (등을 할당 콜백을 보다), 같은 가상 멤버는 디자인, 테스트 및 가상 멤버를 호출할 때 예기치 않은 방법으로 재정의할 수 있습니다 및 임의 코드를 실행할 수 있으므로 유지 관리 비용이 많이 듭니다. 또한 훨씬 더 많은 노력이 명확 하 게 디자인 하 고 문서화 하는 더 높은 가상 멤버의 계약을 정의 하려면 일반적으로 필요 합니다.  
  
 **X 하지 않으면** 그러려면 이유가 있고 디자인, 테스트 및 가상 멤버를 유지 관리와 관련 된 모든 비용에 대해 알고에 가상 멤버를 확인 합니다.  
  
 가상 멤버는 덜 관대 호환성을 중단 하지 않고에 적용 될 변경 내용을 기준으로 합니다. 또한 가상 멤버에 대 한 호출을 인라인 없는 하기 때문에 대부분 비가상 멤버 보다 느린있지 않습니다.  
  
 **✓ 고려** 확장성 반드시 필요한 것만을 제한 합니다.  
  
 **✓ 않습니다** 가상 멤버에 대 한 공용 액세스 가능성을 통해 보호 된 액세스 가능성을 선호 합니다. 공용 멤버 확장성을 제공 해야 (필요한 경우) 보호 된 가상 멤버를 호출 하 여 합니다.  
  
 클래스의 public 멤버는 해당 클래스의 직접 소비자에 대 한 올바른 기능 집합을 제공 해야 합니다. 가상 멤버 하위 클래스에서 재정의 될 수 있도록 되어 및 보호 된 액세스 가능성은 모든 가상 확장성 지점을 사용할 수는 있는 범위를 지정 하는 좋은 방법입니다.  
  
 *Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*  
  
 *피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*  
  
## <a name="see-also"></a>참고 항목  
 [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)  
 [확장성을 위한 디자인](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
