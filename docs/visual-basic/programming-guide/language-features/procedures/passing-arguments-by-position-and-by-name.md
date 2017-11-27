---
title: "위치 및 이름으로 인수 전달(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
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
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 164f69fcf23049441a0acbe05058c792d5363a03
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a>위치 및 이름으로 인수 전달(Visual Basic)
호출 하는 경우는 `Sub` 또는 `Function` 프로시저 인수를 전달할 수 있습니다 *위치별* -프로시저의 정의에 나타나는 순서로-하거나 전달할 수 있습니다 *이름별*, 하지 않고 위치에 관계를 제공 합니다.  
  
 인수 선언 된 이름에 콜론과 등호가 뒤에 지정할 이름으로 인수를 전달 하는 경우 (`:=`), 인수 값입니다. 순서에 관계 없이 명명 된 인수를 제공할 수 있습니다.  
  
 예를 들어, 다음 `Sub` 프로시저는 세 개의 인수를 사용 합니다.  
  
 [!code-vb[VbVbcnProcedures#41](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_1.vb)]  
  
 이 프로시저를 호출할 때 위치, 이름, 또는 둘 모두를 사용 하 여 인수를 제공할 수 있습니다.  
  
## <a name="passing-arguments-by-position"></a>위치로 인수 전달  
 프로시저를 호출할 수 `studentInfo` 위치로 전달 된 다음 예에서 같이 쉼표로 구분 된 인수:  
  
 [!code-vb[VbVbcnProcedures#42](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_2.vb)]  
  
 위치 인수 목록에서 선택적 인수를 생략 하면 쉼표로 대신을 보유 해야 합니다. 다음 예제에서는 `studentInfo` 없이 `age` 인수:  
  
 [!code-vb[VbVbcnProcedures#43](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_3.vb)]  
  
## <a name="passing-arguments-by-name"></a>이름으로 인수 전달  
 호출할 수 있습니다 `studentInfo` 이름으로 전달 된 인수, 또한 쉼표로 구분한 다음 예제와 같이:  
  
 [!code-vb[VbVbcnProcedures#44](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_4.vb)]  
  
## <a name="mixing-arguments-by-position-and-by-name"></a>이름 및 위치 인수 혼합  
 다음 예제와 같이 위치 하 고 하나의 프로시저 호출에서 이름으로 인수를 제공할 수 있습니다.  
  
 [!code-vb[VbVbcnProcedures#45](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_5.vb)]  
  
 앞의 예에서 쉼표로 생략 된 위치를 보유 하는 데 필요한 `age` 인수를 이후 `birth` 이름으로 전달 됩니다.  
  
 위치 및 이름, 위치 인수를 사용 하 여 인수를 제공 하는 경우 모든 먼저와 야 합니다. 이름으로 인수를 지정할 때는 되 면 나머지 인수 모두 이름별 수 있어야 합니다.  
  
## <a name="supplying-optional-arguments-by-name"></a>이름으로 선택적 인수를 제공합니다.  
 이름으로 인수 전달 선택적 인수를 여러 개 있는 프로시저를 호출 하는 경우 특히 유용 합니다. 이름으로 인수를 제공 하는 경우 연속 쉼표를 사용 하 여 생략 된 위치 인수를 나타내기 위해 필요가 없습니다. 이름으로 인수 전달 또한 쉽게 전달 하는 고 생략 되는 기능과 인수를 추적할 수 있습니다.  
  
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
