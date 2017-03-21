---
title: "Option Explicit 문 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Explicit
- vb.OptionExplicit
dev_langs:
- VB
helpviewer_keywords:
- declaring variables, explicit
- forced variable declaration in Option Explicit statement
- Explicit keyword
- explicit variable declaration
- Option Explicit statement
ms.assetid: e82ac1ad-2cd3-49b2-b985-8bcf016f3fcc
caps.latest.revision: 17
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
ms.openlocfilehash: 020f12f1fbb9a06647215f1fac6324e3b74e8a77
ms.lasthandoff: 03/13/2017

---
# <a name="option-explicit-statement-visual-basic"></a>Option Explicit 문(Visual Basic)
파일의 모든 변수에 대해 명시적으로 강제 또는 변수의 암시적 선언을 허용 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a>요소  
 `On`  
 선택적 요소. 수 있도록 `Option Explicit` 검사 합니다. 경우 `On` 또는 `Off` 를 지정 하지 않으면 기본값은 `On`합니다.  
  
 `Off`  
 선택적 요소. 사용 하지 않도록 설정 `Option Explicit` 확인 합니다.  
  
## <a name="remarks"></a>주의  
 때 `Option Explicit On` 또는 `Option Explicit` 를 사용 하 여 모든 변수를 명시적으로 선언 해야 파일에 표시 되는 `Dim` 또는 `ReDim` 문입니다. 선언 되지 않은 변수 이름을 사용 하려고 하면 컴파일 타임에 오류가 발생 합니다. `Option Explicit Off` 문에 변수 선언의 암시적 허용 합니다.  
  
 `Option Explicit` 문은 사용하는 경우 파일에서 다른 소스 코드 문 앞에 나와야 합니다.  
  
> [!NOTE]
>  설정 `Option Explicit` 를 `Off` 는 일반적으로 없는 것이 좋습니다. 프로그램이 실행 될 때 예기치 않은 결과가 발생 하나 이상의 위치에서 변수 이름을 잘못 입력 합니다.  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a>Option Explicit 문 현재 없는 경우  
 소스 코드에 없는 경우는 `Option Explicit` 문는 **Option Explicit** 에 설정 된 [컴파일 페이지, 프로젝트 디자이너 (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) 사용 됩니다. 명령줄 컴파일러를 사용 하는 경우는 [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) 컴파일러 옵션을 사용 합니다.  
  
#### <a name="to-set-option-explicit-in-the-ide"></a>IDE에서 Option Explicit 설정 하려면  
  
1.  **솔루션 탐색기**, 프로젝트를 선택 합니다. 에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다. 자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.  
  
2.  클릭 하 고 **컴파일** 탭 합니다.  
  
3.  값을 설정 된 **Option Explicit** 상자입니다.  
  
 새 프로젝트를 만들 때는 **Option Explicit** 에 설정 된 **컴파일** 로 설정 되는 **Option Explicit** 에서 설정는 **VB 기본값** 대화 상자. 에 액세스 하려면는 **VB 기본값** 대화 상자의 **도구** 메뉴를 클릭 하 여 **옵션**합니다. 에 **옵션** 대화 상자에서 **프로젝트 및 솔루션**를 클릭 하 고 **VB 기본값**합니다. 초기 기본 설정은 **VB 기본값** 는 `On`합니다.  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a>명령줄에서 Option Explicit 설정 하려면  
  
-   포함은 [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) 컴파일러 옵션에는 **vbc** 명령입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Option Explicit` 문을 모든 변수에 대해 명시적 선언을 강제 적용 합니다. 선언 되지 않은 변수를 사용 하려고 하면 컴파일 타임에 오류가 발생 합니다.  
  
 [!code-vb[VbVbalrStatements #&47;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_1.vb)]  
  
 [!code-vb[VbVbalrStatements #&48;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_2.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)   
 [ReDim 문](../../../visual-basic/language-reference/statements/redim-statement.md)   
 [Option Compare 문](../../../visual-basic/language-reference/statements/option-compare-statement.md)   
 [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)   
 [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)   
 [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)   
 [옵션 대화 상자, 프로젝트, Visual Basic 기본값](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
