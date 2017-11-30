---
title: "구조체와 클래스(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- classes [Visual Basic], vs. structures
- structures [Visual Basic]
- classes [Visual Basic]
- structures [Visual Basic], compared to classes
- structures [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: a221e74a-ffcf-4bdc-a0f6-a088a9bf26cc
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 08e31481feac7a6184c6b29269d193c749f440ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="structures-and-classes-visual-basic"></a>구조체와 클래스(Visual Basic)
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]구조체와 클래스에 대 한 구문의 통합 합니다. 그러나 구조체와 클래스의 중요 한 차이점이 있습니다.  
  
 클래스에는 참조 형식이 될 수 있는 이점이-대 한 참조를 전달 하는 것이 모든 데이터와 함께 구조체 변수를 전달할 때 보다 더 효율적입니다. 반면에 구조 전역 힙에 대 한 메모리 할당이 필요 하지 않습니다.  
  
 구조체를 상속할 수 없습니다, 확장할 필요 하지 않은 개체에 대해서만 구조를 사용 해야 합니다. 만들려는 개체 소형 인스턴스 크기가 고 구조체와 클래스의 성능 특성을 고려 하는 경우에 구조를 사용 합니다.  
  
## <a name="similarities"></a>유사성  
 구조체와 클래스에는 다음과 같은 점에서 비슷합니다.  
  
-   둘 다 *컨테이너* 형식, 다른 형식을 멤버로 포함 되어 있는 것을 의미 합니다.  
  
-   둘 다 생성자, 메서드, 속성, 필드, 상수, 열거형, 이벤트 및 이벤트 처리기를 포함할 수 있는 멤버입니다. 그러나 이러한 멤버는 선언 된와 혼동 하지 마십시오 *요소* 구조입니다.  
  
-   둘 다의 구성원이 액세스 수준을 개별화 있을 수 있습니다. 예를 들어 한 멤버를 선언할 수 있습니다 `Public` 또 다른 `Private`합니다.  
  
-   둘 다 인터페이스를 구현할 수 있습니다.  
  
-   둘 다 사용 하거나 매개 변수 없이 공유 생성자를 가질 수 있습니다.  
  
-   둘 다를 노출할 수는 *기본 속성*로 속성은 하나 이상의 매개 변수를 사용 합니다.  
  
-   모두 선언 하 고, 이벤트를 발생 시킬 수 및 대리자를 선언할 수 있습니다.  
  
## <a name="differences"></a>차이점  
 구조체와 클래스는 다음과 같은 점에서 서로 다릅니다.  
  
-   구조체는 *값 형식이*; 클래스는 *참조 형식*합니다. 구조체의 데이터를 포함 하는 구조체 형식의 변수 대신 클래스 형식으로 데이터에 대 한 참조를 포함 합니다.  
  
-   스택 할당;을 사용 하 여 구조 클래스는 힙 할당을 사용합니다.  
  
-   구조체 요소는 모두 `Public` 기본적으로 클래스 변수 및 상수는 `Private` 다른 클래스 멤버는 기본적으로 `Public` 기본적으로 합니다. 이 동작은 클래스 멤버에 대 한 기본값의 Visual Basic 6.0 시스템와의 호환성을 제공합니다.  
  
-   구조체에는 하나 이상의 비공유 변수 또는 비공유, 사용자를 사용 해야 합니다. 이벤트 요소입니다. 클래스는 완전히 비어 있을 수 있습니다.  
  
-   구조 요소도 선언할 수 없습니다 `Protected`; 클래스 멤버 수입니다.  
  
-   경우에 구조 프로시저 이벤트를 처리할 수는 [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub` 프로시저 및만 방법으로 [AddHandler 문](../../../../visual-basic/language-reference/statements/addhandler-statement.md); 모든 클래스 프로시저는 중하나를사용하여이벤트를처리할수[ 처리](../../../../visual-basic/language-reference/statements/handles-clause.md) 키워드 또는 `AddHandler` 문. 자세한 내용은 [이벤트](../../../../visual-basic/programming-guide/language-features/events/index.md)를 참조하세요.  
  
-   구조체 변수 선언 이니셜라이저 또는 배열;에 대 한 초기 크기를 지정할 수 없습니다. 클래스 변수 선언을 할 수 있습니다.  
  
-   구조에서 암시적으로 상속 된 <xref:System.ValueType?displayProperty=nameWithType> 클래스 및 다른 모든 형식;에서 상속할 수 없습니다. 클래스 이외의 다른 클래스 또는 클래스에서 상속할 수 있습니다 <xref:System.ValueType?displayProperty=nameWithType>합니다.  
  
-   구조체가 상속할 수 있습니다. 클래스는입니다.  
  
-   구조는 절대 종료 되지 않으므로 공용 언어 런타임 (CLR)를 호출 하지 않습니다는 <xref:System.Object.Finalize%2A> 메서드; 모든 구조를 클래스를 호출 하는 가비지 수집기 (GC)에 의해 종료 되었는지 <xref:System.Object.Finalize%2A> 활성 참조가 없는 것을 발견 하면 클래스 남은입니다.  
  
-   구조체 생성자; 필요 하지 않습니다. 클래스는 다음 작업을 수행 하지 않습니다.  
  
-   구조체를 가질 수 매개 변수를 사용 하는 경우에 공유 되지 않는 생성자 클래스는 매개 변수 없이 또는 되도록 할 수 있습니다.  
  
 모든 구조에는 매개 변수가 없는 암시적 공용 생성자를 있습니다. 이 생성자는 구조체의 모든 데이터 요소를를 기본값으로 초기화합니다. 이 동작을 재정의할 수 없습니다.  
  
## <a name="instances-and-variables"></a>인스턴스 및 변수  
 구조체는 값 형식 이므로 각 구조 변수 영구적으로 개별 구조 인스턴스에 바인딩되어 있습니다. 하지만 클래스는 참조 형식 및 개체 변수에 서로 다른 시간에 다양 한 클래스 인스턴스를 참조할 수 있습니다. 이 차이는 다음과 같은 방법으로 구조체와 클래스의 사용을 달라 집니다.  
  
-   **초기화 합니다.** 구조체 변수는 구조체의 매개 변수가 없는 생성자를 사용 하 여 요소의 초기화가 암시적으로 포함 됩니다. 따라서 `Dim s As struct1` 같습니다 `Dim s As struct1 = New struct1()`합니다.  
  
-   **변수를 지정 합니다.** 다른 구조체 변수를 할당 하거나 구조체 인스턴스 프로시저 인수를 전달할 때 변수 모든 요소의 현재 값은 새 구조로 복사 됩니다. 다른 개체 변수 할당 또는 프로시저에는 개체 변수를 전달 하는 경우 참조 포인터가 복사 됩니다.  
  
-   **Nothing를 할당 합니다.** 값을 할당할 수 [Nothing](../../../../visual-basic/language-reference/nothing.md) 구조에 인스턴스가 되지만 변수를 계속 해 서 변수와 연결 된입니다. 해당 메서드를 호출 하 고 변수 요소가 다시 할당 하 여 초기화 하지만 해당 데이터 요소에 액세스할 수 있습니다.  
  
     개체 변수를 설정 하면 반대로 `Nothing`클래스 인스턴스에서 분리 하 고 다른 인스턴스를 할당할 때까지 변수를 통해 모든 멤버를 액세스할 수 없습니다.  
  
-   **여러 개의 인스턴스입니다.** 개체 변수는 서로 다른 시간에 할당 된 다른 클래스 인스턴스를 가질 수 및 동시에 여러 개의 개체 변수가 동일한 클래스 인스턴스를 참조할 수 있습니다. 클래스 멤버의 값에 적용 한 변경 내용 동일한 인스턴스를 가리키는 다른 변수를 통해 액세스 하는 경우에 해당 멤버를 영향을 줍니다.  
  
     그러나 구조 요소를 자신의 인스턴스 내에서 격리 됩니다. 해당 값에 대 한 변경의 동일한 다른 인스턴스에 있는 변수를 포함 하 여 다른 구조 변수에 반영 되지 않습니다 `Structure` 선언 합니다.  
  
-   **같음입니다.** 요소 별로 테스트와 함께 두 같음 테스트를 수행 되어야 합니다. 두 개체 변수를 사용 하 여 비교할 수는 <xref:System.Object.Equals%2A> 메서드. <xref:System.Object.Equals%2A>두 변수의 같은 인스턴스를 가리키는지 여부를 나타냅니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [복합 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [값 형식과 참조 형식](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [구조체](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [데이터 형식 문제 해결](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [구조체 및 기타 프로그래밍 요소](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 [개체 및 클래스](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
