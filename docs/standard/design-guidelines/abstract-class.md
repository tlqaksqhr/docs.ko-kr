---
title: "추상 클래스 디자인"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 739f86acd534549bc997dc7a939cf43a0c6fc3cb
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="abstract-class-design"></a>추상 클래스 디자인
**X 하지 않으면** 추상 형식에 public 또는 protected 내부 생성자를 정의 합니다.  
  
 생성자는 사용자가이 형식의 인스턴스를 만들 해야 하는 경우에 공용 이어야 합니다. 추상 형식의 인스턴스를 만들 수 없는 공용 생성자를 포함 하는 추상 형식 되므로 없습니다 제대로 디자인 되 고 사용자에 게 잘못 된 합니다.  
  
 **✓ 않습니다** 추상 클래스에는 protected 또는 내부 생성자를 정의 합니다.  
  
 Protected 생성자는이 더 일반적 및 단순히 작성 한 하위 유형을 자체 초기화 작업을 수행 하기 위해 기본 클래스를 허용 합니다.  
  
 클래스를 정의 하는 어셈블리에는 추상 클래스의 구체적 구현 제한 하는 내부 생성자를 사용할 수 있습니다.  
  
 **✓ 않습니다** 배송 된 각 추상 클래스에서 상속 하는 구체적인 형식이 하나 이상 제공 합니다.  
  
 이 사용이 하면 유효성을 검사 하는 추상 클래스의 디자인을 수행 합니다. 예를 들어 <xref:System.IO.FileStream?displayProperty=nameWithType> 는의 구현에서 <xref:System.IO.Stream?displayProperty=nameWithType> 추상 클래스입니다.  
  
 *일부 © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*  
  
 *피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*  
  
## <a name="see-also"></a>참고 항목  
 [형식 디자인 지침](../../../docs/standard/design-guidelines/type.md)  
 [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
