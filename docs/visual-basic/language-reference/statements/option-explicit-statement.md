---
title: Option Explicit 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Explicit
- vb.OptionExplicit
helpviewer_keywords:
- declaring variables [Visual Basic], explicit
- forced variable declaration in Option Explicit statement [Visual Basic]
- Explicit keyword
- explicit variable declaration
- Option Explicit statement [Visual Basic]
ms.assetid: e82ac1ad-2cd3-49b2-b985-8bcf016f3fcc
ms.openlocfilehash: 3a2d81b1441052c132e4739dfe6045f8c3a026d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="option-explicit-statement-visual-basic"></a>Option Explicit 문(Visual Basic)
모든 변수는 파일에 명시적으로 강제 또는 암시적 선언을 변수의 허용 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a>요소  
 `On`  
 선택 사항입니다. 수 있도록 `Option Explicit` 검사 합니다. 경우 `On` 또는 `Off` 를 지정 하지 않으면 기본값은 `On`합니다.  
  
 `Off`  
 선택 사항입니다. 사용 하지 않도록 설정 `Option Explicit` 검사 합니다.  
  
## <a name="remarks"></a>설명  
 때 `Option Explicit On` 또는 `Option Explicit` 를 사용 하 여 모든 변수를 명시적으로 선언 해야는 파일에 표시 되는 `Dim` 또는 `ReDim` 문. 선언 되지 않은 변수 이름을 사용 하려고 하면 컴파일 타임에 오류가 발생 합니다. `Option Explicit Off` 문은 암시적 선언의 변수를 허용 합니다.  
  
 `Option Explicit` 문은 사용하는 경우 파일에서 다른 소스 코드 문 앞에 나와야 합니다.  
  
> [!NOTE]
>  설정 `Option Explicit` 를 `Off` 없는 일반적으로 것이 좋습니다. 하나 이상의 위치에서 변수 이름을 잘못 입력할 수 있습니다. 그러면 프로그램이 실행될 때 예기치 않은 결과가 발생할 수 있습니다.  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a>Option Explicit 문 현재 없는 경우  
 소스 코드에 포함 되어 있지 않으면는 `Option Explicit` 문는 **Option Explicit** 에 설정 된 [컴파일 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) 사용 됩니다. 명령줄 컴파일러를 사용 하는 경우는 [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) 컴파일러 옵션을 사용 합니다.  
  
#### <a name="to-set-option-explicit-in-the-ide"></a>IDE에서 Option Explicit을 설정 하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. **프로젝트** 메뉴에서 **속성**을 클릭합니다.  
  
2.  **컴파일** 탭을 클릭합니다.  
  
3.  값을 설정는 **Option Explicit** 상자입니다.  
  
 새 프로젝트를 만들 때는 **Option Explicit** 에 설정 된 **컴파일** 탭으로 설정 됩니다는 **Option Explicit** 에서 설정는 **VB 기본값**대화 상자. 에 액세스 하려면는 **VB 기본값** 대화 상자의 **도구** 메뉴를 클릭 하 여 **옵션**합니다. **옵션** 대화 상자에서 **프로젝트 및 솔루션**을 확장하고 **VB 기본값**을 클릭합니다. 초기 기본 설정은 **VB 기본값** 은 `On`합니다.  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a>명령줄에서 Option Explicit을 설정 하려면  
  
-   포함 된 [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) 컴파일러 옵션에는 **vbc** 명령 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Option Explicit` 문을 명시적으로 모든 변수 선언에 있습니다. 선언 되지 않은 변수를 사용 하려고 하면 컴파일 타임에 오류가 발생 합니다.  
  
 [!code-vb[VbVbalrStatements#47](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_1.vb)]  
  
 [!code-vb[VbVbalrStatements#48](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_2.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [ReDim 문](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [Option Compare 문](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [옵션 대화 상자, 프로젝트, Visual Basic 기본값](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
