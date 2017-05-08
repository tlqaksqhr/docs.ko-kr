---
title: "가상 멤버 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "재정의 가능한 멤버"
  - "가상 멤버"
  - "멤버 [.NET Framework] 가상"
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# 가상 멤버
가상 멤버는 서브 클래스의 동작을 변경 하므로 재정의할 수 있습니다. 콜백을 제공 하 고 확장성 측면에서 매우 유사 하지만 실행 성능 및 메모리 사용 측면에서 더 나은 합니다. 또한, 가상 멤버 만들어야 하는 특별 한 종류의 기존 유형 \(특수화\) 시나리오에서 더 자연 스러운 생각 합니다.  
  
 가상 멤버 콜백 및 이벤트 보다 성능이 우수 하지만 비가상 방법 보다 더 잘 수행 하지 않습니다.  
  
 가상 멤버의 가장 큰 단점은 것 가상 멤버의 동작의 컴파일 타임에만 수정할 수 있습니다. 런타임 시 콜백의 동작을 수정할 수 있습니다.  
  
 콜백을 \(등을 할당 콜백을 보다\), 등의 가상 멤버는 디자인, 테스트 및 가상 멤버를 호출할 때 예기치 않은 방법으로 재정의 될 수 임의 코드를 실행할 수 있으므로 유지 관리 비용이 많이 듭니다. 또한 훨씬 더 많은 노력이 명확 하 게 정의 가상 멤버의 계약을 설계 하 고 문서화 하는 비용은 더 높은 되므로 일반적으로 필요 합니다.  
  
 **X 하지 않으려면** 할 이유가 있고 디자인, 테스트 및 가상 멤버를 유지 관리와 관련 된 모든 비용에 대해 알고에 가상 멤버를 확인 합니다.  
  
 가상 멤버는 덜 관대 호환성을 설정할 수 있는 변경 내용을 기준으로 합니다. 또한 이러한 보다 속도가 느립니다 가상이 아닌 멤버, 가상 멤버에 대 한 호출 수 인라인 없기 때문에 대개입니다.  
  
 **✓ 고려** 확장성 반드시 필요한 것만을 제한 합니다.  
  
 **✓ 수행** 가상 멤버에 대 한 공용 액세스 가능성을 통해 보호 된 액세스 가능성을 선호 합니다. 공용 멤버 확장성을 제공 해야 \(필요한 경우\) 보호 된 가상 멤버를 호출 하 여 합니다.  
  
 클래스의 public 멤버는 해당 클래스의 직접 소비자에 대 한 올바른 기능 집합을 제공 해야 합니다. 가상 멤버 하위 클래스에서 재정의 될 수 있도록 되어 및 보호 된 액세스 가능성은 모든 가상 확장성 지점을 사용할 수 있는 범위를 지정 하는 데 유용 합니다.  
  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)   
 [확장성을 위한 디자인](../../../docs/standard/design-guidelines/designing-for-extensibility.md)