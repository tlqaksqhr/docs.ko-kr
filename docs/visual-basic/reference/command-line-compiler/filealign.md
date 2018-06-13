---
title: -filealign
ms.date: 03/10/2018
helpviewer_keywords:
- sections compiler option [Visual Basic]
- alignment compiler option [Visual Basic]
- -filealign compiler option [Visual Basic]
- section alignment
- /filealign compiler option [Visual Basic]
- filealign compiler option [Visual Basic]
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf9c854060e5254cedc6c1004ac3e4f25fbdbbd8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650669"
---
# <a name="-filealign"></a>-filealign
출력 파일의 섹션에 맞출 위치를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
-filealign:number  
```  
  
## <a name="arguments"></a>인수  
 `number`  
 필수. 출력 파일에서 섹션 맞춤을 지정 하는 값입니다. 유효한 값은 512, 1024, 2048, 4096 및 8192입니다. 이러한 값은 바이트 단위입니다.  
  
## <a name="remarks"></a>설명  
 사용할 수는 `-filealign` 출력 파일에서 섹션 맞춤을 지정 하는 옵션입니다. 섹션은 코드 또는 데이터를 포함 하는 PE (이식 가능) 파일의 연속 된 메모리의 블록. `-filealign` 를 옵션 비표준 맞춤으로 응용 프로그램을 컴파일할 수 있습니다. 대부분의 개발자가이 옵션을 사용할 필요가 없습니다.  
  
 각 섹션의 배수인 경계에 정렬 되는 `-filealign` 값입니다. 고정된 기본값이 없습니다. 경우 `-filealign` 를 지정 하지 않으면 컴파일러는 컴파일 타임에 기본값을 선택 합니다.  
  
 섹션 크기를 지정 하 여 출력 파일의 크기를 변경할 수 있습니다. 섹션 크기를 수정하면 더 작은 장치에서 실행되는 프로그램에 유용할 수 있습니다.  
  
> [!NOTE]
>  `-filealign` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 명령줄에서 컴파일할 경우에 사용할 수는 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)
