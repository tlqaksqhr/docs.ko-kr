---
title: "클래스 자동화를 지원 하지 않거나 필요한 인터페이스를 지원 하지 않는 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID430
dev_langs:
- VB
ms.assetid: d985bb7e-e48e-443e-86f2-ddb86758757c
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
ms.openlocfilehash: a5bdce085c676f5c9c20932939486e879bb13a36
ms.lasthandoff: 03/13/2017

---
# <a name="class-does-not-support-automation-or-does-not-support-expected-interface"></a>클래스가 자동화를 지원하지 않거나 필요한 인터페이스를 지원하지 않습니다.
`GetObject` 또는 `CreateObject` 함수 호출에서 지정한 클래스가 프로그래밍 기능 인터페이스를 표시하지 않았거나 프로젝트를 .dll과 .exe 간에 변경했습니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  개체를 만든 응용 프로그램 설명서를 참조하여 이 개체 클래스에서 자동화를 사용하는 경우의 제한을 확인합니다.  
  
2.  프로젝트를 .dll과 .exe 간에 변경한 경우에는 이전 .dll 또는 .exe의 등록을 수동으로 취소해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [오류 형식](../../../visual-basic/programming-guide/language-features/error-types.md)   
 [의견 보내기](https://docs.microsoft.com/visualstudio/ide/talk-to-us)
