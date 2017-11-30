---
title: "프로시저 오버로딩(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- signatures
- Overloads keyword [Visual Basic]
- hiding by signature
- Visual Basic code, procedures
- procedures [Visual Basic], signatures for
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- parameters [Visual Basic], lists
- signatures [Visual Basic], procedure
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- Shadows keyword [Visual Basic]
- procedure overloading
- procedures [Visual Basic], parameter lists
ms.assetid: fbc7fb18-e3b2-48b6-b554-64c00ed09d2a
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 65fd5a6763752c616f13891bfa5acabff6115d7c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="procedure-overloading-visual-basic"></a>프로시저 오버로딩(Visual Basic)
*오버 로드* 프로시저 이름은 같지만 다른 매개 변수 목록을 사용 하 여 여러 버전에서 정의 의미 합니다. 오버 로드의 목적은 이름을 다르게 필요 없이 프로시저의 밀접 한 관련이 있는 여러 버전을 정의 하는 것입니다. 매개 변수 목록을 변경 하 여이 작업을 수행 합니다.  
  
## <a name="overloading-rules"></a>규칙 오버 로드  
 프로시저를 오버 로드할 때는 다음 규칙이 적용 됩니다.  
  
-   **이름이 같은**합니다. 각 오버 로드 된 버전에는 동일한 프로시저 이름을 사용 해야 합니다.  
  
-   **다른 서명**합니다. 다음 측면과 관련 하 여 하나 이상의 다른 모든 오버 로드 된 버전에서 각 오버 로드 된 버전 달라 야 합니다.  
  
    -   매개 변수 개수  
  
    -   매개 변수의 순서  
  
    -   매개 변수 데이터 형식  
  
    -   형식 매개 변수 (제네릭 프로시저의 경우)의 수  
  
    -   반환 형식 (변환 연산자)에  
  
     위의 항목은 전체적으로 프로시저 이름과 함께 호출 된 *서명* 프로시저의 합니다. 오버 로드 된 프로시저를 호출할 때 컴파일러는 서명을 사용 하 여 호출이 올바르게 정의 일치 하는지 확인 합니다.  
  
-   **서명 포함 되지 않는 항목**합니다. 서명을 변경 하지 않고 프로시저를 오버 로드할 수 없습니다. 특히, 다음 항목 중 하나 이상의 변경 하 여 프로시저를 오버 로드할 수 없습니다 있습니다.  
  
    -   프로시저 한정자 키워드와 같은 `Public`, `Shared`, 및`Static`  
  
    -   매개 변수 또는 형식 매개 변수 이름  
  
    -   형식 매개 변수 제약 조건 (제네릭 프로시저의 경우)  
  
    -   매개 변수 한정자 키워드와 같은 `ByRef` 및`Optional`  
  
    -   값을 반환 하는지 여부  
  
    -   반환 값 (변환 연산자 제외)의 데이터 형식  
  
     앞의 목록에 항목 서명의 일부가 않습니다. 사용할 수는 없지만 해당 오버 로드 된 버전을 구분할 수를 적절히 서명만 구분 되어 있는 오버 로드 버전에서 변경할 수 있습니다.  
  
-   **런타임에 바인딩된 인수**합니다. 오버 로드 된 버전을 런타임에 바인딩된 개체 변수를 전달 하려는 경우으로 적절 한 매개 변수를 선언 해야 <xref:System.Object>합니다.  
  
## <a name="multiple-versions-of-a-procedure"></a>여러 버전의 프로시저  
 작성 하는 경우를 가정해 볼는 `Sub` 고객의 균형 및 수에 대 한 트랜잭션을 게시 하는 프로시저 이름으로 또는 계정 번호 고객에 게 참조 수 있게 되기를 원하는 합니다. 이 위해 두 개의 다른 정의할 수 있습니다 `Sub` 다음 예제와 같이 프로시저:  
  
 [!code-vb[VbVbcnProcedures#73](./codesnippet/VisualBasic/procedure-overloading_1.vb)]  
  
### <a name="overloaded-versions"></a>오버 로드 된 버전  
 대신 단일 프로시저 이름을 오버 로드 되려고 합니다. 사용할 수는 [오버 로드](../../../../visual-basic/language-reference/modifiers/overloads.md) 키워드를 각 매개 변수 목록에 대 한 프로시저의 버전을 다음과 같이 정의 합니다.  
  
 [!code-vb[VbVbcnProcedures#72](./codesnippet/VisualBasic/procedure-overloading_2.vb)]  
  
#### <a name="additional-overloads"></a>추가 오버 로드  
 거래 금액을 적용 하려는 경우 `Decimal` 또는 `Single`, 추가로 오버 로드 하면 `post` 이 변형에 대해 수 있도록 합니다. 동일한 작업을 수행 하는 경우 각 앞의 예제에서 오버 로드 해야 4 `Sub` 프로시저 이름이 같은 같지만 서로 다른 네 개의 서명 합니다.  
  
## <a name="advantages-of-overloading"></a>오버 로드의 장점  
 프로시저 오버 로드의 장점은 호출의 유연성에서입니다. 사용 하는 `post` 앞의 예제에서 선언 된 프로시저 호출 코드로 고객 id를 가져올 수는 `String` 또는 `Integer`, 두 경우 모두에서 같은 프로시저를 호출 합니다. 다음 예제는 이러한 과정을 보여 줍니다.  
  
 [!code-vb[VbVbcnProcedures#56](./codesnippet/VisualBasic/procedure-overloading_3.vb)]  
  
 [!code-vb[VbVbcnProcedures#57](./codesnippet/VisualBasic/procedure-overloading_4.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [절차](./index.md)  
 [방법: 여러 버전의 프로시저 정의](./how-to-define-multiple-versions-of-a-procedure.md)  
 [방법: 오버로드된 프로시저 호출](./how-to-call-an-overloaded-procedure.md)  
 [방법: 선택적 매개 변수를 사용하는 프로시저 오버로드](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [방법: 매개 변수를 무제한으로 사용하는 프로시저 오버로드](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [프로시저를 오버로드할 때 고려해야 할 사항](./considerations-in-overloading-procedures.md)  
 [오버로드 확인](./overload-resolution.md)  
 [오버로드](../../../../visual-basic/language-reference/modifiers/overloads.md)  
 [Visual Basic의 제네릭 형식](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
