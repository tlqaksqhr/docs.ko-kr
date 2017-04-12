---
title: "/noconfig | Microsoft 문서"
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
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
caps.latest.revision: 15
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
ms.openlocfilehash: 304d0e7fc787adb1d7776a2c047090ffc230fcc1
ms.lasthandoff: 03/13/2017

---
# <a name="noconfig"></a>/noconfig
지정 하는 컴파일러 참조 하지 않아야 자동으로 자주 사용 되는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 어셈블리 또는 가져오기는 `System` 및 `Microsoft.VisualBasic` 네임 스페이스입니다.  
  
## <a name="syntax"></a>구문  
  
```  
/noconfig  
```  
  
## <a name="remarks"></a>설명  
 `/noconfig` 옵션 Vbc.exe 파일과 동일한 디렉터리에 있는 Vbc.rsp 파일을 사용 하 여 컴파일하면 하지 않도록 컴파일러에 지시 합니다. Vbc.rsp 파일은 일반적으로 사용 되는 참조 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 어셈블리 및 가져오기는 `System` 및 `Microsoft.VisualBasic` 네임 스페이스입니다. 컴파일러는 암시적으로 System.dll 어셈블리를 참조 하지 않는 한는 `/nostdlib` 옵션을 지정 합니다. `/nostdlib` 옵션 Vbc.rsp 컴파일하거나 System.dll 어셈블리를 자동으로 참조 하지 않도록 컴파일러에 지시 합니다.  
  
> [!NOTE]
>  Mscorlib.dll 및 Microsoft.VisualBasic.dll 어셈블리는 항상 참조 합니다.  
  
 모든 Vbc.exe 컴파일에 포함 되어야 하는 추가 컴파일러 옵션을 지정 하려면 Vbc.rsp 파일을 수정할 수 있습니다 (지정 하는 경우를 제외 하 고는 `/noconfig` 옵션). 자세한 내용은 [@ (지시 파일 지정)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)을 참조하세요.  
  
 컴파일러에 전달 된 옵션으로 처리 된 `vbc` 마지막 명령입니다. 따라서 명령줄에서 모든 옵션은 Vbc.rsp 파일에 동일한 옵션의 설정을 재정의합니다.  
  
> [!NOTE]
>  `/noconfig` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 명령줄에서 컴파일할 때에 사용할 수는 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [/nostdlib (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nostdlib.md)   
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)   
 [@ (지시 파일 지정)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)   
 [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
