---
title: -utf8output (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: 753c92cdf2124ee7fb1b471c7bc543b6db6f3daa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="-utf8output-visual-basic"></a>-utf8output (Visual Basic)
UTF-8 인코딩을 사용하여 컴파일러 출력을 표시합니다.  
  
## <a name="syntax"></a>구문  
  
```  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a>인수  
 `+` &#124; `-`  
 선택 사항입니다. 이 옵션의 기본값은 `-utf8output-`, 즉, 컴파일러 출력에 utf-8 인코딩을 사용 하지 않습니다. 지정 `-utf8output` 지정 하는 것과 같습니다 `-utf8output+`합니다.  
  
## <a name="remarks"></a>설명  
 일부 국제 구성에서 컴파일러 출력을 콘솔에 올바르게 표시할 수 없습니다. 이러한 상황에서 사용 하 여 `-utf8output` 컴파일러 출력을 파일로 리디렉션합니다.  
  
> [!NOTE]
>  `-utf8output` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 명령줄에서 컴파일할 경우에 사용할 수는 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 `In.vb` 표시 하도록 컴파일러에 지시 하 고 utf-8 인코딩을 사용 하 여 출력 합니다.  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)  
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
