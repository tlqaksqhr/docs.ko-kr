---
title: "/win32resource | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /win32resource
- win32resource
dev_langs:
- VB
helpviewer_keywords:
- /win32resource compiler option [Visual Basic]
- -win32resource compiler option [Visual Basic]
- win32resource compiler option [Visual Basic]
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
caps.latest.revision: 13
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
ms.openlocfilehash: 37902590d5a05d7fdb2a521f3c3de2ad88c2c502
ms.lasthandoff: 03/13/2017

---
# <a name="win32resource"></a>/win32resource
출력 파일에 Win32 리소스 파일을 삽입합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/win32resource:filename  
```  
  
## <a name="arguments"></a>인수  
 `filename`  
 출력 파일에 추가 하는 리소스 파일의 이름입니다. 파일 이름을 따옴표로 묶습니다 ("")에 공백이 있는 경우.  
  
## <a name="remarks"></a>주의  
 Microsoft Windows 리소스 컴파일러 (RC)으로 Win32 리소스 파일을 만들 수 있습니다.  
  
 Win32 리소스 버전을 포함할 수의 응용 프로그램을 식별 하는 데 도움이 되는 비트맵 (아이콘) 정보 또는 **파일 탐색기**합니다. 지정 하지 않으면 `/win32resource`, 컴파일러는 어셈블리 버전에 따라 버전 정보를 생성 합니다. `/win32resource` 및 `/win32icon` 옵션은 함께 사용할 수 없습니다.  
  
 참조 [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) 참조에는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 리소스 파일 또는 [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) 연결 하는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 리소스 파일입니다.  
  
> [!NOTE]
>  `/win32resource` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 명령줄에서 컴파일할 때에 사용할 수는 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 `In.vb` Win32 리소스 파일을 첨부 `Rf.res`:  
  
```  
vbc /win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
