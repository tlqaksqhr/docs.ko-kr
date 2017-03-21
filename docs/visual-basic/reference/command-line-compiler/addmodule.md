---
title: "/addmodule | Microsoft 문서"
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
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
caps.latest.revision: 14
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 949962905ec933dc42301bf8c21654e73dbe2f70
ms.lasthandoff: 03/13/2017

---
# <a name="addmodule"></a>/addmodule
컴파일러에서 지정된 파일의 모든 형식 정보를 현재 컴파일하고 있는 프로젝트에 사용할 수 있도록 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/addmodule:fileList  
```  
  
## <a name="arguments"></a>인수  
 `fileList`  
 필수 요소. 메타 데이터를 포함 하지만 어셈블리 매니페스트를 포함 하지 않는 파일의 쉼표로 구분 된 목록입니다. 공백이 포함 된 파일 이름은 따옴표로 묶어야 ("").  
  
## <a name="remarks"></a>주의  
 나열 된 파일의 `fileList` 으로 매개 변수를 생성 합니다는 `/target:module` 옵션을 또는 다른 컴파일러의 동일 `/target:module`.  
  
 모든 모듈을 사용 하 여 추가 `/addmodule` 실행 시 출력 파일과 동일한 디렉터리에 있어야 합니다. 즉, 컴파일 타임에 모든 디렉터리에서 모듈을 지정할 수 있습니다 되지만 모듈에서 런타임에 응용 프로그램 디렉터리에 있어야 합니다. 그렇지 않은 경우는 <xref:System.TypeLoadException>오류.</xref:System.TypeLoadException>  
  
 (암시적 또는 명시적)을 지정 하면 모든[/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) 이외의 다른 옵션 `/target:module` 와 `/addmodule`에 전달 되는 파일이 `/addmodule` 프로젝트의 어셈블리의 일부가 됩니다. 어셈블리에 있는 출력 파일을 실행 해야 합니다. 또는 더 많은 파일 추가 `/addmodule`합니다.  
  
 사용 하 여 [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) 어셈블리를 포함 하는 파일에서 메타 데이터를 가져올 수 있습니다.  
  
> [!NOTE]
>  `/addmodule` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 명령줄에서 컴파일할 때에 사용할 수는 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드는 모듈을 만듭니다.  
  
 [!code-vb[VbVbalrCompiler #&47;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_1.vb)]  
  
 다음 코드는 모듈의 형식을 가져옵니다.  
  
 [!code-vb[VbVbalrCompiler #&48;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_2.vb)]  
  
 실행 하는 경우 `t1`, 출력 `802`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)   
 [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
