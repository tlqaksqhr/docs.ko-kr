---
title: "프로시저를 오버로드할 때 고려해야 할 사항(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- signatures [Visual Basic], ParamArray arguments
- ParamArray keyword [Visual Basic], parameter arrays
- ParamArray keyword [Visual Basic], arguments and signatures
- function overloading [Visual Basic], implicit overloads for ParamArray
- ParamArray keyword [Visual Basic], signatures
- Visual Basic code, procedures
- arguments [Visual Basic], parameter arrays
- procedures [Visual Basic], overloading
- parameters [Visual Basic], lists
- function overloading [Visual Basic], typeless programming
- typeless programming
- function overloading [Visual Basic], restrictions
- arguments [Visual Basic], optional
- optional arguments [Visual Basic], overloading
- signatures [Visual Basic], procedure
- parameter lists [Visual Basic]
- parameter arrays [Visual Basic], overloading arguments
- Visual Basic code, parameter lists
- procedure overloading [Visual Basic], considerations
- Option Explicit statement [Visual Basic]
- restrictions [Visual Basic], overloading procedures
- procedures [Visual Basic], parameter lists
ms.assetid: a2001248-10d0-42c5-b0ce-eeedc987319f
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3c9a9a4759d4ec2dd87778c49c4fd82a08c081a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="considerations-in-overloading-procedures-visual-basic"></a>프로시저를 오버로드할 때 고려해야 할 사항(Visual Basic)
프로시저를 오버 로드할 때는 다른 사용 해야 *서명* 각 오버 로드 된 버전에 대 한 합니다. 일반적으로 즉, 각 버전에는 다른 매개 변수 목록을 지정 해야 합니다. 자세한 내용은 "다른 서명"의 참조 [프로시저 오버 로드](./procedure-overloading.md)합니다.  
  
 오버 로드할 수 있습니다는 `Function` 사용 하 여 프로시저는 `Sub` 프로시저를 반대로 시그니처가 다르면를 제공 합니다. 두 개의 오버 로드가 없습니다는 다를 하나에 값을 반환 하 고 다른 때는 그렇지 않습니다.  
  
 같은 방법으로 프로시저 오버 로드를 속성에 오버 로드와 동일한 제한이 적용 됩니다. 그러나 프로시저를 오버 로드할 수 없습니다 또는 그 반대로 속성을 사용 합니다.  
  
## <a name="alternatives-to-overloaded-versions"></a>오버 로드 된 버전에 대 한 대안  
 경우에 따라 해야 오버 로드 된 버전에 대 한 대안 특히의 수에는 변수 또는 인수를 생략할 경우.  
  
 선택적 인수 하 여 모든 언어에서 지원 되는 것은 아니며 및 매개 변수 배열은를 제한 하는 염두에 둬야 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]합니다. 여러 다른 언어로 작성 된 코드에서 호출 될 가능성이 있는 프로시저를 작성 하는 경우 버전 제공 시 뛰어난 유연성 오버 로드 됩니다.  
  
### <a name="overloads-and-optional-arguments"></a>오버 로드 및 선택적 인수  
 호출 코드에서 필요에 따라 제공 하거나 하나 이상의 인수를 생략할 수, 하는 경우 여러 오버 로드 된 버전을 정의 또는 선택적 매개 변수를 사용할 수 있습니다.  
  
#### <a name="when-to-use-overloaded-versions"></a>오버 로드 된 버전을 사용 하는 경우  
 다음과 같은 경우에는 일련의 오버 로드 된 버전을 정의 고려할 수 있습니다.  
  
-   프로시저 코드의 논리는 호출 코드 제공 되는 선택적 인수 여부에 따라 크게 다릅니다.  
  
-   프로시저 코드는 호출 코드가 선택적 인수를 제공 했는지 여부에 안정적으로 테스트할 수 없습니다. 이 경우, 예를 들어, 기본 값에 대 한 가능한 후보 없는 경우 호출 코드 되지 않을을 제공 합니다.  
  
#### <a name="when-to-use-optional-parameters"></a>선택적 매개 변수를 사용 하는 경우  
 다음과 같은 경우에 하나 이상의 선택적 매개 변수를 선호할 수 있습니다.  
  
-   필요한 작업만 호출 하는 코드는 선택적 인수를 제공 하지 않는 경우 기본값에 매개 변수를 설정 하는 것입니다. 이 경우 프로시저 코드 수 덜 복잡 하 게 하나 이상의 단일 버전을 정의 하는 경우 `Optional` 매개 변수입니다.  
  
 자세한 내용은 참조 [선택적 매개 변수](./optional-parameters.md)합니다.  
  
### <a name="overloads-and-paramarrays"></a>오버 로드와 ParamArrays  
 호출 코드에서 가변 개수의 인수를 전달할 수, 하는 경우 여러 오버 로드 된 버전을 정의 하거나 매개 변수 배열을 사용 하 여 수 있습니다.  
  
#### <a name="when-to-use-overloaded-versions"></a>오버 로드 된 버전을 사용 하는 경우  
 다음과 같은 경우에는 일련의 오버 로드 된 버전을 정의 고려할 수 있습니다.  
  
-   호출 코드 되지을 통과 하는지 적은 수의 값 보다 많은 매개 변수 배열에 알 수 있습니다.  
  
-   프로시저 코드의 논리는 호출 코드에서 전달 값의 개수에 따라 크게 다릅니다.  
  
-   호출 코드는 서로 다른 데이터 형식의 값을 전달할 수 있습니다.  
  
#### <a name="when-to-use-a-parameter-array"></a>매개 변수 배열을 사용 하는 경우  
 여는 것이 좋습니다는 `ParamArray` 다음과 같은 경우에는 매개 변수:  
  
-   호출 코드에서 매개 변수 배열에 전달할 수 값의 개수를 예측할 수 없는 및 많은 수 있습니다.  
  
-   면 프로시저 논리가 인계 호출 코드에서 전달 기본적으로 모든 값에 같은 작업을 수행 하는 모든 값을 반복 합니다.  
  
 자세한 내용은 참조 [매개 변수 배열](./parameter-arrays.md)합니다.  
  
## <a name="implicit-overloads-for-optional-parameters"></a>선택적 매개 변수에 대 한 암시적 오버 로드  
 프로시저는 [옵션](../../../../visual-basic/language-reference/modifiers/optional.md) 매개 변수는 선택적 매개 변수를 사용 하 고 하지 않는 두 개의 오버 로드 된 프로시저입니다. 이 중 하나에 해당 하는 매개 변수 목록을 사용 하 여 이러한 프로시저를 오버 로드할 수 없습니다. 다음 선언을 이러한 경우를 설명 합니다.  
  
 [!code-vb[VbVbcnProcedures#58](./codesnippet/VisualBasic/considerations-in-overloading-procedures_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#60](./codesnippet/VisualBasic/considerations-in-overloading-procedures_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#61](./codesnippet/VisualBasic/considerations-in-overloading-procedures_3.vb)]  
  
 둘 이상의 선택적 매개 변수를 사용 하 여 프로시저, 앞의 예제에서와 비슷한 논리에 의해에 도착 한 암시적 오버 로드 집합이 있습니다.  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a>ParamArray 매개 변수에 대 한 암시적 오버 로드  
 컴파일러에 사용 하 여 프로시저 있다고 간주는 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) 무한 어떤 호출 코드에서 전달 매개 변수 배열에 다음과 같이 서로 다른 오버 로드 중에 매개 변수:  
  
-   호출 코드에 인수를 제공 하지 않는 하나의 오버 로드는`ParamArray`  
  
-   호출 코드 1 차원 배열을 제공 하는 경우 하나의 오버 로드는 `ParamArray` 요소 형식  
  
-   양의 정수에 대해 하나의 오버 로드에 대 한 호출 코드를 해당 수의 각 인수를 제공 하는 경우는 `ParamArray` 요소 형식  
  
 다음 선언을 이러한 암시적 오버 로드를 보여 줍니다.  
  
 [!code-vb[VbVbcnProcedures#68](./codesnippet/VisualBasic/considerations-in-overloading-procedures_4.vb)]  
  
 [!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/considerations-in-overloading-procedures_5.vb)]  
  
 매개 변수 배열에 대 한 1 차원 배열을 사용 하는 매개 변수 목록으로 이러한 프로시저를 오버 로드할 수 없습니다. 그러나 다른 암시적 오버 로드의 서명에 사용할 수 있습니다. 다음 선언을 이러한 경우를 설명 합니다.  
  
 [!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/considerations-in-overloading-procedures_6.vb)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a>오버 로드 하는 대신 관대 한 형식의 프로그래밍  
 호출 코드를 다른 데이터 형식 매개 변수에 전달 하려는 경우 또 다른 방법은 관대 한 형식의 프로그래밍 합니다. 형식 검사 스위치를 설정할 수 있습니다 `Off` 하나로 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md) 또는 [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) 컴파일러 옵션입니다. 다음 매개 변수의 데이터 형식을 선언할 필요가 없습니다. 그러나이 방법에는 오버 로드에 비해 다음과 같은 단점이 있습니다.  
  
-   관대 한 형식의 프로그래밍 덜 효율적인 실행 코드를 생성합니다.  
  
-   프로시저는 전달 될 수 있는 모든 데이터 형식에 대 한 테스트 해야 합니다.  
  
-   컴파일러 오류 호출 코드에서 프로시저를 지원 하지 않는 데이터 형식을 전달 하는 경우 신호 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [절차](./index.md)  
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)  
 [프로시저 문제 해결](./troubleshooting-procedures.md)  
 [방법: 여러 버전의 프로시저 정의](./how-to-define-multiple-versions-of-a-procedure.md)  
 [방법: 오버로드된 프로시저 호출](./how-to-call-an-overloaded-procedure.md)  
 [방법: 선택적 매개 변수를 사용하는 프로시저 오버로드](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [방법: 매개 변수를 무제한으로 사용하는 프로시저 오버로드](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [오버로드 확인](./overload-resolution.md)  
 [오버로드](../../../../visual-basic/language-reference/modifiers/overloads.md)
