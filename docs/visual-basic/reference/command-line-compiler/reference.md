---
title: "/reference (Visual Basic) | Microsoft 문서"
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
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
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
ms.openlocfilehash: 12344dba82131d6be2c32127de287a6e9e3efa39
ms.lasthandoff: 03/13/2017

---
# <a name="reference-visual-basic"></a>/reference(Visual Basic)
컴파일러가 지정 된 어셈블리의 형식 정보 현재 컴파일 중인 프로젝트에서 사용할 수 있게 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/reference:fileList  
' -or-  
/r:fileList  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`fileList`|필수 요소. 어셈블리 파일 이름의 쉼표로 구분 된 목록입니다. 파일 이름에 공백이 있으면 이름을 따옴표로 묶습니다.|  
  
## <a name="remarks"></a>설명  
 가져오는 파일 어셈블리 메타 데이터를 포함 해야 합니다. Public 형식만 어셈블리 외부에 표시 됩니다. [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) 옵션 모듈에서 메타 데이터를 가져옵니다.  
  
 어셈블리 (어셈블리 A)를 참조 하는 경우 그 자체가 다른 어셈블리 (어셈블리 B)를 참조 하는 경우를 어셈블리 B를 참조 해야 합니다.  
  
-   어셈블리 A에서에서 형식을 형식에서 상속 되거나 어셈블리 B의 인터페이스 구현  
  
-   필드, 속성, 이벤트 또는 어셈블리 B의 반환 형식이 나 매개 변수 형식의 변수가 있는 메서드가 호출 됩니다.  
  
 사용 하 여 [/libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) 어셈블리 참조 중 하나 이상이 있는 디렉터리를 지정할 수 있습니다.  
  
 (모듈 아님) 어셈블리에서 형식을 인식 하려면 컴파일러의 경우 해당 형식을 확인할 강제 해야 합니다. 이 수행할 수 있는 방법 중 한 가지 예는 형식의 인스턴스를 정의 하는 것입니다. 다른 방법으로 컴파일러에 대 한 어셈블리에서 형식 이름을 확인할 수 있습니다. 예를 들어, 어셈블리의 형식에서 상속 하는 경우 형식 이름에 알려집니다 컴파일러입니다.  
  
 참조는 일반적으로 사용은 Vbc.rsp 지시 파일을 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 어셈블리의 경우 기본적으로 사용 됩니다. 사용 하 여 `/noconfig` Vbc.rsp를 사용 하도록 컴파일러에 원하지 않는 경우.  
  
 약식 `/reference` 는 `/r`합니다.  
  
## <a name="example"></a>예제  
 다음 코드 컴파일하고 소스 파일 I`nput.vb` M에서 어셈블리를 참조 하 고`etad1.dll` 및 M`etad2.dll` O 생성할`ut.exe`합니다.  
  
```  
vbc /reference:metad1.dll,metad2.dll /out:out.exe input.vb  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)   
 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)   
 [공개](../../../visual-basic/language-reference/modifiers/public.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
