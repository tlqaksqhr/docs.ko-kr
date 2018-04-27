---
title: Visual Basic 제한 사항
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- limits
- limitations [Visual Basic]
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d06b743996969dcd7fc022bbb8ab625f3a151137
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="visual-basic-limitations"></a>Visual Basic 제한 사항
이전 버전의 Visual Basic 코드에서 변수 이름, 모듈, 모듈 크기에 허용 되는 변수 수 길이 같은 제한이 있었습니다. Visual Basic.net에서는 이러한 제한이 완화 되었습니다, 훨씬 자유롭게 작성 하 고 정렬 코드를 제공 합니다.  
  
 실제 제한 되 컴파일 시간 고려 사항에는 런타임에 메모리 보다 더 종속. 사용, 여러 클래스와 모듈 큰 응용 프로그램을 나누는 하는 경우에 내부 Visual Basic 제한 사항이 발생할 확률이 거의 없습니다.  
  
 극단적인 경우에 발생할 수 있는 몇 가지 제한 사항이 다음과 같습니다.  
  
-   **이름 길이입니다.** 모든 선언 된 프로그래밍 요소 이름에 대 한 문자의 최대 수가입니다. 이 최대 요소 이름 한정 된 경우 전체 한정 문자열에 적용 됩니다. 참조 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.  
  
-   **줄 길이입니다.** 최대 65, 535 자 소스 코드의 실제 줄에 있습니다. 논리 소스 코드 줄은 줄 연속 문자를 사용 하는 경우에 길어질 수 있습니다. 참조 [하는 방법: 코드에서 문 분리 및 결합](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)합니다.  
  
-   **배열 차원이 있습니다.** 차원 배열에 선언할 수 있는 최대 수가입니다. 배열 요소를 지정 하는 데 사용할 수는 인덱스 수를 제한 합니다. 참조 [차원 Visual Basic의 배열](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md)합니다.  
  
-   **문자열 길이입니다.** 단일 문자열에 저장할 수는 유니코드 문자의 최대 수가입니다. 참조 [문자열 데이터 형식](../../../visual-basic/language-reference/data-types/string-data-type.md)합니다.  
  
-   **환경 문자열 길이입니다.** 명령줄 인수로 사용 되는 모든 환경 문자열에 대 한 32768 문자의 최대가 있습니다. 이 모든 플랫폼에 대 한 제한이 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로그램 구조 및 코드 규칙](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [Visual Basic 명명 규칙](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
