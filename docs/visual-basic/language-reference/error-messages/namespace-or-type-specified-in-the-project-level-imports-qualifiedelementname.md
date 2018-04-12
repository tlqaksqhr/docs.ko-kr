---
title: Namespace 또는 프로젝트 수준의 Imports &#39;에 지정 된 형식 &lt;qualifiedelementname&gt;&#39; 대상이 &#39; t public 멤버가 또는 형식을 찾을 수 없음
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40057
- bc40057
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0d0a164562524af239b3b130f681dbc6eff23814
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="namespace-or-type-specified-in-the-project-level-imports-39ltqualifiedelementnamegt39-doesn39t-contain-any-public-member-or-cannot-be-found"></a>Namespace 또는 프로젝트 수준의 Imports &#39;에 지정 된 형식 &lt;qualifiedelementname&gt;&#39; 대상이 &#39; t public 멤버가 또는 형식을 찾을 수 없음
프로젝트 수준의 Imports'에 지정 된 Namespace 또는 형식을\<qualifiedelementname >' public 멤버가 없거나 찾을 수 없습니다. 해당 네임 스페이스 또는 형식 정의 되어 있고 하나 이상의 public 멤버를 포함 합니다. 별칭 이름에는 다른 별칭 포함 되어 있지 않은지 확인 하십시오.  
  
 프로젝트의 가져오기 속성 지정 하거나 찾을 수 없거나 정의 하지 않는 포함 하는 요소 `Public` 멤버입니다.  
  
 A *요소가 포함 된* 네임 스페이스, 클래스, 구조체, 모듈, 인터페이스 또는 열거형 일 수 있습니다. 포함 하는 요소, 변수, 프로시저 또는 다른 요소를 포함 하는 같은 멤버를 포함합니다.  
  
 가져오기의 목적은 한정 하지 않고 코드 네임 스페이스 또는 형식 멤버에 액세스를 허용 하도록 합니다. 프로젝트의 네임 스페이스 또는 형식에 대 한 참조를 추가 해야 할 수도 있습니다. 자세한 내용은 "포함 된 요소 가져오기"를 참조 [선언 된 요소에 대 한 참조](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)합니다.  
  
 컴파일러에서 지정 된 포함 하는 요소를 찾을 수 없는 경우을 사용 하는 참조를 확인할 수 없습니다. 요소를 찾습니다 있지만 요소는 노출 하지 않는 경우 `Public` 멤버 다음 참조가 없는 성공할 수 있습니다. 두 경우 모두에서 요소를 가져오는 의미가 없습니다.  
  
 사용 된 **프로젝트 디자이너** 가져올 요소를 지정할 수 있습니다. 사용 하 여는 **가져온 네임 스페이스** 의 섹션은 **참조** 페이지. 에 가져올 수 있습니다는 **프로젝트 디자이너** 두 번 클릭 하 여는 **My Project** 아이콘 **솔루션 탐색기**합니다.  
  
 **오류 ID:** BC40057  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  열기는 **프로젝트 디자이너** 로 전환 하 고는 **참조** 페이지.  
  
2.  에 **가져온 네임 스페이스** 섹션에서 요소가 포함 된 프로젝트에서 액세스할 수 있는지 확인 합니다.  
  
3.  포함 하는 요소가 하나 이상를 통해 노출 된 확인 `Public` 멤버입니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로젝트 디자이너, 참조 페이지(Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)  
 [프로젝트 및 솔루션 속성 관리](/visualstudio/ide/managing-project-and-solution-properties)  
 [공용](../../../visual-basic/language-reference/modifiers/public.md)  
 [Visual Basic의 네임 스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [선언된 요소 참조](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
