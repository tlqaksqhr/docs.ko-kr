---
title: -win32resource
ms.date: 03/13/2018
f1_keywords:
- -win32resource
- win32resource
helpviewer_keywords:
- /win32resource compiler option [Visual Basic]
- -win32resource compiler option [Visual Basic]
- win32resource compiler option [Visual Basic]
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ac495e10be2ec1534dc9d9081aef369773d93e17
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42933053"
---
# <a name="-win32resource"></a>-win32resource
출력 파일에 Win32 리소스 파일을 삽입합니다.  
  
## <a name="syntax"></a>구문  
  
```  
-win32resource:filename  
```  
  
## <a name="arguments"></a>인수  
 `filename`  
 출력 파일에 추가 하는 리소스 파일의 이름입니다. 파일 이름을 따옴표로 묶습니다 ("")에 공백이 있는 경우.  
  
## <a name="remarks"></a>설명  
 Microsoft Windows 리소스 컴파일러 (RC) 사용 하 여 Win32 리소스 파일을 만들 수 있습니다.  
  
 Win32 리소스 버전을 포함할 수 있습니다 또는 도움이 되는 비트맵 (아이콘) 정보에서 응용 프로그램을 식별 **파일 탐색기**합니다. 지정 하지 않는 경우 `-win32resource`, 컴파일러에서 어셈블리 버전을 기반으로 하는 버전 정보를 생성 합니다. 합니다 `-win32resource` 고 `-win32icon` 옵션은 상호 배타적입니다.  
  
 참조 [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) 참조를 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 리소스 파일 또는 [-리소스 (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) 연결 하는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 리소스 파일입니다.  
  
> [!NOTE]
>  `-win32resource` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 있는 명령줄에서 컴파일할 경우에 사용할 수 있는 것입니다.  
  
## <a name="example"></a>예  
 다음 코드 컴파일을 `In.vb` Win32 리소스 파일, 연결 및 `Rf.res`:  
  
```console  
vbc -win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)  
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
