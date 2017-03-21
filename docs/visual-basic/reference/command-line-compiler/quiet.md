---
title: "/quiet | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /quiet
- quiet
dev_langs:
- VB
helpviewer_keywords:
- -quiet compiler option [Visual Basic]
- /quiet compiler option [Visual Basic]
- quiet compiler option [Visual Basic]
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
caps.latest.revision: 11
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
ms.openlocfilehash: feafed7464248c38ec70087795a28ead8b8793f3
ms.lasthandoff: 03/13/2017

---
# <a name="quiet"></a>/quiet
컴파일러에서 구문 관련 오류 및 경고에 대한 코드를 표시하지 않도록 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/quiet  
```  
  
## <a name="remarks"></a>주의  
 기본적으로 `/quiet`은 적용되지 않습니다. 컴파일러 구문 관련 오류 또는 경고를 보고, 소스 코드에서 줄도 출력 합니다. 컴파일러 출력을 구문 분석 하는 응용 프로그램을 더 간편 하 게 진단 텍스트만 출력 하도록 컴파일러에 수도 있습니다.  
  
 다음 예에서 `Module1` 없이 컴파일할 때 소스 코드를 포함 하는 오류를 출력 `/quiet`합니다.  
  
```  
Module Module1  
    Sub Main()  
        x()  
    End Sub  
End Module  
```  
  
 출력:  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
 `x`  
  
 `~`  
  
 으로 컴파일된 `/quiet`, 컴파일러는 다음 정보만 출력 합니다.  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
> [!NOTE]
>  `/quiet` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 명령줄에서 컴파일할 때에 사용할 수는 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 `T2.vb` 컴파일러 구문 관련 진단에 대 한 코드를 표시 하지 않습니다.  
  
```  
vbc /quiet t2.vb  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
