---
title: "같음 연산자"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- class library design guidelines [.NET Framework], Equals method
- class library design guidelines [.NET Framework], equality operator
- equality operator (==) [.NET Framework]
- Equals method
- == operator (equality) [.NET Framework]
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 55c0505f5a06dfc87897fa59e9d6083cbd63c8ee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="equality-operators"></a>같음 연산자
이 섹션 같음 연산자를 오버 로드에 대해 설명 하 고 가리키는 `operator==` 및 `operator!=` 같음 연산자입니다.  
  
 **X 하지 않으면** 같음 연산자 있고 다른 선언 중 하나를 오버 로드 합니다.  
  
 **✓ 않습니다** 되도록 <xref:System.Object.Equals%2A?displayProperty=nameWithType> 및 같음 연산자는 정확히 동일한 의미 체계와 비슷한 성능 특성입니다.  
  
 종종 즉 `Object.Equals` 같음 연산자를 오버 로드 될 때 재정의할 수 있어야 합니다.  
  
 **하지 말고 X** 같음 연산자에서 예외를 throw 합니다.  
  
 예를 들어 인수 중 하나가 throw 하는 대신 null 인 경우 false를 반환 `NullReferenceException`합니다.  
  
## <a name="equality-operators-on-value-types"></a>값 형식에 같음 연산자  
 **✓ 않습니다** 같음이 의미가 있을 경우에 값 형식에 같음 연산자를 오버 로드 합니다.  
  
 대부분의 프로그래밍 언어에는 기본 구현 된 `operator==` 값 형식에 대 한 합니다.  
  
## <a name="equality-operators-on-reference-types"></a>참조 형식에 같음 연산자  
 **하지 말고 X** 변경 가능한 참조 형식에 같음 연산자를 오버 로드 합니다.  
  
 여러 언어 참조 형식에 대 한 기본 제공 같음 연산자가 있는 경우. 기본 제공 연산자에는 일반적으로 참조 일치 구현 및 기본 동작 값을 다르게 변경 되 면 대부분의 개발자는 놀라운 사실 합니다.  
  
 이 문제는 불변성을 사용 하면 참조 일치와 값이 같은지 간의 차이 쉽게 변경할 수 없는 참조 형식에 대 한 완화 됩니다.  
  
 **하지 말고 X** 참조 일치 하는 것 보다 크게 느려지지 구현 되는 경우에 참조 형식에 같음 연산자를 오버 로드 합니다.  
  
 *일부 © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*  
  
 *피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*  
  
## <a name="see-also"></a>참고 항목  
 [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)  
 [사용 지침](../../../docs/standard/design-guidelines/usage-guidelines.md)
