---
title: "열거형 디자인"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- type design guidelines, enumerations
- simple enumerations
- enumerations [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], enumerations
- flags enumerations
ms.assetid: dd53c952-9d9a-4736-86ff-9540e815d545
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3ee73e8677ca3fd48f4bb3c94bd4e15c49a564c7
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="enum-design"></a>열거형 디자인
열거형은 특수 한 유형의 값 형식입니다. 열거형의 두 종류가: 단순 열거형 및 플래그 열거형입니다.  
  
 단순 열거형 선택 항목의 닫힌된 작은 집합을 나타냅니다. 단순 열거형의 일반적인 예에는 한 색 집합입니다.  
  
 플래그 열거형 enum 값에 비트 작업을 지원 하도록 설계 되었습니다. 플래그 열거형의 일반적인 예에는 옵션의 목록입니다.  
  
 **✓ 않습니다** 열거형을 사용 하 여 강력한 형식의 매개 변수, 속성 및 값 집합을 나타내는 값을 반환 합니다.  
  
 **✓ 않습니다** 정적 상수 대신 열거형을 사용 합니다.  
  
 **X 하지 않으면** 집합 (예: 운영 체제 버전, 친구, 등의 이름입니다.)에 대 한 열거형을 사용 합니다.  
  
 **X 하지 않으면** 나중에 사용할 수는 예약 된 열거형 값을 제공 합니다.  
  
 항상 단순히 기존 열거형에 이후 단계에서 값을 추가할 수 있습니다. 참조 [열거형에 값 추가](#add_value) 에 대 한 자세한 내용은 열거형에 값을 추가 합니다. 예약된 값만 실제 값 집합이 오염 하며 하 사용자 오류가 발생할 수입니다.  
  
 **하지 말고 X** 열거형 값을 하나만로 공개적으로 노출 합니다.  
  
 C Api의 다음 버전의 확장을 위한 일반적인 방법은 메서드 시그니처를 예약 된 매개 변수를 추가 하는 것입니다. 이러한 예약 된 매개 변수 이며 기본값은 단일 열거형으로 표현할 수 있습니다. 관리 되는 Api에서 수행 되어야이 합니다. 메서드 오버 로드 매개 변수는 이후 릴리스에서 추가할 수 있습니다.  
  
 **X 하지 않으면** 열거형에 센티널 값을 포함 합니다.  
  
 프레임 워크 개발자가 경우에 따라 변수가 이기는 하지만 센티널 값은 프레임 워크의 사용자에 게 혼동입니다. 열거형에 의해 표현 된 집합에서 값 중 하나 되 고 아닌 열거형의 상태를 추적 하는 데 사용 됩니다.  
  
 **✓ 않습니다** 단순 열거형에는 0 값을 제공 합니다.  
  
 다음과 같이 "None"입니다. 값을 호출 하는 것이 좋습니다. 이러한 값이 특정 열거형에 적합 하지 않은 경우 열거형에 대 한 가장 일반적인 기본값 0의 내부 값을 할당 해야 합니다.  
  
 **✓ 고려** 를 사용 하 여 <xref:System.Int32> (대부분의 프로그래밍 언어의 기본값) 열거형의 내부 형식으로 다음 중 하나에 해당 하지 않는 한 합니다.  
  
-   열거형 플래그 열거형은 있으며 32 개 이상의 플래그가 하거나 나중에 둘 수 있습니다.  
  
-   기본 형식이 다를 수 해야 <xref:System.Int32> 다른 크기 열거형 비관리 코드와 쉽게 상호 운용성에 대 한 합니다.  
  
-   더 작은 기본 형식이 하면 공간이 크게 절약으로 반환 됩니다. 제어 흐름에 대 한 인수로 서 주로 사용할 열거형을 예상할 경우 크기 거의 차이가 있습니다. 한 크기 절감 효과가 매우 길어질 수 있습니다 하는 경우:  
  
    -   매우 자주 인스턴스화된 구조체 또는 클래스의 필드로 사용할 enum을 예상 합니다.  
  
    -   원하는 큰 배열 또는 열거형 인스턴스의 컬렉션을 만들 수 있습니다.  
  
    -   Serialize 할 열거형의 인스턴스 수가 많은 예상 합니다.  
  
 메모리 사용량에 대 한 관리 되는 개체는 수 항상 `DWORD`-정렬 되므로 여러 열거형 또는 다른 작은 구조를 항상 때문에 총 인스턴스 크기 차이 확인 하기 위해 포함 된 더 작은 열거형을 압축 하는 인스턴스에 효과적으로 필요 최대 반올림 하 고는 `DWORD`합니다.  
  
 **✓ 않습니다** 단 수 명사 또는 명사구 단순 열거형 및 플래그 열거형 복수 명사 또는 명사구로 이름을 지정 합니다.  
  
 **X 하지 않으면** 확장 <xref:System.Enum?displayProperty=nameWithType> 직접 합니다.  
  
 <xref:System.Enum?displayProperty=nameWithType>특별 한 형식 CLR에서 만드는 데 사용자 정의 열거형. 대부분의 프로그래밍 언어에이 기능에 액세스할 수 있는 프로그래밍 요소를 제공 합니다. 예를 들어 C#에서 `enum` 키워드를 사용 하는 열거형을 정의 합니다.  
  
<a name="design"></a>   
### <a name="designing-flag-enums"></a>디자인 플래그 열거형  
 **✓ 않습니다** 적용 된 <xref:System.FlagsAttribute?displayProperty=nameWithType> 플래그 열거형에 있습니다. 이 특성을 단순 열거형에 적용 되지 않습니다.  
  
 **✓ 않습니다** 수 자유롭게 결합 비트 OR 연산을 사용 하 여 플래그 열거형 값에 2의 제곱을 사용 합니다.  
  
 **✓ 고려** 플래그의 조합을 사용 되는 일반적으로 특수 한 열거 값을 제공 합니다.  
  
 비트 연산은 고급 개념 및 간단한 작업에 필요한 수 없습니다. <xref:System.IO.FileAccess.ReadWrite>이러한 특수 값의 예시입니다.  
  
 **하지 말고 X** 만들기 플래그 열거형 값의 조합이 올바르지 않습니다.  
  
 **하지 말고 X** 값 "플래그를 모두 선택 취소"를 나타내는 적절 하 게 다음 지침에서 설명 했 듯이 라는 하지 않는 한 enum 값이 0 인 플래그를 사용 하 여 합니다.  
  
 **✓ 않습니다** 0 플래그 열거형의 값 이름을 `None`합니다. 플래그 열거형에 대 한 값 해야 항상 의미가 "플래그를 모두 선택 취소 합니다."  
  
<a name="add_value"></a>   
### <a name="adding-value-to-enums"></a>열거형에 값 추가  
 매우 일반적 검색 후 이미 제공 된 열거형에 값을 추가 해야 합니다. 잠재적인 응용 프로그램 호환성 문제는 기존 API에서 새로 추가 된 값이 반환 하는 경우 되므로 잘못 작성 된 응용 프로그램의 새 값을 제대로 처리 하지 수도 있습니다.  
  
 **✓ 고려** 작은 호환성 위험 불구 하 고 열거형에 값을 추가 합니다.  
  
 열거형에 대 한 추가 인해 발생 하는 응용 프로그램 호환성 문제에 대 한 실제 데이터를 설정한 경우에 새과 이전 값을 반환 하는 새로운 API를 추가 하는 것이 좋습니다. 하 고 이전 값만 반환 합니다. 계속 하는 이전 API에 사용할 수 없게 합니다. 이렇게 하면 기존 응용 프로그램 호환성을 유지 합니다.  
  
 *일부 © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*  
  
 *피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*  
  
## <a name="see-also"></a>참고 항목  
 [형식 디자인 지침](../../../docs/standard/design-guidelines/type.md)  
 [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
