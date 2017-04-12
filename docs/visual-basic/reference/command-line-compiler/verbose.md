---
title: "/verbose | Microsoft 문서"
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
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
caps.latest.revision: 11
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
ms.openlocfilehash: f6d8a8b914ccffff72128bbc907482816b95b8a0
ms.lasthandoff: 03/13/2017

---
# <a name="verbose"></a>/verbose
상태 및 오류에 대 한 자세한 정보 메시지를 생성 하는 컴파일러가 선택 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/verbose[+ | -]  
```  
  
## <a name="arguments"></a>인수  
 `+` &#124; `-`  
 선택적 요소. 지정 `/verbose` 지정 하는 것과 같습니다 `/verbose+`, 자세한 정보 메시지를 내보낼 컴파일러가 합니다. 이 옵션의 기본값은 `/verbose-`합니다.  
  
## <a name="remarks"></a>주의  
 `/verbose` 옵션은 컴파일러에서 생성 한 오류의 총 수에 대 한 정보를 표시 합니다. 모듈에 의해 로드 되 고 있는 어셈블리를 보고 하 고 현재 컴파일 중인 파일을 표시 합니다.  
  
> [!NOTE]
>  `/verbose` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 명령줄에서 컴파일할 때에 사용할 수는 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 `In.vb` 를 자세한 상태 정보를 표시 하도록 컴파일러에 지시 합니다.  
  
```  
vbc /verbose in.vb  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
