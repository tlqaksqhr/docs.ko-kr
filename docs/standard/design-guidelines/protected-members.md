---
title: 보호된 멤버
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d4d334d9809f374442e19807d3b249a17a1d9df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571087"
---
# <a name="protected-members"></a>보호된 멤버
단독으로 보호 된 멤버는 확장성을 제공 하지 않습니다 하지만 더 강력한 서브클래싱을 통해 확장성을 내릴 수 있습니다. 기본 공용 인터페이스를 불필요 하 게 하므로 복잡해 집니다 하지 않고 고급 사용자 지정 옵션을 표시 데 사용할 수 있습니다.  
  
 프레임 워크 디자이너에 주의를 기울여야 보호 된 멤버 이름이 "보호" 보안에 대해 잘못 된 지정할 수 없기 때문에 필요 합니다. 모든 사용자는 하위 클래스는 봉인 되지 않은 클래스 및 멤버에 보호 된 액세스를 하 하 고 공용 멤버에 사용 되는 코딩 관례 보호 된 멤버에 적용 되는 동일한 하므로 합니다.  
  
 **✓ CONSIDER** 를 사용 하 여 고급 사용자 지정에 대 한 멤버를 보호 합니다.  
  
 **✓ DO** 보안, 설명서 및 호환성 분석용으로 public으로 봉인 되지 않은 클래스의 보호 된 멤버를 처리 합니다.  
  
 누구 든 지 클래스에서 상속 하 고 보호 된 멤버에 액세스할 수 있습니다.  
  
 *Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*  
  
 *피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*  
  
## <a name="see-also"></a>참고 항목  
 [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)  
 [확장성을 위한 디자인](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
