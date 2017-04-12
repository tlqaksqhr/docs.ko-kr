---
title: "/utf8output (Visual Basic) | Microsoft 문서"
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
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
caps.latest.revision: 11
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
ms.openlocfilehash: 89f41527703df781f32015f386bf87c1383d9769
ms.lasthandoff: 03/13/2017

---
# <a name="utf8output-visual-basic"></a>/utf8output(Visual Basic)
UTF-8 인코딩을 사용하여 컴파일러 출력을 표시합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/utf8output[+ | -]  
```  
  
## <a name="arguments"></a>인수  
 `+` &#124; `-`  
 선택적 요소. 이 옵션의 기본값은 `/utf8output-`, 즉, 컴파일러 출력에 utf-8 인코딩을 사용 하지 않습니다. 지정 `/utf8output` 지정 하는 것과 같습니다 `/utf8output+`합니다.  
  
## <a name="remarks"></a>설명  
 일부 국가별 구성 컴파일러 출력 콘솔에 올바르게 표시할 수 없습니다. 이러한 상황에서 사용 하 여 `/utf8output` 컴파일러 출력 파일을 리디렉션합니다.  
  
> [!NOTE]
>  `/utf8output` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 명령줄에서 컴파일할 때에 사용할 수는 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 `In.vb` 표시 하도록 컴파일러에 지시 하 고 utf-8 인코딩을 사용 하 여 출력 합니다.  
  
```  
vbc /utf8output in.vb  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
