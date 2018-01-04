---
title: "확장성을 위한 디자인"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: f21e9239199ecd36432ed8f14adb896f1799506b
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="designing-for-extensibility"></a>확장성을 위한 디자인
프레임 워크를 디자인할 때의 중요 한 측면 있는지 확인 하는 프레임 워크의 확장성을 신중 하 게 고려 했습니다. 이렇게 하려면 다양 한 확장성 메커니즘와 관련 된 이점과 비용을 이해 해야 합니다. 이 장에서 확장성 메커니즘 중 어떤 것인지-서브클래싱, 이벤트, 가상 멤버, 콜백 및 등-프레임 워크의 요구 사항을 충족할 수 있습니다.  
  
 프레임 워크의 확장성을 허용 하는 방법은 여러 가지가 있습니다. 까지의 덜 강력 하지만 보다 저렴 한 비용 저렴 하지만 매우 강력 합니다. 모든 지정된 확장성 요구 사항에 대 한 요구 사항을 충족 하는 가장 비용이 많이 드는 확장성 메커니즘을 선택 해야 합니다. 일반적으로 보다 높은 확장성은 나중에 추가할 수는 있지만 사용할 수 있으며 되지 자리를 비울 주요 변경 없이 염두에서에 둬야 합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [봉인되지 않은 클래스](../../../docs/standard/design-guidelines/unsealed-classes.md)  
 [보호된 멤버](../../../docs/standard/design-guidelines/protected-members.md)  
 [이벤트 및 콜백](../../../docs/standard/design-guidelines/events-and-callbacks.md)  
 [가상 멤버](../../../docs/standard/design-guidelines/virtual-members.md)  
 [추상화(추상 형식 및 인터페이스)](../../../docs/standard/design-guidelines/abstractions-abstract-types-and-interfaces.md)  
 [추상화 구현을 위한 기본 클래스](../../../docs/standard/design-guidelines/base-classes-for-implementing-abstractions.md)  
 [봉인](../../../docs/standard/design-guidelines/sealing.md)  
 *일부 © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*  
  
 *피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*  
  
## <a name="see-also"></a>참고 항목  
 [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
