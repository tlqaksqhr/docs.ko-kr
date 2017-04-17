---
title: "이벤트 및 콜백 | Microsoft Docs"
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
  - "확장 이벤트 [.NET Framework]"
  - "콜백이, 메서드 [.NET Framework]"
  - "콜백 메서드"
  - "콜백"
ms.assetid: 48b55c60-495f-4089-9396-97f9122bba7c
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# 이벤트 및 콜백
콜백에 대리자를 통해 사용자 코드를 다시 호출 하는 프레임 워크를 사용할 수 있는 확장성 지점입니다. 이러한 대리자는 대개는 메서드의 매개 변수를 통해 프레임 워크에 전달 됩니다.  
  
 이벤트는 특수 한 콜백 편리 하 고 일관성 있는 구문에 대해 지 원하는 대리자 \(이벤트 처리기\)를 제공 합니다. 또한 Visual Studio의 문 완성 및 디자이너에서 이벤트 기반 Api를 사용 하 여 도움말을 제공 합니다.[이벤트 디자인](../../../docs/standard/design-guidelines/event.md)를 참조하세요.  
  
 **✓ 고려** 콜백을 사용 하 여 프레임 워크에서 실행할 사용자 지정 코드를 제공 하는 사용자 수 있도록 합니다.  
  
 **✓ 고려** 이벤트를 사용 하 여 사용자가 개체 지향 디자인을 이해 하는 데 필요 없이 프레임 워크의 동작을 사용자 지정할 수 있도록 합니다.  
  
 **✓ 수행** 광범위 한 개발자에 게 친숙 문 완성 Visual Studio와 통합 되어 있기 때문에 일반 콜백 보다 이벤트를 선호 합니다.  
  
 **X 방지** 성능에 민감한 Api에서 콜백을 사용 합니다.  
  
 **✓ 수행** 새로운 `Func<...>`, `Action<...>`, 또는 `Expression<...>` 콜백을 Api를 정의할 때 사용자 지정 대리자 대신 형식입니다.  
  
 `Func<...>` 및 `Action<...>` 제네릭 대리자를 나타냅니다.`Expression<...>` 컴파일하고 이후에 수 없지만 런타임에 호출 될 수 있는 나타냅니다 함수 정의 serialize 및 원격 프로세스에 전달할 수 있습니다.  
  
 **✓ 수행** 사용 하 여 성능에 영향을 이해 하 고 측정 `Expression<...>`, 를 사용 하는 대신 `Func<...>` 및 `Action<...>` 대리자입니다.  
  
 `Expression<...>` 대부분의 경우 논리적으로 같습니다 유형은 `Func<...>` 및 `Action<...>` 대리자입니다. 주요 차이점은 대리자는 로컬 프로세스 시나리오;에서 사용할 수 식은 원격 프로세스 또는 컴퓨터의 식을 계산 하는 것이 도움이 문제와 유용 하기 위해 사용 됩니다.  
  
 **✓ 수행** 대리자를 호출 하 여 임의의 코드 실행은 이해 하 고 보안, 정확성 및 호환성 영향을 줄 수입니다.  
  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [확장성을 위한 디자인](../../../docs/standard/design-guidelines/designing-for-extensibility.md)   
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)