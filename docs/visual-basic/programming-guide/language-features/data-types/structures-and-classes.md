---
title: "구조체와 클래스 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- classes [Visual Basic], vs. structures
- structures
- classes [Visual Basic]
- structures, compared to classes
- structures, structure variables
- structure variables
ms.assetid: a221e74a-ffcf-4bdc-a0f6-a088a9bf26cc
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e7402ec0fcfc279470d39a4919d3b5ec8b5d9dff
ms.lasthandoff: 03/13/2017

---
# <a name="structures-and-classes-visual-basic"></a>구조체와 클래스(Visual Basic)
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]구조체와 클래스에 대 한 구문의 통합 합니다. 그러나 구조체와 클래스 간의 중요 한 차이점도 있습니다.  
  
 클래스에는 참조 형식 이라는 이점이-참조를 전달 하는 것은 해당 데이터를 모두 사용 하 여 구조체 변수를 전달 보다 더 효율적입니다. 반면에 구조는 메모리는 전역 힙에 할당이 필요 하지 않습니다.  
  
 구조체를 상속할 수 없습니다 확장할 필요 하지 않은 개체에 대해서만 구조를 사용 해야 합니다. 만들려는 개체 소규모 인스턴스 크기가 고 구조체와 클래스의 성능 특성을 고려 하는 경우에 구조를 사용 합니다.  
  
## <a name="similarities"></a>유사점  
 구조체와 클래스에는 다음과 같은 점에서 비슷합니다.  
  
-   둘 다 *컨테이너* 형식, 다른 형식을 멤버로 포함 되어 있는 것을 의미 합니다.  
  
-   둘 다에 생성자, 메서드, 속성, 필드, 상수, 열거형, 이벤트 및 이벤트 처리기를 포함할 수 있는 멤버를 가집니다. 그러나 이러한 멤버는 선언 된와 혼동 하지 마십시오 *요소* 구조체입니다.  
  
-   둘 다의 구성원에는 액세스 수준을 개별화 있을 수 있습니다. 예를 들어 하나의 멤버를 선언할 수 있습니다 `Public` 및 다른 `Private`합니다.  
  
-   두 인터페이스를 구현할 수 있습니다.  
  
-   둘 다 사용 하거나 매개 변수 없이 공유 생성자를 가질 수 있습니다.  
  
-   모두 노출할 수는 *기본 속성*속성은 하나 이상의 매개 변수는 제공 합니다.  
  
-   둘 다를 선언 하 고 이벤트를 발생 시킬 수 및 대리자를 선언할 수 있습니다.  
  
## <a name="differences"></a>차이점  
 구조체와 클래스는 다음과 같은 점에서 차이가 있습니다.  
  
-   구조체는 *값 형식이*; 클래스는 *참조 형식*합니다. 클래스 형식으로 데이터에 대 한 참조를 포함 하는 하지 않고 구조체의 데이터를 포함 하는 구조체 형식의 변수입니다.  
  
-   스택 할당;를 사용 하는 구조체 클래스는 힙 할당을 사용합니다.  
  
-   구조체 요소는 모두 `Public` 기본적으로 클래스 변수 및 상수는 `Private` 다른 클래스 멤버는 기본적으로 `Public` 기본적으로 합니다. 이 동작은 클래스 멤버에 대 한 기본값의 Visual Basic 6.0 시스템와의 호환성을 제공합니다.  
  
-   구조체에는 하나 이상의 비공유 변수 또는 비공유, 사용자를 사용 해야 합니다. 이벤트 요소입니다. 클래스는 완전히 비어 있을 수 있습니다.  
  
-   구조 요소로 선언할 수 없습니다 `Protected`; 클래스 멤버 수입니다.  
  
-   구조체 프로시저에서는 경우에 이벤트를 처리할 수는 [공유](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub` 프로시저 및만 방법으로 [AddHandler 문](../../../../visual-basic/language-reference/statements/addhandler-statement.md); 클래스는 모든 프로시저 중 하나를 사용 하 여 이벤트를 처리할 수는 [처리](../../../../visual-basic/language-reference/statements/handles-clause.md) 키워드 또는 `AddHandler` 문. 자세한 내용은 참조 [이벤트](../../../../visual-basic/programming-guide/language-features/events/index.md)합니다.  
  
-   구조체 변수 선언 이니셜라이저 또는; 배열의 초기 크기를 지정할 수 없습니다. 변수 선언 클래스는 다음 작업을 할 수 있습니다.  
  
-   구조에서 암시적으로 상속는 <xref:System.ValueType?displayProperty=fullName>클래스 및 다른 모든 형식;에서 상속할 수 없는 클래스 또는 <xref:System.ValueType?displayProperty=fullName>.</xref:System.ValueType?displayProperty=fullName> 이외의 클래스에서 상속할 수 있습니다</xref:System.ValueType?displayProperty=fullName>  
  
-   구조체가 상속할 수 있습니다. 클래스는입니다.  
  
-   구조는 절대 종료 되지 않으므로 공용 언어 런타임 (CLR)를 호출 하지 않습니다는 <xref:System.Object.Finalize%2A>모든 구조; 메서드 클래스를 호출 하는 가비지 수집기 (GC)에 의해 종료 됩니다 <xref:System.Object.Finalize%2A>남은 활성 참조가 없는 것을 발견 하면 클래스에.</xref:System.Object.Finalize%2A> </xref:System.Object.Finalize%2A>  
  
-   구조체는 생성자; 필요 하지 않습니다. 클래스는 다음 작업을 수행 하지 않습니다.  
  
-   구조체는 포함할 수 매개 변수를 사용 하는 경우에 비공유 생성자 클래스는 또는 매개 변수 없이 가질 수 있습니다.  
  
 모든 구조에는 매개 변수 없이 암시적인 공용 생성자를 있습니다. 이 생성자는 구조체의 모든 데이터 요소를를 기본값으로 초기화합니다. 이 동작을 재정의할 수 없습니다.  
  
## <a name="instances-and-variables"></a>인스턴스 및 변수  
 구조는 값 형식 이므로 각 구조체 변수 개별 구조체 인스턴스에 영구적으로 바인딩됩니다. 하지만 클래스는 참조 형식 및 개체 변수에 서로 다른 시간에 다양 한 클래스 인스턴스를 참조할 수 있습니다. 이러한 차이점으로이 인해 다음과 같은 방법으로 구조체 및 클래스의 사용 현황을 달라 집니다.  
  
-   **초기화 합니다.** 구조체 변수 구조체의 매개 변수가 없는 생성자를 사용 하 여 요소의 초기화가 암시적으로 포함 됩니다. 따라서 `Dim s As struct1` 같습니다 `Dim s As struct1 = New struct1()`합니다.  
  
-   **변수를 지정 합니다.** 다른 구조체 변수를 할당 하거나 구조체 인스턴스 프로시저 인수를 전달할 때 모든 변수 요소의 현재 값을 새 구조로 복사 됩니다. 다른 개체 변수 할당 또는 프로시저에는 개체 변수를 전달 하는 경우 참조 포인터가 복사 됩니다.  
  
-   **아무 것도 할당 합니다.** 값을 할당할 수 [Nothing](../../../../visual-basic/language-reference/nothing.md) 구조에 인스턴스가 되지만 변수를 계속 해 서 변수와 연결할 수 있습니다. 해당 메서드를 호출 하 고 변수 요소가 할당 하 여 다시 초기화 하는 있지만 해당 데이터 요소에 액세스할 수 있습니다.  
  
     반대로, 개체 변수를 설정 하면 `Nothing`클래스 인스턴스에서 분리 하 고 다른 인스턴스를 할당할 때까지 변수를 통해 모든 멤버를 액세스할 수 없습니다.  
  
-   **여러 개의 인스턴스입니다.** 개체 변수는 서로 다른 시간에 할당 된 다른 클래스 인스턴스를 가질 수와 동시에 여러 개의 개체 변수가 동일한 클래스 인스턴스를 참조할 수 있습니다. 클래스 멤버의 값에 수행한 변경 내용을 동일한 인스턴스를 가리키는 다른 변수를 통해 액세스할 때 해당 멤버를 영향을 줍니다.  
  
     그러나 구조 요소는 자체 인스턴스 내에 격리 됩니다. 값으로 변경 같은 다른 인스턴스에 있는 변수를 포함 하 여 다른 구조체 변수에 반영 되지 않습니다 `Structure` 선언 합니다.  
  
-   **같음입니다.** 두 구조체의 같음 테스트를 요소 별로 테스트와 함께 수행 되어야 합니다. 두 개체 변수를 사용 하 여 비교할 수는 <xref:System.Object.Equals%2A>메서드.</xref:System.Object.Equals%2A> <xref:System.Object.Equals%2A>두 변수의 같은 인스턴스를 가리키는지 여부를 나타냅니다.</xref:System.Object.Equals%2A>  
  
## <a name="see-also"></a>참고 항목  
 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [복합 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)   
 [값 형식과 참조 형식](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [구조](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [데이터 형식 문제 해결](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [구조체 및 기타 프로그래밍 요소](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)   
 [개체 및 클래스](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
