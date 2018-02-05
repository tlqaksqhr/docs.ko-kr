---
title: "위치 및 이름으로 인수 전달(Visual Basic)"
ms.custom: 
ms.date: 02/01/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arguments [Visual Basic], passing by name
- procedures [Visual Basic], arguments
- := passing arguments
- procedure arguments
- Visual Basic code, procedures
- named arguments [Visual Basic], passing arguments
- arguments [Visual Basic], passing by position
- Function procedures [Visual Basic], passing arguments
- named parameters [Visual Basic], passing arguments
- named arguments
- passing parameters [Visual Basic], named parameter arguments
- passing parameters [Visual Basic], by position
- procedures [Visual Basic], calling
- named parameters
- Sub procedures [Visual Basic], passing arguments
- argument passing
- passing parameters [Visual Basic], by name
- argument passing [Visual Basic], by position
- arguments [Visual Basic], listing by name
ms.assetid: 1ad7358f-1da9-48da-a95b-f3c7ed41eff3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13f5e5a8da6a899d4920a25b250ca88b2a21f559
ms.sourcegitcommit: 099aa20d9b6450d1b7452d782a55771a6ad8ff35
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2018
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a>위치 및 이름으로 인수 전달(Visual Basic)
호출 하는 경우는 `Sub` 또는 `Function` 프로시저 인수를 전달할 수 있습니다 *위치별* -프로시저의 정의에 나타나는 순서로-하거나 전달할 수 있습니다 *이름별*, 하지 않고 위치에 관계를 제공 합니다.  
  
 인수 선언 된 이름에 콜론과 등호가 뒤에 지정할 이름으로 인수를 전달 하는 경우 (`:=`), 인수 값입니다. 순서에 관계 없이 명명 된 인수를 제공할 수 있습니다.  
  
 예를 들어, 다음 `Sub` 프로시저는 세 개의 인수를 사용 합니다.  
  
 [!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]  
  
 이 프로시저를 호출할 때 위치, 이름, 또는 둘 모두를 사용 하 여 인수를 제공할 수 있습니다.  
  
## <a name="passing-arguments-by-position"></a>위치로 인수 전달  
 호출할 수 있습니다는 `Display` 메서드 인수를 위치에 의해 전달 하 고 다음 예제와 같이 쉼표로 구분 된:  
  
[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)] 
  
 위치 인수 목록에서 선택적 인수를 생략 하면 쉼표로 대신을 보유 해야 합니다. 다음 예제에서는 `Display` 메서드 없이 `age` 인수:  
  
[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)] 
  
## <a name="passing-arguments-by-name"></a>이름으로 인수 전달  
 호출할 수 있습니다 `Display` 이름으로 전달 된 인수, 또한 쉼표로 구분한 다음 예제와 같이:  
  
[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)] 

 이러한 방식으로 이름으로 인수 전달 선택적 인수를 여러 개 있는 프로시저를 호출 하는 경우 특히 유용 합니다. 이름으로 인수를 제공 하는 경우 연속 쉼표를 사용 하 여 생략 된 위치 인수를 나타내기 위해 필요가 없습니다. 이름으로 인수 전달 또한 쉽게 전달 하는 고 생략 되는 기능과 인수를 추적할 수 있습니다.  
  
## <a name="mixing-arguments-by-position-and-by-name"></a>이름 및 위치 인수 혼합  

다음 예제와 같이 위치 하 고 하나의 프로시저 호출에서 이름으로 인수를 제공할 수 있습니다.  
  
[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)] 
  
 앞의 예에서 쉼표로 생략 된 위치를 보유 하는 데 필요한 `age` 인수를 이후 `birth` 이름으로 전달 됩니다.  
  
15.5 이전 버전의 Visual Basic, 위치 및 이름, 위치 인수를 사용 하 여 인수를 제공 하는 경우 모든 먼저와 야 합니다. 이름으로 인수를 지정할 때는 되 면 나머지 인수는 모두 모든 전달 되어야 합니다 이름별으로.  다음을 호출 하는 예를 들어는 `Display` 메서드는 컴파일러 오류 표시 [BC30241: 명명 된 인수를 예상](../../../misc/bc30241.md)합니다.

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)] 

Visual Basic 15.5 부터는 위치 인수를 따르면 명명 된 인수 끝 위치 인수 올바른 위치에 있는 경우 됩니다. Visual Basic 15.5에 대 한 이전 호출에서 컴파일된 경우는 `Display` 메서드가 성공적으로 컴파일되고 컴파일러 오류가 더 이상 [BC30241](../../../misc/bc30241.md)합니다.  

순서에 관계 없이 명명 된 인수와 위치와 일치 하 고 혼합이 기능을 명명된 된 인수를 사용 하 여 코드를 더 쉽게 읽을 수 있도록 하려는 경우 특히 유용 합니다. 예를 들어, 다음 `Person` 클래스 생성자를 사용 하려면 형식의 두 인수 `Person`, 둘 다 수 `Nothing`합니다. 

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)] 

코드의 의도 확인 하는 데 도움이 될 때의 선택을 취소 하는 혼합 된 명명 된 인수와 위치 인수를 사용 하 여의 값은 `father` 및 `mother` 인수는 `Nothing`:

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)] 

명명 된 인수 위치 인수를 수행 하려면 Visual Basic 프로젝트에 다음 요소를 추가 해야 (\*.vbproj) 파일:

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

## <a name="restrictions-on-supplying-arguments-by-name"></a>이름으로 인수에 대 한 제한  

필수 인수를 입력 하지 못하도록 하려면 이름으로 인수를 전달할 수 없습니다. 선택적 인수에만 생략할 수 있습니다.  
  
매개 변수 배열을 이름으로 전달할 수 없습니다. 즉는 프로시저를 호출할 때 불특정 개수의 매개 변수 배열에 대 한 쉼표로 구분 된 인수를 제공 하 고 컴파일러가 단일 이름으로 둘 이상의 인수를 연결할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [절차](./index.md)  
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)  
 [방법: 프로시저에 인수 전달](./how-to-pass-arguments-to-a-procedure.md)  
 [값 또는 참조로 인수 전달](./passing-arguments-by-value-and-by-reference.md)  
 [선택적 매개 변수](./optional-parameters.md)  
 [매개 변수 배열](./parameter-arrays.md)  
 [선택 사항](../../../../visual-basic/language-reference/modifiers/optional.md)  
 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)
