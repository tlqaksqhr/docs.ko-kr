---
title: /baseaddress
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- /baseaddress
- baseaddress
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1ad39acdec92667fbb0848a1c64c567b504dcb67
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="baseaddress"></a>/baseaddress
DLL을 만들 때 기본 기준 주소를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/baseaddress:address  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`address`|필수. DLL의 기준 주소입니다. 이 주소는 16 진수 숫자로 지정 되어야 합니다.|  
  
## <a name="remarks"></a>설명  
 DLL에 대 한 기본 기준 주소 설정한는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]합니다.  
  
 주의이 주소의 하위 단어 반올림 됩니다. 예를 들어 0x11110001를 지정 하면 0x11110000 반올림 됩니다.  
  
 DLL에 대 한 서명 프로세스를 완료 하려면 사용 된 `–R` 강력한 이름 도구 (Sn.exe)의 옵션입니다.  
  
 대상 DLL이 아닌 경우이 옵션은 무시 됩니다.  
  
|/Baseaddress Visual Studio IDE에서 설정 하려면|  
|---|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. **프로젝트** 메뉴에서 **속성**을 클릭합니다. <br />2.  **컴파일** 탭을 클릭합니다.<br />3.  **고급**을 클릭합니다.<br />4.  값을 수정 된 **DLL 기준 주소:** 상자입니다. **참고:** 는 **DLL 기준 주소:** 대상 DLL이 아니면 부분은 읽기 전용입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Sn.exe (강력한 이름 도구)] [Sn.exe (강력한 이름 도구)](../../../framework/tools/sn-exe-strong-name-tool.md))
