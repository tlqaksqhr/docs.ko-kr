---
title: "/baseaddress | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /baseaddress
- baseaddress
dev_langs:
- VB
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
caps.latest.revision: 16
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
ms.openlocfilehash: 527a7c348583498f46ee094ef9b9eec9abf1bcd0
ms.lasthandoff: 03/13/2017

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
|`address`|필수 요소. DLL에 대 한 기본 주소입니다. 이 주소는&16; 진수 숫자로 지정 되어야 합니다.|  
  
## <a name="remarks"></a>주의  
 DLL에 대 한 기본 기준 주소 설정 되는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]합니다.  
  
 이 주소의 하위 순서 단어는 반올림 됩니다. 예를 들어 0x11110001을 지정 하면 0x11110000 반올림 됩니다.  
  
 DLL에 대 한 서명 프로세스를 완료 하려면 사용 된 `–R` 강력한 이름 도구 (Sn.exe)의 옵션입니다.  
  
 대상 DLL이 아닌 경우이 옵션은 무시 됩니다.  
  
|Visual Studio IDE에서 /baseaddress를 설정 하려면|  
|---|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다. 에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다. 자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.<br />2.  클릭 하 고 **컴파일** 탭 합니다.<br />3.  **고급**을 클릭합니다.<br />4.  값을 수정 된 **DLL 기준 주소:** 상자입니다. **참고:** 는 **DLL 기준 주소:** 상자는 읽기 전용 대상 DLL이 아니면 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Sn.exe (강력한 이름 도구)](https://msdn.microsoft.com/library/k5b5tt23)
