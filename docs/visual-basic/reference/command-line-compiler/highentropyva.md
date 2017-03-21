---
title: "/highentropyva (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
caps.latest.revision: 12
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
ms.openlocfilehash: 34987930b3afd6d95d12190172a5a5e512106f8a
ms.lasthandoff: 03/13/2017

---
# <a name="highentropyva-visual-basic"></a>/highentropyva(Visual Basic)
나타냅니다로 표시 된 실행 파일이 나 64 비트 실행 파일 여부는 [/platform:anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) 컴파일러 옵션은 높은 엔트로피 주소 공간 레이아웃 불규칙화 (ASLR)를 지원 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/highentropyva[+ | -]  
```  
  
## <a name="arguments"></a>인수  
 `+` &#124; `-`  
 선택적 요소. 기본적으로 해제 되어 옵션 또는 지정 하는 경우 `/highentropyva-`합니다. 지정 하는 경우에 옵션은 `/highentropyva` 또는 `/highentropyva+`합니다.  
  
## <a name="remarks"></a>주의  
 이 옵션을 지정 하는 경우에 Windows 커널의 호환 되는 버전 커널 ASLR의 일부로 프로세스의 주소 공간 레이아웃을 임의 때 더 높은 수준의 엔트로피를 사용할 수 있습니다. 커널 더 높은 수준의 엔트로피를 사용 하면 스택 및 힙과 같은 메모리 영역에 더 많은 주소를 할당할 수 있습니다. 따라서 특정 메모리 영역의 위치를 추측하기 어려워집니다.  
  
 옵션을 설정 하면 대상 실행 파일 및 모든 모듈에 대 그에 따라 달라 지는 수 있어야 64 비트 프로세스로 실행 되 고 이러한 모듈은 4gb (기가바이트) 보다 큰 포인터 값을 처리 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
