---
title: "형식 승격 (Visual Basic) | Microsoft 문서"
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
- declared elements, scope
- visibility, declared elements
- Partial keyword, unexpected results with type promotion
- scope, declared elements
- scope, Visual Basic
- type promotion
- declared elements, visibility
ms.assetid: 035eeb15-e4c5-4288-ab3c-6bd5d22f7051
caps.latest.revision: 17
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
ms.openlocfilehash: d732e765fc28eaedc0deab477dbf9955a40e97c9
ms.lasthandoff: 03/13/2017

---
# <a name="type-promotion-visual-basic"></a>형식 승격(Visual Basic)
모듈에는 프로그래밍 요소를 선언 하는 경우 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 범위 모듈을 포함 하는 네임 스페이스를 승격 합니다. 이 이라고 *형식 승격*합니다.  
  
 다음 예제에서는 모듈의 기본 정 및 해당 모듈의 두 가지 멤버를 보여 줍니다.  
  
 [!code-vb[VbVbalrDeclaredElements #&1;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_1.vb)]  
  
 내에서 `projModule`프로그래밍, 모듈 수준에서 선언 된 요소 수준이 올라간 `projNamespace`합니다. 앞의 예제에서 `basicEnum` 및 `innerClass` 승격 된 되지만 `numberSub` 않으므로, 모듈 수준에서 선언 되지 않았습니다.  
  
## <a name="effect-of-type-promotion"></a>형식 승격의 효과  
 형식 승격의 효과 한정 문자열 모듈 이름을 포함할 필요는 없습니다. 다음 예제는 앞의 예제에서 프로시저를 두 번 호출을 만듭니다.  
  
 [!code-vb[VbVbalrDeclaredElements #&2;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_2.vb)]  
  
 앞의 예제에서 첫 번째 호출 완전 한 한정 문자열을 사용합니다. 그러나이 필요 없는 인해 형식 승격 합니다. 두 번째 호출도 액세스 모듈의 멤버를 포함 하지 않고 `projModule` 한정 문자열에 있습니다.  
  
## <a name="defeat-of-type-promotion"></a>형식 승격의 무효화  
 네임 스페이스에는 모듈 멤버와 동일한 이름 가진 멤버 이미 있으면 형식 승격이 무효화 됩니다 해당 모듈 멤버입니다. 다음 예제에서는 열거형과 같은 네임 스페이스 내에서 모듈의 기본 정의 보여 줍니다.  
  
 [!code-vb[VbVbalrDeclaredElements #&3;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_3.vb)]  
  
 앞의 예제에서 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 클래스를 승격할 수 없습니다 `abc` 를 `thisNameSpace` 네임 스페이스 수준에서 동일한 이름의 열거형 이미 있기 때문에 있습니다. 에 액세스 하려면 `abcSub`, 정규화 문자열을 사용 해야 `thisNamespace.thisModule.abc.abcSub`합니다. 그러나 클래스 `xyz` 는 여전히 승격 액세스할 수 있습니다 `xyzSub` 짧은 한정 문자열 `thisNamespace.xyz.xyzSub`합니다.  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a>부분 형식에 대 한 형식 승격의 무효화  
 클래스 또는 구조체 모듈 내에서 사용 하는 경우는 [부분](../../../../visual-basic/language-reference/modifiers/partial.md) 키워드, 형식 승격을 자동으로 해당 클래스 또는 구조체에 대 한 네임 스페이스에 동일한 이름 가진 멤버가 있는지 여부. 모듈에서 다른 요소는 여전히 형식 승격에 적합 합니다.  
  
 **결과가 발생 합니다.** 부분 정의의 형식 승격의 무효화도 컴파일러 오류 및 예기치 않은 결과가 발생할 수 있습니다. 다음 예제에서는 그 중 하나는 모듈 내 클래스의 기본 부분 정의 보여 줍니다.  
  
 [!code-vb[VbVbalrDeclaredElements #&4;](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_4.vb)]  
  
 앞의 예제에서 개발자의 두 부분 정의를 병합할 컴파일러 예상 `sampleClass`합니다. 그러나 컴파일러 내의 부분 정의 대 한 승격 고려 하지 않습니다 `sampleModule`합니다. 결과적으로, 두 개의 개별 클래스를 컴파일하려고 시도 이라는 `sampleClass` 로 같지만 서로 다른 한정 경로입니다.  
  
 컴파일러는 정규화된 경로가 동일한 경우에만 부분 정의를 병합합니다.  
  
## <a name="recommendations"></a>권장 사항  
 다음 권장 사항을 바람직한 프로그래밍 관행을 나타냅니다.  
  
-   **고유 이름입니다.** 프로그래밍 요소 이름 지정에 대 한 모든 권한을 있으면 고유 이름을 사용 하는 것은입니다. 동일한 이름을 추가 정해야 할 수 있으며 코드를 읽기 어려울. 사소한 오류와 예기치 않은 결과가 발생할 수 있습니다.  
  
-   **전체 경로입니다.** 모듈 및 기타 요소는 동일한 네임 스페이스에서와 작업 하는 항상 모든 프로그래밍 요소에 대 한 정규화를 사용 하는 가장 안전한 방법은입니다. 형식 승격 모듈 멤버에 대 한 패배 하 고 해당 멤버를 완벽 하 게 지정 하지 않으면 실수로 다른 프로그래밍 요소를 액세스할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Module 문](../../../../visual-basic/language-reference/statements/module-statement.md)   
 [Namespace 문](../../../../visual-basic/language-reference/statements/namespace-statement.md)   
 [부분](../../../../visual-basic/language-reference/modifiers/partial.md)   
 [Visual Basic의 범위](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)   
 [방법: 변수의 범위 제어](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)   
 [선언된 요소 참조](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
