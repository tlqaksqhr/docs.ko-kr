---
title: /imports(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6cdb7cff2221930113d6b49a640da0844f175f1b
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="imports-visual-basic"></a>/imports(Visual Basic)
지정된 된 어셈블리에서 네임 스페이스를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
/imports:namespaceList  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`namespaceList`|필수. 가져올 네임 스페이스의 쉼표로 구분 된 목록입니다.|  
  
## <a name="remarks"></a>설명  
 `/imports` 옵션 현재 참조 되는 어셈블리 또는 소스 파일의 집합 내에 정의 된 모든 네임 스페이스를 가져옵니다.  
  
 지정 된 네임 스페이스의 멤버 `/imports` 컴파일할 때 모든 소스 코드 파일에 사용할 수 있습니다. 사용 하 여는 [Imports 문 (.NET Namespace 및 형식)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) 단일 소스 코드 파일에서 네임 스페이스를 사용 합니다.  
  
|설정 하려면 Visual Studio 통합된 개발 환경에서 가져오는 /|  
|---|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. **프로젝트** 메뉴에서 **속성**을 클릭합니다. <br />2.  **참조** 탭을 클릭합니다.<br />3.  네임 스페이스 이름 옆의 상자에 입력 된 **사용자 가져오기 추가** 단추입니다.<br />4.  클릭는 **사용자 가져오기 추가** 단추입니다.|  
  
## <a name="example"></a>예  
 다음 코드를 컴파일한 경우 `/imports:system` 지정 됩니다.  
  
 [!code-vb[VbVbalrCompiler#21](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/imports_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)  
 [참조 및 Imports 문](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
