---
title: /nologo(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -nologo compiler option [Visual Basic]
- banners [Visual Basic], suppressing startup
- nologo compiler option [Visual Basic]
- /nologo compiler option [Visual Basic]
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3c2c7e7a111a3763d7463f67c2d984955da33bbf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="nologo-visual-basic"></a>/nologo(Visual Basic)
컴파일 시 저작권 배너 및 정보 메시지를 표시를 하지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
/nologo  
```  
  
## <a name="remarks"></a>설명  
 지정 하는 경우 `/nologo`, 컴파일러 저작권 배너를 표시 하지 않습니다. 기본적으로 `/nologo`은 적용되지 않습니다.  
  
> [!NOTE]
>  `/nologo` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 명령줄에서 컴파일할 경우에 사용할 수는 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 `T2.vb` 를 저작권 배너를 표시 하지 않습니다.  
  
```  
vbc /nologo t2.vb  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md)  
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
