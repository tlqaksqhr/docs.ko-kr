---
title: -참조 (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb5d3b4c50a9c22880bdcc8406835cf51481e3cd
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43003127"
---
# <a name="-reference-visual-basic"></a>-참조 (Visual Basic)
컴파일러가 지정된 된 어셈블리의 형식 정보 현재 컴파일 중인 프로젝트에서 사용할 수 있게 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
-reference:fileList  
' -or-  
-r:fileList  
```  
  
## <a name="arguments"></a>인수  
  
|용어|정의|  
|---|---|  
|`fileList`|필수. 쉼표로 구분된 어셈블리 파일 이름 목록입니다. 파일 이름에 공백이 있으면 이름을 따옴표로 묶습니다.|  
  
## <a name="remarks"></a>설명  
 가져오는 파일 어셈블리 메타 데이터를 포함 해야 합니다. Public 형식만 어셈블리 외부에 표시 됩니다. 합니다 [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) 옵션 모듈에서 메타 데이터를 가져옵니다.  
  
 어셈블리 (어셈블리 A) 참조 하는 경우는 다른 어셈블리 (어셈블리 B)를 참조 하는 경우 어셈블리 B를 참조 해야 합니다.  
  
-   어셈블리 A의 형식은 형식에서 상속되거나 어셈블리 B의 인터페이스를 구현합니다.  
  
-   어셈블리 B의 반환 형식이나 매개 변수 형식을 사용하는 필드, 속성, 이벤트 또는 메서드가 호출됩니다.  
  
 사용 하 여 [-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) 어셈블리 참조 중 하나 이상이 있는 디렉터리를 지정 합니다.  
  
 어셈블리 (모듈 아님)의 형식을 인식할 수 컴파일러의 경우 해당 형식을 확인할 강제 해야 합니다. 이 수행할 수 있는 방법의 예로 형식의 인스턴스를 정의 하는 것입니다. 다른 방법으로 컴파일러에 대 한 어셈블리의 형식 이름을 확인 하기 위해 사용할 수 있습니다. 예를 들어, 어셈블리의 형식에서 상속 하는 경우 형식 이름에 알려집니다 컴파일러.  
  
 참조 일반적으로 Vbc.rsp 지시 파일이 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 어셈블리의 경우 기본적으로 사용 됩니다. 사용 하 여 `-noconfig` Vbc.rsp 사용 하도록 컴파일러에 원하지 않는 경우.  
  
 `-reference`의 약식은 `/r`입니다.  
  
## <a name="example"></a>예제  
 다음 명령은 소스 파일을 컴파일하 `Input.vb` 참조 어셈블리 및 `Metad1.dll` 및 `Metad2.dll` 되려면 `Out.exe`합니다.  
  
```console
vbc -reference:metad1.dll,metad2.dll -out:out.exe input.vb  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [공용](../../../visual-basic/language-reference/modifiers/public.md)  
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
