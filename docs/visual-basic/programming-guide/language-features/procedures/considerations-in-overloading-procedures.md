---
title: "프로시저 (Visual Basic)를 오버 로드에 대 한 고려 사항 | Microsoft 문서"
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
- signatures, ParamArray arguments
- ParamArray keyword, parameter arrays
- ParamArray keyword, arguments and signatures
- function overloading, implicit overloads for ParamArray
- ParamArray keyword, signatures
- Visual Basic code, procedures
- arguments [Visual Basic], parameter arrays
- procedures, overloading
- parameters, lists
- function overloading, typeless programming
- typeless programming
- function overloading, restrictions
- arguments [Visual Basic], optional
- optional arguments, overloading
- signatures, procedure
- parameter lists
- parameter arrays, overloading arguments
- Visual Basic code, parameter lists
- procedure overloading, considerations
- Option Explicit statement
- restrictions, overloading procedures
- procedures, parameter lists
ms.assetid: a2001248-10d0-42c5-b0ce-eeedc987319f
caps.latest.revision: 26
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
ms.openlocfilehash: aa20cf367fba157f88afd861a4799540dcdecde1
ms.lasthandoff: 03/13/2017

---
# <a name="considerations-in-overloading-procedures-visual-basic"></a>프로시저를 오버로드할 때 고려해야 할 사항(Visual Basic)
프로시저를 오버 로드할 때는 다른 사용 해야 *서명* 각 오버 로드 된 버전입니다. 이 경우 대체로 각 버전에는 다른 매개 변수 목록을 지정 해야 합니다. 자세한 내용은 "서로 다른 서명"의 참조 [프로시저 오버 로딩](./procedure-overloading.md)합니다.  
  
 오버 로드할 수 있습니다는 `Function` 있는 프로시저는 `Sub` 프로시저를 반대로 시그니처가 다르면를 제공 합니다. 두 오버 로드만 된다는 하나에 값을 반환 하지 않으면 달라.  
  
 같은 방법으로 프로시저를 오버 로드를 속성에 오버 로드와 동일한 제한 사항이 있습니다. 그러나 프로시저를 오버 로드할 수 없습니다 속성을 사용 하거나 그 반대의 경우도 마찬가지입니다.  
  
## <a name="alternatives-to-overloaded-versions"></a>오버 로드 된 버전에 대 한 대안  
 때로는 해야 오버 로드 된 버전에 대 한 대안의 수에는 변수 또는 인수를 생략할 경우에 특히 합니다.  
  
 매개 변수 배열은를 제한 하 고 선택적 인수입니다. 모든 언어에서 지원 되는 것은 아니며 유의 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]합니다. 여러 다른 언어로 작성 된 코드에서 호출 될 가능성이 있는 프로시저를 작성 하는 경우 버전 제공 시 뛰어난 유연성을 오버 로드 됩니다.  
  
### <a name="overloads-and-optional-arguments"></a>선택적 인수 및 오버 로드  
 호출 코드 필요에 따라 제공 하거나 하나 이상의 인수를 생략할 수, 하는 경우에 여러 오버 로드 된 버전을 정의 하거나 선택적 매개 변수를 사용 하 여 수 있습니다.  
  
#### <a name="when-to-use-overloaded-versions"></a>오버 로드 된 버전을 사용 하는 경우  
 다음과 같은 경우에는 일련의 오버 로드 된 버전을 정의 고려할 수 있습니다.  
  
-   프로시저 코드의 논리는 호출 코드 제공 되는 선택적 인수 여부에 따라 크게 다릅니다.  
  
-   프로시저 코드는 호출 코드에는 선택적 인수를 제공 하는 여부에 안정적으로 테스트할 수 없습니다. 이 경우, 예를 들어, 기본 값에 대 한 가능한 후보 없는 경우 호출 코드 수 체계를 제공 합니다.  
  
#### <a name="when-to-use-optional-parameters"></a>선택적 매개 변수를 사용 하는 경우  
 다음과 같은 경우에 하나 이상의 선택적 매개 변수를 선호할 수 있습니다.  
  
-   유일한 필수 작업 호출 하는 코드는 선택적 인수를 제공 하지 않는 경우는 기본값을 매개 변수를 설정 하는 것입니다. 이 경우 프로시저 코드 수 덜 복잡 하 게 하나 이상의와 단일 버전을 정의 하는 경우 `Optional` 매개 변수입니다.  
  
 자세한 내용은 참조 [선택적 매개 변수](./optional-parameters.md)합니다.  
  
### <a name="overloads-and-paramarrays"></a>오버 로드와 ParamArrays  
 호출 코드에서 가변 개수의 인수를 전달할 수 여러 오버 로드 된 버전을 정의할 수도 있고 매개 변수 배열을 사용할 수 있습니다.  
  
#### <a name="when-to-use-overloaded-versions"></a>오버 로드 된 버전을 사용 하는 경우  
 다음과 같은 경우에는 일련의 오버 로드 된 버전을 정의 고려할 수 있습니다.  
  
-   호출 코드는 되지 전달 적은 수의 값 보다 많은 매개 변수 배열에 알 수 있습니다.  
  
-   프로시저 코드의 논리는 호출 코드에서 전달 값의 개수에 따라 크게 다릅니다.  
  
-   호출 하는 코드는 서로 다른 데이터 형식의 값을 전달할 수 있습니다.  
  
#### <a name="when-to-use-a-parameter-array"></a>매개 변수 배열을 사용 하는 경우  
 여는 것이 좋습니다는 `ParamArray` 매개 변수는 다음과 같은 경우에서:  
  
-   호출 코드에서 매개 변수 배열에 전달할 수는 얼마나 많은 값을 예측할 수 없는 하 고 많은 수 있습니다.  
  
-   프로시저 논리가 기본적으로 모든 값에 동일한 작업을 수행 하는 호출 코드는가 전달 되는 모든 값을 반복에 적합 합니다.  
  
 자세한 내용은 참조 [매개 변수 배열](./parameter-arrays.md)합니다.  
  
## <a name="implicit-overloads-for-optional-parameters"></a>선택적 매개 변수에 대 한 암시적 오버 로드  
 프로시저는 [옵션](../../../../visual-basic/language-reference/modifiers/optional.md) 매개 변수는 선택적 매개 변수를 사용 하 고 하지 않는 두 개의 오버 로드 된 프로시저입니다. 이 중 하나에 해당 하는 매개 변수 목록을 사용 하 여 이러한 프로시저를 오버 로드할 수 없습니다. 다음과 같은 선언을 이러한 경우를 설명 합니다.  
  
 [!code-vb[VbVbcnProcedures #&58;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_1.vb)]  
  
 [!code-vb[VbVbcnProcedures #&60;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_2.vb)]  
  
 [!code-vb[VbVbcnProcedures #&61;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_3.vb)]  
  
 둘 이상의 선택적 매개 변수를 사용 하 여 프로시저를 앞의 예제와 비슷한 논리에 의해에 도착 한 암시적 오버 로드 집합이 있습니다.  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a>ParamArray 매개 변수에 대 한 암시적 오버 로드  
 컴파일러가 고려 있는 프로시저는 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) 무한 수가 어떻게 호출 코드에서 전달 매개 변수 배열에 다음과 같이 각각 서로 다른 오버 로드에 매개 변수:  
  
-   호출 코드에 인수를 제공 하지 않는 하나의 오버 로드는`ParamArray`  
  
-   호출 코드는&1; 차원 배열을 제공 하는 경우 하나의 오버 로드는 `ParamArray` 요소 형식  
  
-   양의 정수에 대 한 하나의 오버 로드에 대 한 호출 코드를 해당 수의 각 인수를 제공 하는 경우는 `ParamArray` 요소 형식  
  
 다음과 같은 선언을 이러한 암시적 오버 로드를 보여 줍니다.  
  
 [!code-vb[VbVbcnProcedures #&68;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_4.vb)]  
  
 [!code-vb[VbVbcnProcedures #&70;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_5.vb)]  
  
 매개 변수 배열에 대 한&1; 차원 배열을 사용 하는 매개 변수 목록으로는 이러한 프로시저를 오버 로드할 수 없습니다. 그러나 다른 암시적 오버 로드의 서명에 사용할 수 있습니다. 다음과 같은 선언을 이러한 경우를 설명 합니다.  
  
 [!code-vb[VbVbcnProcedures #&71;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_6.vb)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a>오버 로드 하는 대신 관대 한 형식의 프로그래밍  
 호출 코드를 다른 데이터 형식을 매개 변수로 전달할 수 있도록 하려는 경우 또 다른 방법은 관대 한 형식의 프로그래밍 합니다. 형식 검사 스위치를 설정할 수 있습니다 `Off` 하나로 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md) 또는 [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) 컴파일러 옵션입니다. 다음 매개 변수의 데이터 형식을 선언할 필요가 없습니다. 그러나이 방법에는 오버 로드에 비해 다음과 같은 단점이 있습니다.  
  
-   관대 한 형식의 프로그래밍 덜 효율적인 실행 코드를 생성합니다.  
  
-   프로시저는 전달 될 수 있는 모든 데이터 형식에 대 한 테스트 해야 합니다.  
  
-   컴파일러 호출 코드에서 프로시저를 지원 하지 않는 데이터 형식을 전달 하는 경우 오류를 표시 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로시저](./index.md)   
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)   
 [문제 해결 절차](./troubleshooting-procedures.md)   
 [방법: 여러 버전의 프로시저 정의](./how-to-define-multiple-versions-of-a-procedure.md)   
 [방법: 오버 로드 된 프로시저 호출](./how-to-call-an-overloaded-procedure.md)   
 [방법: 선택적 매개 변수를 사용 하는 프로시저 오버 로드](./how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [방법: 불특정 개수의 매개 변수를 사용 하는 프로시저 오버 로드](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)   
 [오버 로드 확인](./overload-resolution.md)   
 [오버로드](../../../../visual-basic/language-reference/modifiers/overloads.md)
