---
title: "Visual Basic 제한 사항 | Microsoft 문서"
ms.custom: 
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
- limits
- limitations, Visual Basic
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
caps.latest.revision: 14
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
ms.openlocfilehash: d556b045b4ebae6ba24c0571a6cb7e5337c6a8f2
ms.lasthandoff: 03/13/2017

---
# <a name="visual-basic-limitations"></a>Visual Basic 제한 사항
이전 버전의 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 제한 사항이 있었습니다 변수 이름의 길이 등의 코드 모듈 및 모듈 크기에 허용 되는 변수의 수입니다. [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)], 이러한 제한이 완화 되었습니다, 작성 하 고 코드를 정렬 한 큰 자유를 제공 합니다.  
  
 실제 제한은 종속 더 보다 런타임에 메모리에서 컴파일 타임 고려 사항입니다. 거의 발생할 가능성을 내부는 신중한 프로그래밍 관행을 사용 하 고 큰 응용 프로그램을 여러 클래스 및 모듈을 나누는 경우 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 제한 합니다.  
  
 다음은 극단적인 경우에 발생할 수 있는 몇 가지 제한 사항이 있습니다.  
  
-   **이름 길이입니다.** 선언 된 모든 프로그래밍 요소 이름에 대 한 문자의 최대 수가입니다. 이 최대 요소 이름을 정규화 하는 경우 전체 정규화 문자열에 적용 합니다. 참조 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.  
  
-   **줄 길이입니다.** 소스 코드의 실제 줄에서 65535 자가 있습니다. 논리적 소스 코드 줄은 줄 연속 문자를 사용 하는 경우에 길어질 수 있습니다. 참조 [하는 방법: 코드에서 문 분리 및 결합](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)합니다.  
  
-   **배열 차원입니다.** 차원 배열에 선언할 수 있는 최대 수가입니다. 배열 요소를 지정 하는 데 사용할 수는 인덱스 수를 제한 합니다. 참조 [Visual Basic의 차원 배열](../../../visual-basic/programming-guide/language-features/arrays/array-dimensions.md)합니다.  
  
-   **문자열 길이입니다.** 단일 문자열에 저장할 수는 유니코드 문자의 최대 수가입니다. 참조 [문자열 데이터 형식](../../../visual-basic/language-reference/data-types/string-data-type.md)합니다.  
  
-   **환경 문자열 길이입니다.** 최대 명령줄 인수로 사용 되는 모든 환경 문자열에 대 한 32, 768 자의 있습니다. 이 모든 플랫폼에 대 한 제한이 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로그램 구조 및 코드 규칙](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)   
 [Visual Basic 명명 규칙](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)
