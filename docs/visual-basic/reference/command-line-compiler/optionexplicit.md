---
title: /optionexplicit
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: /optionexplicit
helpviewer_keywords:
- /optionexplicit compiler option [Visual Basic]
- optionexplicit compiler option [Visual Basic]
- -optionexplicit compiler option [Visual Basic]
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1cfdb94ebafa7d6a14253aeb59ab98b3a953fe4b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="optionexplicit"></a>/optionexplicit
사용 하면 컴파일러 오류 보고를 사용 하기 전에 선언 되지 않은 경우.  
  
## <a name="syntax"></a>구문  
  
```  
/optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a>인수  
 `+` &#124; `-`  
 선택 사항입니다. 지정 `/optionexplicit+` 명시적 변수 선언이 필요 합니다. `/optionexplicit+` 옵션은 기본값 이므로 동일 `/optionexplicit`합니다. `/optionexplicit-` 옵션을 사용 하면 변수를 암시적으로 선언 합니다.  
  
## <a name="remarks"></a>설명  
 소스 코드 파일을 포함 하는 경우는 [Option Explicit 문](../../../visual-basic/language-reference/statements/option-explicit-statement.md), 문이 재정의 `/optionexplicit` 명령줄 컴파일러 설정을 사용 합니다.  
  
### <a name="to-set-optionexplicit-in-the-visual-studio-ide"></a>/Optionexplicit Visual Studio IDE에서 설정 하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. **프로젝트** 메뉴에서 **속성**을 클릭합니다. 자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.  
  
2.  **컴파일** 탭을 클릭합니다.  
  
3.  값을 수정 된 **Option Explicit** 상자입니다.  
  
## <a name="example"></a>예제  
 다음 코드를 컴파일한 경우 `/optionexplicit-` 사용 됩니다.  
  
 [!code-vb[VbVbalrCompiler#5](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/optionexplicit_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Option Explicit 문](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [옵션 대화 상자, 프로젝트, Visual Basic 기본값](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
