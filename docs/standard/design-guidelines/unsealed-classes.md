---
title: 봉인되지 않은 클래스
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 672d36c6b888ee9a89a76d5d417a7a7e92dd8f36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="unsealed-classes"></a>봉인되지 않은 클래스
From, 봉인된 클래스는 상속 될 수 없습니다 및 확장성을 방지 합니다. 반면, 클래스에서 상속 되는 봉인 되지 않은 클래스 라고 합니다.  
  
 **✓ 고려** 저렴 한 제공할 수 있는 좋은 방법 아직 훨씬 좋습니다 프레임 워크를 확장 하는 대로 가상 또는 보호 된 멤버를 추가 없이 봉인 되지 않은 클래스를 사용 하 여 합니다.  
  
 개발자는 종종 편의 멤버 예: 사용자 지정 생성자, 새로운 메서드 또는 메서드 오버 로드를 추가 하기 위해 봉인 되지 않은 클래스에서 상속 하려고 합니다. 예를 들어 `System.Messaging.MessageQueue` 봉인 되지 않으며 사용자가 큐를 만드는 사용자 지정 특정 큐 경로에 해당 기본 하거나 특정 시나리오에 대 한 API를 단순화 하는 사용자 지정 메서드를 추가할 수 있습니다.  
  
 클래스는 대부분의 프로그래밍 언어에서 기본적으로 봉인 되지 않은 및 프레임 워크에서 대부분의 클래스에 대 한 권장 되는 기본 이기도 합니다. 봉인 되지 않은 형식에서 제공 하는 확장성 프레임 워크 사용자가 훨씬 지 환영 합니다 봉인 되지 않은 형식과 관련 된 테스트 상대적으로 낮은 비용으로 인해 수 있도록 매우 저렴 한 됩니다.  
  
 *Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*  
  
 *피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*  
  
## <a name="see-also"></a>참고 항목  
 [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)  
 [확장성을 위한 디자인](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [봉인](../../../docs/standard/design-guidelines/sealing.md)
