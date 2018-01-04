---
title: "클래스와 구조체 간의 선택"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- class library design guidelines [.NET Framework], classes
- structures [.NET Framework], vs. classes
- classes [.NET Framework], design guidelines
- type design guidelines, structures
- structures [.NET Framework], design guidelines
- classes [.NET Framework], vs. structures
- type design guidelines, classes
ms.assetid: f8b8ec9b-0ba7-4dea-aadf-a93395cd804f
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 68a3d2c7335ff15706925f9a7986164e6d9c0c36
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="choosing-between-class-and-struct"></a>클래스와 구조체 간의 선택
모든 프레임 워크 디자이너를 향하도록 기본 디자인 결정 사항 중 하나 (예: 참조 형식)는 클래스 또는 구조체 (값 형식)으로 형식을 디자인을 여부입니다. 참조 형식 및 값 형식의 동작의 차이점에 잘 알고는이 선택 하는 중요 합니다.  
  
 첫 번째 스택 참조 형식과 값 형식은 참조 형식은 힙에 할당 되 고 가비지 수집 인라인에 포함 된 형식 및 할당 취소 될 때 또는 값 형식 스택에 하거나 할당 된 것으로 간주 됩니다 간의 차이점 가 해제 또는 포함 하는 형식 가져옵니다 할당 취소 하는 경우. 따라서 할당 및 할당 취소 값 형식의 일반 할당 및 할당 해제 참조 형식의 보다 저렴에 있습니다.  
  
 그런 다음 배열 형식은 참조의 힙에 있는 참조 형식의 인스턴스에 대 한 정당한 참조 아웃 아웃오브 라인, 즉 배열 요소의 할당 합니다. 값 형식 배열 인라인으로 배열 요소 값 형식의 실제 인스턴스는 할당 됩니다. 따라서 할당 및 할당 취소를 값 형식 배열의 할당 및 할당 해제의 참조 형식 배열 보다 적은 비용이 듭니다. 또한 대부분의 경우 값 형식 배열 참조의 집약성이 훨씬 더 높아지므로 시.  
  
 다음 차이점 메모리 사용량 관련이 있습니다. 값 형식은 참조 형식 또는 구현 하는 인터페이스 중 하나를 캐스팅 하는 경우 boxed 가져옵니다. 러 워 unboxed 값 형식으로 다시 캐스팅 하는 경우. 상자 힙에 할당 되 고 가비지 수집, 너무 많이 boxing 및 unboxing 하는 개체는 힙, 가비지 수집기 및 궁극적으로 응용 프로그램의 성능에 부정적인 영향을 미칠 수 있습니다.  반대로 이러한 boxing 캐스팅 하는 참조 형식 발생 합니다.  
  
 다음으로, 참조 형식 할당이 값 형식 할당이 전체 값을 복사 하는 반면 해당 참조를 복사 합니다. 따라서 큰 참조 형식의 할당은 큰 값 형식의 할당 보다 저렴 합니다.  
  
 마지막으로, 참조 형식은 값 형식을 값으로 전달 되는 반면, 참조로 전달 됩니다. 참조 형식의 인스턴스로 변경에는 모든 참조는 인스턴스를 가리키는 적용 됩니다. 값 형식 인스턴스 값으로 전달 될 때 복사 됩니다. 값 형식의 인스턴스 변경 되 면 물론 바뀌지 않습니다 복사본 중 하나입니다. 복사본은 사용자가 명시적으로 생성 되지 않습니다 이지만 인수가 전달 되는 값이 반환 되도록 반환 때 암시적으로 생성, 때문에 값 형식을 변경할 수 있는 많은 사용자에 게 혼란을 줄 수 있습니다. 따라서 값 형식은 변경할 수 없어야 합니다.  
  
 경험상,으로 대부분의 프레임 워크의 형식에는 클래스 여야 합니다. 그러나, 경우가 있습니다는 값 형식의 특성 쉽게 구조체를 사용 하는 더 적합 합니다.  
  
 **✓ 고려** 형식 인스턴스의 작고 일반적으로 수명이 또는 일반적으로 다른 개체에 포함 된 경우 클래스 대신 구조체를 정의 합니다.  
  
 **하지 말고 X** 형식에는 다음과 같은 특성을 모두 하지 않으면 구조체를 정의 합니다.  
  
-   기본 형식 유사한 단일 값을 논리적으로 나타내는 (`int`, `double`등.).  
  
-   인스턴스 크기 16 바이트 미만인 있음  
  
-   변경할 수는 없습니다.  
  
-   자주 boxed 수 않아도 됩니다.  
  
 다른 모든 경우에 클래스 형식을 정의 해야 합니다.  
  
 *일부 © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*  
  
 *피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*  
  
## <a name="see-also"></a>참고 항목  
 [형식 디자인 지침](../../../docs/standard/design-guidelines/type.md)  
 [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
