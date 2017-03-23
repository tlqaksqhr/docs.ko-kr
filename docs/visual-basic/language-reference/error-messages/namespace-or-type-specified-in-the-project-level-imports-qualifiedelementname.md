---
title: "Namespace 또는 형식이 프로젝트 수준의 Imports&quot;에 지정 된&lt;qualifiedelementname&gt;&quot; public 멤버가 없거나 또는 찾을 수 없는 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40057
- bc40057
dev_langs:
- VB
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
caps.latest.revision: 10
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
ms.openlocfilehash: 5dae6f92f573a57d0974c860500bc7420f55a94f
ms.lasthandoff: 03/13/2017

---
# <a name="namespace-or-type-specified-in-the-project-level-imports-39ltqualifiedelementnamegt39-doesn39t-contain-any-public-member-or-cannot-be-found"></a>Namespace 또는 형식이 프로젝트 수준의 Imports'에 지정 된&lt;qualifiedelementname&gt;' public 멤버가 없거나 또는 찾을 수 없습니다
Namespace 또는 형식이 프로젝트 수준의 Imports'에 지정 된\<qualifiedelementname > ' public 멤버가 없거나 또는 찾을 수 없습니다. 네임 스페이스 또는 형식 정의 되 고 하나 이상의 공용 멤버에 포함 되어 있는지 확인 합니다. 별칭 이름에는 다른 별칭 포함 되어 있지 않은지 확인 하십시오.  
  
 찾을 수 없거나 또는 정의 하지 않는 포함 하는 요소를 지정 하는 프로젝트의 가져오기 속성 `Public` 멤버입니다.  
  
 A *요소가 포함 된* 네임 스페이스, 클래스, 구조체, 모듈, 인터페이스 또는 열거형이 될 수 있습니다. 포함 하는 요소는 변수, 프로시저 또는 다른 요소를 포함 하는 같은 멤버를 포함합니다.  
  
 가져오기의 목적은 한정 하지 않고도 코드 네임 스페이스 또는 형식 멤버에 액세스를 허용 하는 것입니다. 프로젝트의 네임 스페이스 또는 형식에 대 한 참조를 추가 해야 할 수도 있습니다. 자세한 내용은 "포함 된 요소를 가져오는"의 참조 [선언 된 요소에 대 한 참조](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)합니다.  
  
 컴파일러는 포함 하는 지정 된 요소를 찾을 수 없는 경우 사용 하는 참조를 확인할 수 없습니다. 요소를 찾습니다 있지만 요소는 노출 하지 않는 경우 `Public` 멤버에 다음 참조 없이 성공할 수 있습니다. 두 경우 모두 요소를 가져오는 의미가 없습니다.  
  
 사용 된 **프로젝트 디자이너** 가져올 요소를 지정할 수 있습니다. 사용 하는 **가져온 네임 스페이스** 의 섹션은 **참조** 페이지. 에 가져올 수 있습니다는 **프로젝트 디자이너** 두 번 클릭 하는 **My Project** 아이콘 **솔루션 탐색기**합니다.  
  
 **오류 ID:** BC40057  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  열기는 **프로젝트 디자이너** 로 전환 하 고는 **참조** 페이지입니다.  
  
2.  에 **가져온 네임 스페이스** 섹션를 포함 하는 요소가 프로젝트에서 액세스할 수 있는지 확인 합니다.  
  
3.  포함 하는 요소를 통해 노출 된 하나 이상의 확인 `Public` 멤버입니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로젝트 디자이너, 참조 페이지(Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)   
 [NIB 하는 방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [공개](../../../visual-basic/language-reference/modifiers/public.md)   
 [Visual Basic의 네임 스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [선언된 요소 참조](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
