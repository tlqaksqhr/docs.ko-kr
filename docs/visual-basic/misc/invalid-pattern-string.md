---
title: "잘못된 패턴 문자열"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: ec1aecdb-5339-4a93-be71-eec56b1d7438
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f824a5844d6d2b365358030119826266a4b42ef3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="invalid-pattern-string"></a>잘못된 패턴 문자열
검색의 `Like` 작업에서 지정된 패턴 문자열이 잘못되었습니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  목록 식에 유효한 문자를 검토합니다.  
  
2.  패턴 범위에서 `[a-z]`처럼 범위 시작 문자가 범위 끝 문자보다 작은지 확인합니다.  
  
3.  패턴 범위에서 `[a--z]`처럼 여러 하이픈이 서로 인접하지 않는지 확인합니다.  
  
4.  닫는 대괄호를 사용하여 패턴 범위를 종료합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Like 연산자](../../visual-basic/language-reference/operators/like-operator.md)
