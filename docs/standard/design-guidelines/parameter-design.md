---
title: 매개 변수 디자인
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines [.NET Framework], parameters
- members [.NET Framework], parameters
- names [.NET Framework], parameters
- parameters, design guidelines
- reserved parameters
ms.assetid: 3f33bf46-4a7b-43b3-bb78-1ffebe0dcfa6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e39b38fd72f9f3b9ce76aa6f7e96e44841daabb9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33578276"
---
# <a name="parameter-design"></a>매개 변수 디자인
이 섹션 인수 검사에 대 한 지침과 섹션을 추가 하는 매개 변수 디자인에는 광범위 한 지침을 제공 합니다. 에 설명 된 지침을 참조 해야 또한 [매개 변수 이름 지정](../../../docs/standard/design-guidelines/naming-parameters.md)합니다.  
  
 **✓ 않습니다** 멤버에 필요한 기능을 제공 하는 최소 파생 된 매개 변수 형식을 사용 합니다.  
  
 예를 들어 컬렉션을 열거 하 고 각 항목을 콘솔에 출력 하는 메서드를 디자인 하려면 한다고 가정 합니다. 이러한 메서드를 수행 해야 <xref:System.Collections.IEnumerable> 매개 변수로 하지 <xref:System.Collections.ArrayList> 또는 <xref:System.Collections.IList>, 예를 들어 있습니다.  
  
 **X 하지 않으면** 예약 된 매개 변수를 사용 합니다.  
  
 멤버에 대 한 더 많은 입력 향후 버전에서 필요한 경우 새 오버 로드를 추가할 수 있습니다.  
  
 **X 하지 마십시오** 가 공개적으로 포인터, 포인터, 배열 또는 다차원 배열을 매개 변수로 사용 하는 메서드를 노출 합니다.  
  
 포인터 및 다차원 배열에는 상대적으로 올바르게 사용 하기 어려운 합니다. 거의 모든 경우에 Api는 이러한 형식을 매개 변수를 받지 않도록 다시 디자인 수 있습니다.  
  
 **✓ 않습니다** 모든 배치 `out` 다음 값으로의 모든 매개 변수 및 `ref` 매개 변수 (매개 변수 배열 제외) 매개 변수 오버 로드 간의 순서 지정에 불일치가 발생 하는 경우에 (참조 [멤버 오버 로드](../../../docs/standard/design-guidelines/member-overloading.md)).  
  
 `out` 추가 반환 값으로 매개 변수를 볼 수 있습니다 및 메서드 시그니처를 더욱 쉽게 이해 함께 그룹화 하는 것입니다.  
  
 **✓ 않습니다** 멤버를 재정의 하는 경우 매개 변수를 명명 또는 인터페이스 멤버 구현 일관 되 게 합니다.  
  
 이 메서드 간의 관계를 더 잘 통신합니다.  
  
### <a name="choosing-between-enum-and-boolean-parameters"></a>열거형 및 부울 매개 변수 중에서 선택  
 **✓ 않습니다** 구성원 부울 매개 변수 두 개 이상의 미칠 경우 열거형을 사용 합니다.  
  
 **X 하지 않으면** 확실히 될 수 없으므로 두 개 이상의 값에 대 한 필요 하지 않는 한 부울을 사용 합니다.  
  
 열거형 값을이 향후 추가 위한 몇 가지 공간 수 있지만에서 설명 하는 열거형에 값을 추가 하는 모든 의미를 알고 있어야 [Enum 디자인](../../../docs/standard/design-guidelines/enum.md)합니다.  
  
 **✓ 고려** 부울 값이 실제로 두 가지 상태는 부울 속성을 초기화 하는 생성자 매개 변수를 사용 하 여 합니다.  
  
### <a name="validating-arguments"></a>인수 유효성 검사  
 **✓ 않습니다** public, protected 또는 명시적으로 구현 된 멤버에 전달 되는 인수의 유효성을 검사 합니다. Throw <xref:System.ArgumentException?displayProperty=nameWithType>, 또는 해당 서브 클래스 중 하나를 유효성 검사에 실패 합니다.  
  
 실제 유효성 검사 반드시 public 또는 protected 멤버 자체에서 발생 하는 참고 사항 일부 전용 또는 내부 루틴에서 하위 수준에서 발생할 수 있습니다. 주요 점은 최종 사용자에 게 노출 되는 전체 표면적 인수를 검사 하는 것입니다.  
  
 **✓ 않습니다** throw <xref:System.ArgumentNullException> 에 null 인수가 전달 되 고 멤버가 null 인수를 지원 하지 않는 경우.  
  
 **✓ 않습니다** enum 매개 변수 유효성 검사 합니다.  
  
 Enum 인수가 열거형으로 정의 된 범위에 있을 것을 가정 하지 마십시오. CLR은 열거형에 값이 정의 되지 않은 경우에 enum 값에 임의의 정수 값을 캐스팅 수 있습니다.  
  
 **X 하지 않으면** 사용 <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> 열거형 범위 검사 합니다.  
  
 **✓ 않습니다** 유효성을 검사 한 후 인수가 변경할 수 있는 변경 수에 유의 합니다.  
  
 멤버가 보안에 중요 한 경우에 복사 하 고 다음 유효성 검사 및 인수를 처리 하는 것이 좋습니다 됩니다.  
  
### <a name="parameter-passing"></a>매개 변수 전달  
 프레임 워크 디자이너의 관점에서 세 가지 기본 그룹이 있습니다 매개 변수: 값으로 매개 변수를 `ref` 매개 변수 및 `out` 매개 변수입니다.  
  
 인수에 값으로 매개 변수를 통해 전달 될 때는 멤버에 전달 된 실제 인수의 복사본을 받습니다. 인수가 값 형식, 인수의 복사본이 스택의 전환 됩니다. 인수가 참조 형식이 면 참조의 복사본이 스택의 전환 됩니다. 가장 인기 있는 CLR과 같은 언어를 C#, VB.NET 및 c + +에서는 기본적으로 매개 변수 값으로 전달 합니다.  
  
 인수를 통해 전달 되 면는 `ref` 매개 변수를 멤버에 전달 되는 실제 인수에 대 한 참조를 받습니다. 인수가 값 형식, 인수에 대 한 참조를 스택에 저장 됩니다. 인수가 참조 형식이 면 스택에 대 한 참조에 대 한 참조가 저장 됩니다. `Ref` 매개 변수 멤버를 호출자에 의해 전달 된 인수를 수정 하려면 데 사용할 수 있습니다.  
  
 `Out` 매개 변수는 비슷합니다 `ref` 작은 몇 가지 차이점이 있지만 매개 변수입니다. 매개 변수가 처음 것으로 간주 되어 할당 되지 않은 일부 값을 할당 하기 전에 멤버 본문에서 읽을 수 없습니다. 또한는 매개 변수는 멤버 반환 되기 전에 일부 값이 할당 되어야 합니다.  
  
 **하지 말고 X** 를 사용 하 여 `out` 또는 `ref` 매개 변수입니다.  
  
 사용 하 여 `out` 또는 `ref` 매개 변수는 포인터를 값 형식과 참조 형식, 어떻게 다른 지를 이해 하 고 반환 값이 여러 개인 메서드를 처리 해야 합니다. 또한 간의 차이 `out` 및 `ref` 매개 변수는 잘 알려져 있지 않습니다. 일반 사용자를 대상에 대 한 디자인 하는 프레임 워크 설계자와 작업에 능숙 할 사용자가 기대 하지 `out` 또는 `ref` 매개 변수입니다.  
  
 **X 하지 않으면** 참조 형식을 참조로 전달 합니다.  
  
 참조를 바꿔 사용할 수 있는 메서드와 같은 규칙에 제한 된 몇 가지 예외 사항이 있습니다.  
  
### <a name="members-with-variable-number-of-parameters"></a>매개 변수 개수가 가변적인 멤버  
 가변 개수의 인수를 사용할 수 있는 멤버 배열 매개 변수에 제공 하 여 표현 됩니다. 예를 들어 <xref:System.String> 다음 메서드를 제공 합니다.  
  
```  
public class String {  
    public static string Format(string format, object[] parameters);  
}  
```  
  
 사용자를 호출할 수는 <xref:System.String.Format%2A?displayProperty=nameWithType> 다음과 같이 메서드:  
  
 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`  
  
 C# params 키워드는 배열 매개 변수를 추가 소위 params 배열 매개 변수를 매개 변수를 변경 하 고 임시 배열을 만드는 바로 가기의 제공 합니다.  
  
```  
public class String {  
    public static string Format(string format, params object[] parameters);  
}  
```  
  
 이 메서드를 호출 하 여 배열 요소를 인수 목록에 직접 전달 하 여 사용자 수 있습니다.  
  
 `String.Format("File {0} not found in {1}",filename,directory);`  
  
 Params 키워드 매개 변수 목록의 마지막 매개 변수에 추가할 수 있는지 확인 합니다.  
  
 **✓ 고려** 는 적은 수의 요소 배열을 전달 하는 최종 사용자가 예상 되는 경우에 params 키워드 배열 매개 변수를 추가 합니다. 예상 하지만 다양 한 요소 전달할 공통 시나리오, 사용자가 이러한 요소를 인라인으로 누르고, 통과 하지 못할는 및에 params 키워드 이므로 필요 하지 않습니다.  
  
 **하지 말고 X** 호출자에 게는 거의 항상 이미 입력 배열의 경우 매개 변수 배열을 사용 하 여 합니다.  
  
 예를 들어 개별 바이트를 전달 하 여 바이트 배열 매개 변수가 있는 멤버는 호출할 수 거의 없습니다. 이런 이유로.NET Framework의 바이트 배열 매개 변수는에 params 키워드를 사용 하지 마십시오.  
  
 **X 하지 않으면** 배열 멤버 params 배열 매개 변수를 사용 하 여 수정 된 경우 매개 변수 배열을 사용 합니다.  
  
 대부분의 컴파일러 호출 사이트에서 임시 배열에는 멤버에 대 한 인수를 설정 사실 때문에 배열 임시 개체 일 수 있습니다 및 배열에 대 한 수정을 손실 됩니다.  
  
 **✓ 고려** 단순 오버 로드에서에 params 키워드를 사용 하 여 경우에 더 복잡 한 오버 로드를 사용 하지 못했습니다.  
  
 보다 잘 하는 경우 사용자가 중요 하 게 생각 모든 오버 로드에는 없 었 하는 경우에 하나의 오버 로드에는 배열이 필요 합니다.  
  
 **✓ 않습니다** params 키워드를 사용할 수 있도록 적절 한 매개 변수를 하려고 합니다.  
  
 **✓ 고려** 적은 수의 성능에 민감한 매우 Api에는 인수를 사용 하 여 호출에 대 한 특별 한 오버 로드와 코드 경로 제공 합니다.  
  
 이렇게 하면 적은 수의 인수를 사용 하는 API를 호출 하는 경우 배열 개체를 만들지 않도록 합니다. 배열 매개 변수의 단 수 형태를 가져오고 숫자 접미사를 추가 하 여 매개 변수 이름이 형성 합니다.  
  
 특별 한 경우 전체 코드 경로 배열을 만듭니다 뿐 아니라 한 보다 일반적인 메서드를 호출 하려는 경우에 다음이 수행만 해야 합니다.  
  
 **✓ 않습니다** 유의 매개 변수 배열 인수는 null을 전달할 수 있습니다.  
  
 배열의 처리 하기 전에 null 임을 확인 해야 합니다.  
  
 **X 하지 마십시오** 사용는 `varargs` 메서드, 줄임표 라고도 합니다.  
  
 C + +와 같은 일부 CLR 언어 라는 변수 매개 변수 목록을 전달 하기 위한 대체 규칙 지원 `varargs` 메서드. CLS 규격이 아니므로 프레임 워크에서의 규칙은 사용할 수 없습니다.  
  
### <a name="pointer-parameters"></a>포인터 매개 변수  
 일반적으로 포인터 되지 잘 설계 된 관리 되는 코드 프레임 워크의 공개 노출 영역에 나타납니다. 대부분의 경우 포인터를 캡슐화 합니다. 그러나 경우에 따라 포인터는 상호 운용성을 위해 필요 하 고 적절 한는 포인터를 사용 하 여 이러한 경우에 합니다.  
  
 **✓ 않습니다** 포인터 CLS 규격이 아닙니다. 때문에 포인터 인수를 사용 하는 멤버에 대 한 대체 방법을 제공 합니다.  
  
 **하지 말고 X** 과도 한 인수 포인터 인수의 검사를 수행 합니다.  
  
 **✓ 않습니다** 포인터로 멤버를 디자인 하는 경우 일반 포인터와 관련 된 규칙을 따릅니다.  
  
 예를 들어 동일한 결과 얻기 위해 단순한 포인터 산술을 사용할 수 있으므로 시작 인덱스를 전달할 필요가 없습니다 있습니다.  
  
 *Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*  
  
 *피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*  
  
## <a name="see-also"></a>참고 항목  
 [멤버 디자인 지침](../../../docs/standard/design-guidelines/member.md)  
 [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
