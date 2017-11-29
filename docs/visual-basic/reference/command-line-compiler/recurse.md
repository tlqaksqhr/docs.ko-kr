---
title: /recurse
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bb69c7c44dcc2e8da5eb8a76f7d22f936a6d948f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="recurse"></a>/recurse
지정된 된 디렉터리 또는 프로젝트 디렉터리의 모든 하위 디렉터리의 소스 코드 파일을 컴파일합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/recurse:[dir\]file  
```  
  
## <a name="arguments"></a>인수  
 `dir`  
 선택 사항입니다. 검색을 시작하려는 디렉터리입니다. 지정 하지 않으면 프로젝트 디렉터리에서 검색을 시작 합니다.  
  
 `file`  
 필수 요소. 검색할 파일입니다. 와일드카드 문자가 허용됩니다.  
  
## <a name="remarks"></a>설명  
 사용 하지 않고 프로젝트 디렉터리에 있는 모든 파일을 컴파일하는 파일 이름에 와일드 카드를 사용할 수 `/recurse`합니다. 출력 파일 이름은 없으므로 지정 하는 경우 컴파일러 기반 처리 하는 첫 번째 입력된 파일에 출력 파일 이름을 만듭니다. 이 일반적으로 사전순으로 볼 때 컴파일된 파일의 목록에서 첫 번째 파일입니다. 이러한 이유로 것이 가장 좋습니다 사용 하 여 출력 파일을 지정 하는 `/out` 옵션입니다.  
  
> [!NOTE]
>  `/recurse` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 명령줄에서 컴파일할 경우에 사용할 수는 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드를 컴파일하고 모든 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 현재 디렉터리에 있는 파일입니다.  
  
```  
vbc *.vb  
```  
  
 다음 코드를 컴파일하고 모든 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 파일에 `Test\ABC` 디렉터리와이 디렉터리, 한 다음 생성 `Test.ABC.dll`합니다.  
  
```  
vbc /target:library /out:Test.ABC.dll /recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)  
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
