---
title: "/nostdlib (Visual Basic) | Microsoft 문서"
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
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
caps.latest.revision: 18
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
ms.openlocfilehash: 3bacd7d51d12ec6c48dc11ff4b83d842a9e78a30
ms.lasthandoff: 03/13/2017

---
# <a name="nostdlib-visual-basic"></a>/nostdlib(Visual Basic)
컴파일러가를 자동으로 표준 라이브러리를 참조 하지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
/nostdlib  
```  
  
## <a name="remarks"></a>주의  
 `/nostdlib` 옵션 System.dll 어셈블리에 대 한 자동 참조를 제거 하 고는 컴파일러가 Vbc.rsp 파일을 읽을 수 없습니다. Vbc.rsp 파일-Vbc.exe 파일과 동일한 디렉터리에 있는-자주 사용 되는 참조 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 어셈블리 및 가져오기는 `System` 및 `Microsoft.VisualBasic` 네임 스페이스입니다.  
  
> [!NOTE]
>  Mscorlib.dll 및 Microsoft.VisualBasic.dll 어셈블리는 항상 참조 합니다.  
  
> [!NOTE]
>  `/nostdlib` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 명령줄에서 컴파일할 때에 사용할 수는 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 `T2.vb` 표준 라이브러리를 참조 하지 않고 있습니다. 설정 해야는 `_MYTYPE` 조건부 컴파일 상수를 문자열 "Empty"를 제거 하는 `My` 개체입니다.  
  
```  
vbc /nostdlib /define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a>참고 항목  
 [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)   
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [My에 사용할 수 있는 개체 사용자 지정](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)
