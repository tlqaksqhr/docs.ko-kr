---
title: "Visual Basic의 수명 | Microsoft 문서"
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
- static variables, lifetime
- static variables, Visual Basic
- declared elements, lifetime
- Shared variable lifetime
- lifetime, declared elements
- lifetime, Visual Basic
- lifetime
ms.assetid: bd91e390-690a-469a-9946-8dca70bc14e7
caps.latest.revision: 14
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: fa0cbdf4a8fe5e8fc41e4e4f373c79451fb7b75f
ms.lasthandoff: 03/13/2017

---
# <a name="lifetime-in-visual-basic"></a>Visual Basic의 수명
*수명* 선언 요소의 시간 동안 어떤 용도로 사용할 수 있습니다. 변수는 수명이 있는 유일한 요소입니다. 이 위해 컴파일러는 프로시저 매개 변수를 처리 및 변수의 특별 한 경우로 함수를 반환 합니다. 변수의 수명 값을 저장할 수 있는 기간을 나타냅니다. 해당 값은 해당 수명 동안 변경 될 수 있지만 항상 어떤 값을 가집니다.  
  
## <a name="different-lifetimes"></a>다른 수명  
 A *멤버 변수* (다른 프로시저 외부의 모듈 수준에서 선언 됨) 일반적으로 수명이 같은 선언 된 요소입니다. 클래스 또는 구조체에 선언 된 비공유 변수 선언 된 구조체의 각 인스턴스에 대해 별도 복사본으로 존재 합니다. 각 변수는 해당 인스턴스로 수명이 동일 합니다. 그러나 한 `Shared` 변수는 응용 프로그램을 실행 하는 전체 기간 동안 지속 되는 단일 수명이 합니다.  
  
 A *지역 변수* (프로시저 내에 선언 된) 선언 된 프로시저를 실행 하는 동안에 존재 합니다. 또한 모든 함수 반환 값 및 해당 프로시저의 매개 변수에 적용 됩니다이. 그러나 해당 프로시저가 다른 프로시저를 호출 하는 경우 지역 변수 값을 유지 호출된 프로시저를 실행 하는 동안.  
  
## <a name="beginning-of-lifetime"></a>수명의 시작  
 로컬 변수의 수명 제어가 선언 되는 프로시저를 입력할 때 시작 됩니다. 프로시저를 시작 하는 즉시 모든 지역 변수 데이터 형식에 대 한 기본 값으로 초기화 됩니다를 실행 합니다. 프로시저가 발견 하는 경우는 `Dim` 초기 값을 지정 하는 문을 해당 변수를 설정 하려면 이러한 값을 코드에 이미 다른 값을 할당 한 경우에 합니다.  
  
 구조체 변수의 각 멤버는 마치는 별도 변수인 것 처럼 초기화 됩니다. 마찬가지로, 배열 변수의 각 요소는 개별적으로 초기화 됩니다.  
  
 프로시저 내의 블록 내에서 선언 된 변수 (예:는 `For` 루프) 프로시저에는 항목에 대해 초기화 됩니다. 이러한 초기화 코드 블록 실행 여부를 적용 합니다.  
  
## <a name="end-of-lifetime"></a>수명의 끝  
 프로시저 종료 되 면 해당 지역 변수의 값 유지 되지 않습니다, 그리고 및 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 해당 메모리를 회수 합니다. 다음에 프로시저를 호출할 때 모든 지역 변수가 다시 만들고 다시 초기화 합니다.  
  
 클래스 또는 구조체의 인스턴스를 종료 하는 경우의 메모리와 해당 값 비공유 변수의 손실 합니다. 클래스 또는 구조체의 각 새 인스턴스를 만들고 비공유 변수의 다시 초기화 합니다. 그러나 `Shared` 변수는 응용 프로그램의 실행이 중지 될 때까지 유지 됩니다.  
  
## <a name="extension-of-lifetime"></a>수명의 연장  
 사용 하 여 로컬 변수를 선언 하는 경우는 `Static` 키워드를 수명 보다 길면 해당 프로시저의 실행 시간입니다. 다음 표에서 프로시저 선언 기간 결정 하는 방법을 보여 줍니다.는 `Static` 변수가 존재 합니다.  
  
|프로시저 위치 및 공유|정적 변수 수명을 시작합니다|정적 변수 수명 끝|  
|------------------------------------|-------------------------------------|-----------------------------------|  
|(기본적으로 공유) 모듈에서|처음에 프로시저 호출 될 때|응용 프로그램 실행이 중지 될 때|  
|클래스에서 `Shared` (절차는 인스턴스 멤버가 아님)|처음으로 프로시저를 호출할 특정 인스턴스 또는 자체 클래스 또는 구조체 이름|응용 프로그램 실행이 중지 될 때|  
|클래스의 인스턴스에 하지 `Shared` (절차는 인스턴스 멤버는)|프로시저 라고 하는 특정 인스턴스에 처음으로|가비지 수집 (GC)에 인스턴스가 해제 되는 경우|  
  
## <a name="static-variables-of-the-same-name"></a>이름이 같은 정적 변수  
 둘 이상의 프로시저에 같은 이름의 정적 변수를 선언할 수 있습니다. 이 작업을 수행 하는 경우는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러는 각 변수를 별도 요소로 간주 합니다. 이러한 변수 중 하나를 초기화할 때 다른 값 영향을 주지 않습니다. 오버 로드 집합이 있는 프로시저를 정의 하 고 각 오버 로드에 동일한 이름 가진 정적 변수를 선언 하는 경우에 적용 됩니다.  
  
## <a name="containing-elements-for-static-variables"></a>정적 변수에 대 한 요소가 포함 된  
 해당 클래스의 프로시저 즉, 클래스 내의 정적 지역 변수를 선언할 수 있습니다. 그러나 구조체 멤버 또는 해당 구조 내에서 프로시저의 지역 변수로 구조체에 정적 지역 변수를 선언할 수 없습니다.  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 예제에서는 사용 하 여 변수를 선언 된 [정적](../../../../visual-basic/language-reference/modifiers/static.md) 키워드입니다. (참고 필요 하지 않은 `Dim` 키워드 때는 [Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) 와 같은 한정자를 사용 하 여 `Static`.)  
  
### <a name="code"></a>코드  
 [!code-vb[VbVbalrKeywords #&13;](../../../../visual-basic/language-reference/codesnippet/VisualBasic/lifetime_1.vb)]  
  
### <a name="comments"></a>설명  
 위의 예제에서는 변수에서에서 `applesSold` 계속 존재는 절차를 수행한 후 `runningTotal` 호출 코드로 반환 합니다. 다음에 `runningTotal` 이라고 `applesSold` 는 이전에 계산 된 값을 유지 합니다.  
  
 경우 `applesSold` 선언 되었으면 네임 스페이스를 사용 하지 않고 `Static`, 이전의 누적된 값에 대 한 호출에서 유지 되지는 것 `runningTotal`합니다. 다음에 `runningTotal` 를 호출 했지만 `applesSold` 다시 및 0으로 초기화 된 것 및 `runningTotal` 호출 된 동일한 값 단순히 반환는 합니다.  
  
### <a name="compiling-the-code"></a>코드 컴파일  
 정적 지역 변수 선언의 일부로 값을 초기화할 수 있습니다. 배열을 선언 하는 경우 `Static`, 해당 순위 (차원의 수), 각 차원의 길이 및 개별 요소의 값을 초기화할 수 있습니다.  
  
### <a name="security"></a>보안  
 앞의 예제에서 선언 하 여 동일한 수명 주기를 생성할 수 있습니다 `applesSold` 모듈 수준입니다. 그러나 변수의 범위를 이러한 방식으로 변경 하면 프로시저가 더 이상 있을 경우 단독으로 액세스할 수 없습니다. 다른 프로시저에 액세스할 수 있으므로 `applesSold` 및 해당 값을 변경, 누적 합계를 신뢰할 수 및 코드를 유지 하기 위해 더욱 어려워질 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [공유](../../../../visual-basic/language-reference/modifiers/shared.md)   
 [아무 것도](../../../../visual-basic/language-reference/nothing.md)   
 [선언된 요소 이름](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [선언 된 요소에 대 한 참조](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Visual Basic의 범위](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)   
 [Visual Basic의 액세스 수준](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [변수](../../../../visual-basic/programming-guide/language-features/variables/index.md)   
 [변수 선언](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [데이터 형식 문제 해결](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [정적](../../../../visual-basic/language-reference/modifiers/static.md)
