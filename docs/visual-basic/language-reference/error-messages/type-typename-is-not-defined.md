---
title: 형식 &#39; &lt;typename&gt; &#39; 정의 되어 있지 않습니다
ms.date: 07/20/2015
f1_keywords:
- vbc30002
- bc30002
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
ms.openlocfilehash: 20f36a06000d0197ad80b83766f6612a474d5758
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595188"
---
# <a name="type-39lttypenamegt39-is-not-defined"></a>형식 &#39; &lt;typename&gt; &#39; 정의 되어 있지 않습니다
문이 정의 되지 않은 형식에 대 한 참조를 만들었습니다. 선언문의 형식을 같은 정의 `Enum`, `Structure`, `Class`, 또는 `Interface`합니다.  
  
 **오류 ID:** BC30002  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   형식 정 및 참조 둘 다 사용 하는 동일한 철자를 확인 합니다.  
  
-   형식 정의 참조에 액세스할 수 있는지 확인 하십시오. 예를 들어, 형식이 다른 모듈에서 선언 된 경우 `Private`, 참조 하는 모듈로 형식 정의 이동 하거나 선언 `Public`합니다.  
  
-   형식의 네임 스페이스 프로젝트 내에서 다시 정의 되지 않는지 확인 하십시오. 사용 하 여는 `Global` 키워드 형식 이름을 정규화 해야 합니다. 예를 들어, 명명 된 네임 스페이스를 정의 하는 프로젝트 `System`, <xref:System.Object?displayProperty=nameWithType> 사용 하 여 정규화 하지 않은 형식에 액세스할 수 없습니다는 `Global` 키워드: `Global.System.Object`합니다.  
  
-   형식이 정의 되어 있지만 Visual Basic을 사용 하면 클릭에 개체 라이브러리 또는 정의 된 형식 라이브러리 등록 되지 않은 경우 **참조 추가** 에 **프로젝트** 메뉴를 선택한 후 적절 한 개체 라이브러리 또는 형식 라이브러리입니다.  
  
-   대상된.NET Framework 프로필의 일부인 어셈블리에 형식 인지 확인 합니다. 자세한 내용은 [.NET Framework 대상 지정 오류 문제 해결](/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic의 네임 스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 [Enum 문](../../../visual-basic/language-reference/statements/enum-statement.md)  
 [Structure 문](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Class 문](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Interface 문](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [프로젝트의 참조 관리](/visualstudio/ide/managing-references-in-a-project)
