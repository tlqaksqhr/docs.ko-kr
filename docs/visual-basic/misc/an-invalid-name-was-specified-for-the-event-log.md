---
title: "이벤트 로그에 대해 잘못된 이름을 지정했습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: b1b158bd-f13f-4371-a8af-31c0e86ae6be
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 76e4082710a6786ec5e743ce606e849637c26512
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="an-invalid-name-was-specified-for-the-event-log"></a>이벤트 로그에 대해 잘못된 이름을 지정했습니다.
이벤트 로그에 대해 잘못된 이름을 지정했습니다. 일반적으로 이름, 빈 파일 이름 또는 너무 긴 파일 이름에 잘못된 문자가 포함되어 발생합니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   지정된 이름이 8자보다 긴 경우 다른 이벤트 로그 이름과 충돌하지 않아야 합니다. 이름이 고유한지 확인할 때 처음 8자만 비교합니다.  
  
-   경로를 제공하는 경우 제대로 구문 분석되어야 합니다.  
  
-   이름에 잘못된 문자가 없는지 확인합니다. `<`, `>`, `:`, `"`, `/`, `\`및 `|`는 파일 이름에 사용할 수 없는 문자입니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 파일 경로의 구문 분석](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)  
 [방법: 파일 이름 바꾸기](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)  
 
