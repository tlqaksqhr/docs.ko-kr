---
title: "/langversion (Visual Basic) | Microsoft 문서"
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
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
caps.latest.revision: 8
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
ms.openlocfilehash: 9970df0c9babc368210169fae0490b423d77f40d
ms.lasthandoff: 03/13/2017

---
# <a name="langversion-visual-basic"></a>/langversion(Visual Basic)
컴파일러가 지정 된 Visual Basic 언어 버전에 포함 된 구문만 허용 하도록 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/langversion:version  
```  
  
## <a name="arguments"></a>인수  
 `version`  
 필수 요소. 컴파일 중에 사용할 언어 버전입니다. 사용 가능한 값은 `9`, `9.0`, `10`, 및 `10.0`합니다.  
  
## <a name="remarks"></a>주의  
 `/langversion` 옵션은 컴파일러에서 허용 되는 구문을 지정 합니다. 예를 들어 언어 버전이 9.0 인지를 지정 하면 컴파일러 구문으로 10.0 버전에만 유효 하 고 나중에 대 한 오류를 생성 합니다.  
  
 해당 대상 서로 다른 버전의.NET Framework 응용 프로그램을 개발 하는 경우이 옵션을 사용할 수 있습니다. 예를 들어.NET Framework 3.5를 대상으로 하는 언어 버전 10.0에서에서 구문을 사용 하지 않으면이 옵션을 사용할 수 있습니다.  
  
 설정할 수 있습니다 `/langversion` 직접 명령줄을 사용 해야만 합니다. 자세한 내용은 [특정 대상 .NET Framework 버전 지정](https://docs.microsoft.com/visualstudio/ide/targeting-a-specific-dotnet-framework-version)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 코드에서는 `sample.vb` Visual Basic 9.0에 대 한 합니다.  
  
```  
vbc /langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [특정 대상 .NET Framework 버전 지정](https://docs.microsoft.com/visualstudio/ide/targeting-a-specific-dotnet-framework-version)
