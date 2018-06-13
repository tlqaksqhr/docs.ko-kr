---
title: 가져오기에 지정 된 Namespace 또는 형식을 &#39; &lt;qualifiedelementname&gt; &#39; 대상이&#39;t public 멤버가 또는 형식을 찾을 수 없음
ms.date: 07/20/2015
f1_keywords:
- bc40056
- vbc40056
helpviewer_keywords:
- BC40056
ms.assetid: b59f5754-444f-4378-9272-9678b437e84a
ms.openlocfilehash: 8be0df5cbe4b8d4a640c9b6c2e126b3828254fd6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595107"
---
# <a name="namespace-or-type-specified-in-the-imports-39ltqualifiedelementnamegt39-doesn39t-contain-any-public-member-or-cannot-be-found"></a>가져오기에 지정 된 Namespace 또는 형식을 &#39; &lt;qualifiedelementname&gt; &#39; 대상이&#39;t public 멤버가 또는 형식을 찾을 수 없음
Imports'에 지정 된 Namespace 또는 형식을\<qualifiedelementname >' public 멤버가 없거나 찾을 수 없습니다. 해당 네임 스페이스 또는 형식 정의 되어 있고 하나 이상의 public 멤버를 포함 합니다. 별칭 이름에는 다른 별칭 포함 되어 있지 않은지 확인 하십시오.  
  
 `Imports` 문을 지정 하거나 찾을 수 없거나 정의 하지 않는 포함 하는 요소 `Public` 멤버입니다.  
  
 A *요소가 포함 된* 네임 스페이스, 클래스, 구조체, 모듈, 인터페이스 또는 열거형 일 수 있습니다. 포함 하는 요소, 변수, 프로시저 또는 다른 요소를 포함 하는 같은 멤버를 포함합니다.  
  
 가져오기의 목적은 한정 하지 않고 코드 네임 스페이스 또는 형식 멤버에 액세스를 허용 하도록 합니다. 프로젝트의 네임 스페이스 또는 형식에 대 한 참조를 추가 해야 할 수도 있습니다. 자세한 내용은 "포함 된 요소 가져오기"를 참조 [선언 된 요소에 대 한 참조](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)합니다.  
  
 컴파일러에서 지정 된 포함 하는 요소를 찾을 수 없는 경우을 사용 하는 참조를 확인할 수 없습니다. 요소를 찾습니다 있지만 요소는 노출 하지 않는 경우 `Public` 멤버 다음 참조가 없는 성공할 수 있습니다. 두 경우 모두에서 요소를 가져오는 의미가 없습니다.  
  
 포함 하는 요소를 가져오기 별칭을 할당 하는 경우 다음 사용할 수 없다는 해당 가져오기 별칭을 다른 요소를 가져오는 것을 명심 하십시오. 다음 코드는 컴파일러 오류를 생성 합니다.  
  
 `Imports`   `winfrm`   `= System.Windows.Forms`  
  
 `' The following statement is`   `INVALID`   `because it reuses an import alias.`  
  
 `Imports behav =`   `winfrm`  `.Design.Behavior`  
  
 **오류 ID:** BC40056  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  포함 하는 요소는 프로젝트에서 액세스할 수 있는지 확인 합니다.  
  
2.  포함 하는 요소 사양 다른 가져오기에서 모든 가져오기 별칭에 포함 되지 않습니다 확인 합니다.  
  
3.  포함 하는 요소가 하나 이상를 통해 노출 된 확인 `Public` 멤버입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Imports 문(.NET 네임스페이스 및 형식)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [Namespace 문](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [공용](../../../visual-basic/language-reference/modifiers/public.md)  
 [Visual Basic의 네임 스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [선언된 요소 참조](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
