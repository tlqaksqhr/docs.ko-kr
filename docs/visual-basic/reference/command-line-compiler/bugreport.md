---
title: "/bugreport | Microsoft 문서"
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
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
caps.latest.revision: 22
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
ms.openlocfilehash: 9c64ec49d7e6842edbc0fed7407a34132a8f5a88
ms.lasthandoff: 03/13/2017

---
# <a name="bugreport"></a>/bugreport
버그 보고서를 파일로 작성할 때는 사용할 수 있는 파일을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
/bugreport:file  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`file`|필수 요소. 버그 보고서를 포함 하는 파일의 이름입니다. 파일 이름을 따옴표로 묶습니다 ("") 이름에 공백이 있는 경우.|  
  
## <a name="remarks"></a>주의  
 다음 정보에 추가 됩니다 `file`:  
  
-   컴파일할 때 모든 소스 코드 파일의 복사본입니다.  
  
-   컴파일에 사용 되는 컴파일러 옵션의 목록.  
  
-   컴파일러, 공용 언어 런타임 및 운영 체제에 대 한 버전 정보입니다.  
  
-   컴파일러 출력, 있는 경우입니다.  
  
-   에 대 한 메시지가 표시 되는 문제에 대 한 설명  
  
-   에 대 한 메시지가 표시 되는 문제를 생각 하는 방법에 대 한 설명을 수정 되어야 합니다.  
  
 모든 소스 코드 파일의 복사본에 포함 되어 있으므로 `file`, 가능한 가장 짧은 프로그램의 코드 결함을 재현 하는 것이 좋습니다.  
  
> [!IMPORTANT]
>  `/bugreport` 옵션은 잠재적으로 중요 한 정보가 포함 된 파일을 생성 합니다. 현재 시간, 컴파일러 버전 이때 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 버전, 운영 체제 버전, 사용자 이름, 명령줄 인수는 컴파일러를 실행 하면서 모든 소스 코드 및 참조 된 어셈블리의 모든 이진 형식입니다. 이 옵션의 서버 쪽 컴파일에 대 한 Web.config 파일에서 명령줄 옵션을 지정 하 여 액세스할 수는 [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] 응용 프로그램입니다. 이 방지 하려면 사용자가 서버에서 컴파일하지을 Machine.config 파일을 수정 합니다.  
  
 이 옵션은 함께 사용할 경우 `/errorreport:prompt`, `/errorreport:queue`, 또는 `/errorreport:send`, 응용 프로그램의 정보를 내부 컴파일러 오류를 발견 한 `file` Microsoft Corporation로 보내집니다. 정보는 Microsoft 엔지니어가 오류의 원인을 파악 하는 데 도움이 되며의 다음 릴리스를 개선 하는 데 도움이 될 수 있습니다 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]합니다. 기본적으로 정보가 Microsoft에 보내집니다. 그러나 컴파일하는 경우 응용 프로그램 사용 하 여 `/errorreport:queue`, 기본적으로 활성화 되어, 응용 프로그램의 오류 보고서를 수집 합니다. 그런 다음 컴퓨터의 관리자가 로그인 할 때 오류 보고 시스템 관리자를 로그온 이후 발생 한 모든 오류 보고서를 Microsoft에 전달 하는 팝업 창을 표시 합니다.  
  
> [!NOTE]
>  `/bugreport` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 사용할 수는 명령줄에서 컴파일할 때만 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 컴파일합니다 `T2.vb` 파일에 모든 버그 보고 정보를 저장 하 고 `Problem.txt`합니다.  
  
```  
vbc /bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md)   
 [/errorreport](../../../visual-basic/reference/command-line-compiler/errorreport.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [securityPolicy (ASP.NET 설정 스키마)에 대 한 trustLevel 요소](http://msdn.microsoft.com/en-us/729ab04c-03da-4ee5-86b1-be9d08a09369)
