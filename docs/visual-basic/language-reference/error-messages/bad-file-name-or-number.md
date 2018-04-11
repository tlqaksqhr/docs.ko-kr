---
title: 파일 이름 또는 번호가 잘못되었습니다.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID52
ms.assetid: d0e96aea-7621-48f6-a78b-5d37d18aaa4e
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3d7c8bae3df0e75a1c4f9afacdff681a553503d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="bad-file-name-or-number"></a>파일 이름 또는 번호가 잘못되었습니다.
지정한 파일에 액세스 하는 동안 오류가 발생 했습니다. 이 오류의 가능한 원인:  
  
-   문에서 참조에 지정 되지 않은 파일 이름 또는 숫자로 파일에는 `FileOpen` 문 또는 하에 지정 된는 `FileOpen` 하지만 된 문이 이후에 닫힙니다.  
  
-   문에서 숫자 파일 번호의 범위를 벗어난를 사용 하 여 파일 참조 합니다.  
  
-   문에서 파일 이름 또는 유효 하지 않은 숫자를 참조 합니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  파일 이름 지정은 확인 된 `FileOpen` 문. 호출 된 경우에 `FileClose` 문 인수 없이 있습니다 닫힐 수 열려 있는 모든 파일.  
  
2.  코드 생성 하는 경우 파일 번호 알고리즘 방식으로,은 사용할 수 있는지 확인 합니다.  
  
3.  운영 체제 규칙을 준수 하는지 확인 하려면 파일 이름을 확인 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>  
 [Visual Basic 명명 규칙](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
