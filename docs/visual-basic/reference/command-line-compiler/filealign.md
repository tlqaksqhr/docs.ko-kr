---
title: "/filealign | Microsoft 문서"
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
- sections compiler option [Visual Basic]
- alignment compiler option [Visual Basic]
- -filealign compiler option [Visual Basic]
- section alignment
- /filealign compiler option [Visual Basic]
- filealign compiler option [Visual Basic]
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
caps.latest.revision: 14
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
ms.openlocfilehash: 18d5c3e327e2e41f4786eda6c3e981125f87389d
ms.lasthandoff: 03/13/2017

---
# <a name="filealign"></a>/filealign
출력 파일의 섹션에 맞출 위치를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/filealign:number  
```  
  
## <a name="arguments"></a>인수  
 `number`  
 필수 요소. 출력 파일의 섹션 맞춤을 지정 하는 값입니다. 유효한 값에는 512, 1024, 2048, 4096, 8192은입니다. 이러한 값은 바이트입니다.  
  
## <a name="remarks"></a>설명  
 사용할 수는 `/filealign` 출력 파일의 섹션 맞춤을 지정 하는 옵션입니다. 섹션은 코드 또는 데이터를 포함 하는 PE (이식 가능) 파일의 연속 된 메모리 블록입니다. `/filealign` 옵션으로 비표준 맞춤으로 응용 프로그램을 컴파일할 수 있습니다; 대부분의 개발자가이 옵션을 사용할 필요가 없습니다.  
  
 각 섹션의 배수인 경계에 정렬 되는 `/filealign` 값입니다. 고정 기본값이 없습니다. 경우 `/filealign` 를 지정 하지 않으면 컴파일러는 컴파일 타임에 기본값을 선택 합니다.  
  
 섹션 크기를 지정 하 여 출력 파일의 크기를 변경할 수 있습니다. 섹션 크기를 수정 하는 것은 소형 장치에서 실행 되는 프로그램에 유용할 수 있습니다.  
  
> [!NOTE]
>  `/filealign` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 명령줄에서 컴파일할 때에 사용할 수는 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
